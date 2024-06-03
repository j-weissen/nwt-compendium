Root schaltet nie Ports ab
Bridge ID (BID) 8 byte, 2 Prio + 6 MAC
Metriken: 1. Geschwindigkeit, 2. Portnummer, Später BID
GBit Kosten 4
Leitungsprioritäten nicht Zukunftssicher (Was ist bei 10GBit)
Bei neuen Versionen "Lange Pfadkosten" => GBit 20000
Ohne Redundanz lieber Loopback Detection
Problem bei hochbelasteten Netzwerken wenn BPDUs nicht ankommen
## Protokolle
- STP - Spanning Tree Protocol
- RSTP - Rapid STP (Umbau ist schneller, da Ausfallsstrecken schon berechnet werden bevor sie nötig sind)
- MSTP - Multiple STP (STP pro VLAN, nicht genutzte Leitungen können in anderen VLANs verwendet werden)
- Cisco proprietär:
	- PVST - Per VLAN STP
	- PVST+ (PVST mit rapid)
	- bei nur einem VLAN kompatibel mit freien Standarts (Achtung bei Prioritäten da PVST VLAN IDs einrechnet)