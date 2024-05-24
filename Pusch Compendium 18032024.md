# LWL
- LWL = Wellenleiter für sichtbare und infrarote em. Wellen
- Abmessungen des LWL >>> Wellenlänge des Signals => Optikgesetze gelten
- Datenübertragung in der Regel durch Intensitätsmodulation
- Dispersion ~ Kabellänge
## Pro/Contra
### Vorteile
- hohe Trägerfrequenz => hohe Bandbreite => hohe Datenrate
- geringe Dämpfung => hohe Reichweite
- geringes Volumen und Gewicht
- em. Störungen ausgeschlossen (Blitze, Übersprechen)
- galvanische Trennung von Sender/Empfänger (kein gemeinsames Potenzial nötig)
- temperaturunabhängig
- zukunftssicher
- gutes Preis/Leistungsverhältnis
- langlebig
### Nachteile
- Krümmungsradien sind einzuhalten (r > r<sub>min</sub>)
- Steckermontage und Splicen aufwändig
- keine Fernspeisung möglich
- Werkzeug teurer
- komplexere Messtechnik
## Material
- Quarzglas dotiert mit GeO<sub>2</sub> od. P<sub>2</sub>O<sub>5</sub> um Brechungsindex zu erreichen
- Kunststofffaser (POF)
## Arten

| Name                           | Abmessungen | Anmerkung                                                         |
| ------------------------------ | ----------- | ----------------------------------------------------------------- |
| Multimode Stufenindexfaser     | 200um/100um | veraltet, starke Laufzeitunterschiede => starke Dispersion        |
| Multimode Gradientenindexfaser | 125um/50um  | Brechzahl nach außen weniger => Signal "biegt" sich nach und nach |
| Singlemode Faser               | 125um/8um   | standard, nur ein Mode => keine Laufzeitunteschiede               |

# Wellenlängenmultiplex

## Arten

| Name                           | Kürzel | Anwendung           | Kanäle | Datenrate/Kanal | Bänder      | Anmerkung                            |
| ------------------------------ | ------ | ------------------- | ------ | --------------- | ----------- | ------------------------------------ |
| Coarse Wave Division Multiplex | CWDM   | △$\lambda$ 20-100nm | 18     | 2,5Gbit/s       | 1260-1625nm | günstige Alternative                 |
| Dense Wave Division Multiplex  | DWDM   | △$\lambda$ 0,2-2nm  | 160    | 50Gbit/s        | 1530-1625nm | präzise, teure Komponenten notwendig |

## Arrayed Waveguide Grating
- Implementation durch optische Bauteile => keine em. Umwandlung nötig
![[multiplexer.png]]
# Datenratenreduktion
## Arten
### Redundanzreduktion
- verlustfrei, reversibel
- Reduktionsfaktoren 1,2 bis 10
- zB FLAC
#### Run Length Coding (RLC)
- Markierungsinformation (`A`) vor Anzahl
- `WWWWWSSWSSSSSSS` => `A5WSSWA7S`
- Anwendung
	- Fax
	- JPEG
### Irrelevanzreduktion
- verlustbehaftet
- nutzt Wahrnehmung des Menschen aus
- zB MP3, AAC
#### Vektorquantisierung
- Beidseitige Tabelle aus Mustervektoren
- Anzahl Mustervektoren <<< Anzahl möglicher Vektoren
- Index des "nächsten" Vektors (nach Kriterium) wird übertragen
## Audio
- Aufspaltung in Frequenzbereiche mit angepasster Quantisierung
- Ausnutzung von Verdeckungseffekten
- 12.1/12.2