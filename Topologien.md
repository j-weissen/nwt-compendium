# Bus
Mehrere Clients schreiben und lesen auf/vom gleichen Kabel. Sie sind verbunden über T-Stücke, am Ende sind [[Endwiderstände]] mit Ohmschem Widerstand des Wellenwiderstands des Kabels notwendig um Reflexionen zu vermeiden.
![[bus.excalidraw]]
## CSMA/CD
Carrier-sense multiple access with collision detection ist ein Protokoll zur fehlerfreien Übertragung von Daten in Bussystemen.
Vereinfachter Ablauf, wenn ein Client senden will:
![[csmacd.excalidraw]]

# Ring
Jeder Client ist mit zwei anderen Verbunden, wodurch sich ein geschlossener Kreis ergibt. Das hat gegenüber Bussystemen den Vorteil, dass viele Kollisionen vermieden werden können. Je nach implementation können die Übertragungsstrecken unidirektional oder duplex sein. 
![[ring.excalidraw]]


- Stern