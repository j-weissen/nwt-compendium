# Empfangen
Im Normalfall wird das Empfangen von E-Mails über Polling implementiert, wird im Client konfiguriert, zB wird der Mailserver alle 15 Minuten nach neuen Mails abgefragt.

## Protokolle
### IMAP
IMAP (Internet Message Access Protocol) läuft prinzipiell auf Port 143/tcp, IMAPS (IMAP Secure) auf Port 993/tcp auf TLS. Mails werden vom Server kopiert, der Status (gelesen/ungelesen) und Ordner werden am Server verwaltet. 

#### Verschlüsselung
IMAPS ist einfach IMAP in einem TLS Tunnel. Auf Port 993 wird auf einen TLS Handshake gewartet. Wird IMAP unverschlüsselt verwendet, kann auf eine verschlüsselte Verbindung aufgestuft werden, falls beide Kommunikationspartner STARTTLS unterstützen: Beim TCP Handshake werden vom Server CAPABILITYs gesendet, auch STARTTLS, falls aktiv. Antwortet der Client mit dem STARTTLS Befehl, beginnt ein TLS Handshake. 

### POP3
POP3 läuft am Port 110 auf TCP. Mails werden heruntergeladen, am Server als gelesen markiert. Ordner sind clientsided. POP3 ist nicht mehr zu empfehlen, da bei mehreren Clients keine Synchronisation für gelesene Mails passiert.

#### Verschlüsselung
Auch POP3 unterstützt STARTTLS mit dem STLS Befehl.

#### Server
POP3 Server haben ein Sicherheitrisiko: Bei Authentifizierung mit Username liefert der Server sofort und ohne Angabe eines Passwortes, ob der gegebene User existiert. Wird mehrfach ein falsches Passwort angegeben landet der User in einer "Teergrube": Die Verifikation weiterer gegebener Passwörter wird künstlich in die länge gezogen um Bruteforce-Attacken schwieriger zu machen.

### MAPI
Microsoft-proprietär gibt es auch MAPI (Messaging API). Dieses kann zwischen MS Exchange Servern und Outlook Clients gesprochen werden.

# Senden (SMTP)
Historisch definiert in #RFC821 und #RFC822 / #RFC2821 und #RFC2822, modern #RFC5321 und #RFC5322.
\*21 definiert SMTP, also das "Kuvert" der Mail, \*22 definiert das Internet Message Format also den Inhalt der Mail. SMTP Pakete werden zwischen Mailservern gesendet, über POP3 oder IMAP wird nur IMA gesendet. 

- SMTP
	- `HELO` (wird nicht immer geprüft),
	- `MAIL FROM: ...`
	- `RCPT TO: ...`
	- Daten, beendet mit "." in einer sonst leeren Zeile 
	- `QUIT`
- IMF
	- `FROM: ...`
	- `TO: ...`
	- `SUBJECT: ...`
	- `DATE: ...`
	- Text
Bemerke, dass SMTP und IMF einen Absender definieren, dieser muss nicht übereinstimmen! Ein Mailclient hat keine Möglichkeit, den tatsächlichen SMTP Sender  herauszufinden. Abhilfe schaffen nur verschlüsselte, signierte Mails.

Port 25/tcp ohne Passwort, für Kommunikation zwischen Mailservern, meist unverschlüsselt
Port 587/tcp (Submission Port) mit Adresse/Passwort für Client zu Server, Mail abgeben, nutzt meist STARTTLS
Port 465/tcp SMTPS über TLS, für Kommunikation zwischen Servern unüblich

Handshake:
Responses mit HTTP-ähnlichen status codes (2XX OK, 4XX Temporary Error)
bei 4XX probiert der sendende Mailserver für normalerweise 72h wieder, nach 1h Info an User

```
220 webmail.htl-steyr.ac.at ESMTP
HELO example.com
250 webmail.htl-steyr.ac.at
MAIL FROM: me@example.com
RCPT TO: wolfi@htl-steyr.ac.at
```

Schickt ein Mailserver eine Mail an einen anderen Mailserver, gibt es (je nach Config) mehrere Möglichkeiten ob die Mail angenommen wird:
- Bevor der TCP Handshake angenommen wird
	- Hat der Sender eine IP aus einem statischen Pool?
	- Ist der Sender ein registrierter Mailserver?
		- IP wird auf FQDN aufgelöst (PTR-Record)
		- FQHN wird auf Mailserver aufgelöst (MX-Record)
		- Passt eine Mailserver IPs zur Sender IP, wird die connection angenommen
	- Darf der Mailserver die Mail versenden?
		- Stimmt mit FQDN überein
		- oder steht im SPF TXT-DNS-Record

## Trivia
- Microsoft Exchange Server ist weit mehr als ein Mailserver. Mit Outlook als Client können auch Kalender, Kontakte, etc. verwaltet werden.
- SMTP Auth ist auch über ein Zertifikat möglich
- Anstatt Polling kann IMAP erweitert auch die TCP-Session offen halten und auf eine Notifikation des Servers warten, wenn eine Mail ankommt.
- Im SMPT ist Pipelining möglich, sofern es der Mailserver unterstützt: Mehrere SMTP Paktete werden in einer TCP-Connection aneinandergereiht gesendet, das trickst manche Spamfilter aus.
- EHLO sendet Liste von unterstützten Features
- Liste der Mailserver über die die Mail gelaufen ist, steht im IMF-"Header"

