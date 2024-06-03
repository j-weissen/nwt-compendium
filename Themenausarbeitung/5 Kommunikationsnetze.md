## *PUSC* Übertragung digitaler Sprachdaten im IP-Netz
Die Telekom Austria hat vor einigen Jahren begonnen, die Sprachtelefonie im Core-Netz auf Voice-Over-IP umzustellen. Die Sprachdaten werden getrennt von Internetdaten in eigenen Glasfasernetzen geführt, damit es zu keinen für Sprachdaten kritischen Zeitverzögerungen kommen kann.

OSI-Modell, Zusammenspiel der Schichten, Sprachübertragung und Zeitverzögerung, …
- Mikrofone
- Geroutete Pakete statt Punkt zu Punkt
- Telekom: Überlastete Router bringen Zeitverzögerung => eigenes Netz für VoIP und Leitungen nur 30% auslasten
- ARQ lieber auf L2 als L4 da Echtzeit (4G)
- GSM
	- für Sprachdaten kleinere Interleaver & Fehlerverschleierung
	- für Internet größere Interleaver, nicht Echtzeitfähig dafür Fehlerfrei

## *PUSC* Einsatz von ARQ in der Netzwerktechnik
In modernen Mobilfunkstandards wird ARQ auch bereits auf der Sicherungsschicht eingesetzt, in den älteren Standards nur auf Layer 4. Analysieren und bewerten Sie beide Konzepte!

OSI-Modell, Fehlerdetektion, Fehlerkorrektur (FEC), ARQ, hybrides ARQ, …

## *PUSC* Übertragungsverfahren für eine Funkstrecke in einem Mobilfunknetz
Eine Funkstrecke bildet eine Teilstrecke eines Übertragungssystems. Messungen an der Übertragungsstrecke haben gezeigt, dass es (aufgrund von Bewegung) häufig zu Bündelfehlern kommt. Ihre Aufgabe ist der Entwurf eines geeigneten Übertragungsverfahrens.

OSI-Modell, Fehlerdetektion, Fehlerkorrektur (FEC), Zeitinterleaving, ARQ, hybrides ARQ, …

## *PUSC* Dynamische Auswahl des Übertragungsverfahrens
Häufig sind Teilstrecken von Übertragungsnetzwerken als Funkstrecken ausgeführt, wie es z.B. in Mobilfunksystemen der Fall ist. Die Übertragungsverhältnisse sind sehr variabel. Entwerfen Sie ein Übertragungskonzept, wo sich das Netzwerk den Übertragungsverhältnissen dynamisch anpasst.

OSI-Modell, aktuelle Kanalqualität, Fehlerkorrektur (FEC), ARQ, hybrides ARQ, Adaptive Multirate (AMR), …
- AMR
	- Kanalcodierung variieren
	- bei schlechterer Übertragung mehr komprimieren / Redundanz

## *PUSC* Einsatz von Modulationsverfahren in der Netzwerktechnik
Häufig sind Übertragungsnetzwerke ganz oder teilweise als Funkstrecken ausgeführt. Auch das österreichische Bundesheer setzt auf Funktechnik, um vom Ort und von Infrastruktur unabhängig zu sein, um beispielsweise KFOR-Truppen im Ausland verlässlich erreichen zu können, was über kabelgebundene Netzwerke ev. nicht der Fall sein bzw. unterbunden werden könnte. Auch der terrestrische Rundfunk arbeitet funkbasiert. Auf solchen Strecken muss die Übertragung moduliert erfolgen.

AM, FM, warum überträgt man im HF-Bereich, …
- Amateurfunker
- Kurzwelle (RK im Katastrophenfall)
- Mittelwelle
	- manchmal in Amerika gängig für ländliche Gebiete
	- "Weltempfänger", Radio für überall
- Reflektion an der Ionosphäre (Frequenzen anpassen)
- je höher die Trägerfrequenz, umso mehr verfügbare Bandbreite, umso mehr mögliche Datenrate
- Antennen (lambda=c/f)
- Satelliten
- Breite Kanäle in LF-Bereich technisch nicht implementierbar, höhere Frequenz für mehr Bandbreite nötig
- Fresnelzone
- Modulation im Basisband
- Störungen wirken sich additiv auf die Amplitude und somit bei AM die Informationen aus. FM somit störungsfreier
- 87,5-108MHz FM mit 200kHz Bändern
- Ausbreitung bei LF besser als bei HF: 
- Digitale Dividende
	- viele Funkressourcen für Fernsehen reserviert
	- digitales Fernsehen: Linz und Steyr könnten (sofern nur ~1µs Asynchronität) das gleiche senden ohne sich zu stören (=Gleichwellenfunk)
	- 800MHz Band geht an Mobilfunk für Breitbandinternet im ländlichen Bereich
	- Hügel etc. für 800MHz kein Problem => große Gebiete pro Funkstation
	- In der Stadt mehrere Zellen mit weniger Reichweite
- FM Breitbandiger als AM => bessere Übertragungsqualität von zB Musik

## *PUSC* Beurteilung einer Nachrichtenleitung nach übertragungstechnischen Aspekten.
Ein Telekommunikations-Anbieter beabsichtigt einen Netzausbau zur Kapazitätserweiterung vorzunehmen. Davor ist eine Bewertung vorhandener Leitungsinfrastruktur vorzunehmen, wobei es sich um ein Glasfasersystem handeln möge.

Lichtleiter: Aufbau, Funktionsweise, Anwendung, …