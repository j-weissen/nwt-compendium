Das **Hypertext Transfer Protocol** gilt als wichtigstes Protokoll des Webs und wurde erfunden von Tim Berners-Lee. Es funktioniert über ein Client-Server Modell und ist Textbasiert, die Daten sind "stringly" typed, genauere Datentypen müssen durch Formate wie [[JSON]] implementiert werden. Es wird klassisch zum Transfer von HTML, CSS, JS, JSON oder XML verwendet, theoretisch können beliebige Strings übertragen werden.

# Aufbau
Beispielrequest:
```http
GET /index.html HTTP/1.1
Authentication: Bearer afzJHr6D4VkY0jwxxN1pbw==
```
## 1. Start-Line
### Request
Bei Requests auch Request-Line genannt, welche sich wiederum aus drei durch Leerzeichen getrennten Komponenten zusammensetzt
1. Die HTTP Methode/Verb
2. Die URI, also der Pfad der angefragten Resource. Klassisch ist das der Pfad zur angefragten HTML-Datei. Zudem können mit einem `?` von der URI getrennt Parameter übertragen werden, diese wiederum werden durch `&` getrennt. Beispiel: `/index.html?name=wolfi&vorliebe=cisco` Diese Parameter müssen URL-encoded sein, zB würde ein Leerzeichen durch `%20` ersetzt werden.
3. Die HTTP Version
#### HTTP Methoden
Die verschiedenen HTTP Methoden sind für verschiedene Aktionen am Server deklariert, wobei die erlaubten Auswirkungen auf Daten am Server für unterschiedliche Methoden genau definiert sind. Zudem sind auch Bodys in Request sowie Response je nach Methode, benötigt/erlaubt/verboten. Der Standard ist `GET`, dieser fragt den Server einfach nach einem Transfer der angegebenen Resource. `POST` wird für Web-Formulare verwendet, da bei dieser Methode im Gegensatz zu `GET` ein Request Body gesendet werden kann, zudem wird es zum Erstellen von Objekten/Daten genutzt. Weitere vielgentzte HTTP Methoden sind: 
- `PUT` fürs Verändern oder Ersetzen einer Resource (im Unterschied zu `POST` idempotent)
- `PATCH` für das Verändern/Updaten von Teilen einer Resource (nicht unbedingt idempotent)
- `DELETE` zum löschen einer Resource, 
- `HEAD`, welche nur den Transfer der Header der angegeben Resource anfordert
### Response
Bei der Response sieht die Start-Line ähnlich aus:
1. Die HTTP-Version
2. Der Response-Code
3. Dem Namen des Response Codes

#### Response-Codes
Die HTTP Response Codes reichen von 100 bis 599, wobei nur ein Bruchteil davon definiert ist. 
- 100-199 Informationen
- 200-299 Erfolg
- 300-399 Umleitungen
- 400-499 Client Fehler
- 500-599 Server Fehler
Die Wichtigsten Status codes sind
- `200 OK` welcher eine erfolgreiche Abfrage von Daten markiert
- `201 CREATED` für erfolgreiches Erstellen von Daten
- `204 NO CONTENT` für Erfolg, aber einen leeren Response Body
- `400 BAD REQUEST` für ein Fehlschlagen aufgrund zB nicht lesbarer Daten, welche vom Client übermittelt wurden
- `401 UNAUTHORIZED` welcher durch "unauthenticated" besser beschrieben wäre,
- `403 FORBIDDEN`, also Fehlschlagen aufgrund von fehlenden Berechtigungen
- `404 NOT FOUND` wenn eine Resource nicht gefunden wurde
- `500 INTERNAL SERVER ERROR` wenn der Server durch nicht weiter erkärbare Umstände die Anfrage nicht erfüllen kann
## 2. Header
Auf der folgenden Zeile starten die Header, es darf keine Leerzeile dazwischen sein.
Diese enthalten Informationen wie zB Auth-Tokens, Browserart und Version, Akzeptierte/Gesendete Datenformate, Bevorzugte Sprache, ...
Die Header sind case-insensitive und werden als `key: value` formatiert (zB `Authorization: Bearer eqOJj82938Hod93j30sjj2==`)
Prinzipiell sind die Header frei wählbar, (`Wolfgang: Reisinger` wäre auch ein Valider Header) allerdings gibt es Header, die nur von den User Agents gesetzt werden dürfen, mit zB der JavaScript `fetch`-Funktion dürfen sie nicht bearbeitet werden. (Liste der forbidden headers https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name)

## 3. Body
Der Request Body ist durch eine Leerzeile (also zwei Linebreaks) von den Headern getrennt und enthält Daten, die an den Server übermittelt werden sollen. Der Typ der Daten wird als `Content-Type` Header angegeben, die Länge der Daten in Octets (also Bytes) im `Content-Length` Header. Durch diesem weiß der Empfänger auch, wann die Nachricht zuende ist.

# APIs
## REST
Heutzutage gängig sind REST-APIs (Representational State Transfer), aufbauend auf HTTP, ein gängiges Mittel um Programmierern Dienste oder Daten zugänglich zu machen. Die Konzepte sind start an HTTP gebunden: Es ist Stateless, die verschiedenen HTTP Methoden/Verben bestimmen die Aktionen. Als Datenformat wird meist JSON genutzt.

# Trägerprotokoll
HTTP wird prinzipiell über TCP übertragen, mit HTTPS (HTTP Secure, heutzutage standard) wird ein verschlüsselter TLS Tunnel genutzt. 
Bessere Performance als TCP liefert QUIC, ein auf UDP augbauendes Protokoll, welches bei HTTP3 auch als Trägerprotokoll verwendet werden kann. Nur wenige Webserver unterstützen dieses Protokoll heutzutage, Vorreiter ist der Erfinder Google. Ein Großteil der HTTP-Kommunikation zwischen Chrome Clients und Google Servern läuft heutzutage über QUIC. 