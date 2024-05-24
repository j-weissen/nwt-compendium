# Kategorien / Klassen
Übertragungsstrecken können nach ihren Übertragungseigenschaften in Kategorien und Klassen eingeteilt werden. Kategorien beschreiben dabei die einzelnen Komponenten (zB eine Dose oder ein Kabel) und Klassen den ganzen Permanent Link (Patchkabel + Dose + Verlegekabel + Dose + Patchkabel).
Bei der Klasse sticht die niedrigste Kategorie, ist die Dose zB nur Cat 6a aber alles andere Cat 7 ist der Link trotzdem der Klasse Fa zuzuordnen. Arbeitet man mit einer Mix&Match Konfiguration (Komponenten verschiedener Hersteller im Link), muss allerdings dies aufgrund von Kompatibilitäten nicht gegeben sein, der Link kann sich als noch schlechter Herausstellen als die Schlechtesete Komponente.
Klassen werden in Buchstaben, Kategorien in Zahlen angegeben. (A=1, B=2, ...)
Ein Permanent Link darf maximal 85m lang sein, mit max. 15m Patchkabel kommt ein Channel auf maximal 100m Kabelweg.

Übersicht über Klassen und Kategorien findet man hier: https://en.wikipedia.org/wiki/Twisted_pair#Building_infrastructure
Aktuell sollte bei neuen Installationen mindestens Cat 7 verlegt werden, Stecker sind oft Cat 6a.
# Dämpfung
Die Dämpfung einer Leitung beschreibt, wie sehr die Signalamplitude über die Länge des Kabels abnimmt, sie ist direkt proportional zur Kabellänge. Je höher die Dämpfung, desto öfter muss das Signal verstärkt werden.
# Crosstalk
Crosstalk (=Übersprechen) beschreibt das beeinflussen von der Übertragung von Signalen auf einem Draht zu einem anderen Draht, welcher Daten überträgt. Dabei verursachen wechselde elektrische Felder magnetische Felder, welche durch ihre Änderung wiederum induktiv Spannung auf den umliegenden Drähten induziert, was die dortigen Übertragungseigenschaften beeinträchtigt. Bei TP ist hierbei das Übersprechen von einem Adernpaar zu einem anderen gemeint.
Dieser Effekt tritt vor allem bei fehlerhafter Installation von Kabeln / Dosen auf.
## NEXT
NEXT steht für Near End Crosstalk, was bedeutet, dass das Übersprechen am nahen Ende des Kabels gemessen wird.
## FEXT
FEXT steht für Far End Crosstalk, was bedeutet, dass das Übersprechen am entfernten Ende des Kabels gemessen wird.
## ELFEXT
Equaled Level FEXT, welcher die Dämpfung des Überprechens über die Kabellänge einberechnet.
## AXT
Alien Crosstalk beschreibt das Übersprechen zwischen verschiedenen Kabeln. Dieser Wert kann nur mit sehr speziellen Messgeräten gemessen werden, da man mehrere Kabel anschließen muss. Bis GBit Ethernet ist der Effekt allerdings vernachlässigbar, erst ab 10GBit ist er ein Problem.
## Powersum NEXT/ELFEXT
Bei dieser Art von Crosstalk werden Signale auf drei der vier Adernpaare gelegt und der NEXT bzw. ELFEXT auf der vierten Leitung gemessen.
![[crosstalk.excalidraw]]
# ACR
Attenuation Crosstalk Ratio beschreibt das Verhältnis von Dämpfung zu Übersprechen. Wenn ein Signal über den Übertragungspfad zu viel gedämpft wird und das Übersprechen zu groß ist, steht am Ende ein Signal des anderen Adernpaars zur Verfügung – was nicht gewünscht ist. Je größer der Abstand zwischen Dämpfung und Übersprechen, desto besser.
# Laufzeitdifferenz
Die unterschiedlich stark verdrillten Adernpaare, wobei stärker verdrillte Paare länger sind als weniger stark verdrillte, bewirken, dass bei gleichzeitigem Einspeisen in die jeweiligen Paare die Signale zu unterschiedlichen Zeiten am anderen Ende ankommen. Eine zu große Differenz in den Ankunftszeiten kann bei der Nutzung von Gigabit Ethernet, 10GBit Ethernet oder anderen Anwendungen, die alle vier Adernpaare verwenden, zu Übertragungsstörungen führen.
# Rückflussdämpfung
Der Parameter drückt aus, wie effektiv das rücklaufende Signal durch Fehlanpassungen und Unstetigkeiten in der Verdrahtung gedämpft wird, wodurch nicht die gesamte Sendeenergie bis zum Ende gelangt und Teile des Signals reflektiert werden.