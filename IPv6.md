Nach IPv6 Standard muss nur SLAAC implementiert sein, statische Adressen und DHCPv6 sind optionale Features

Netzprefix: die linke ~64bit der Adresse, analog zum IPv4 Netzid
## SLAAC
Stateless Address auto-configuration ist das Verfahren, mit welchem IPv6 Clients zu ihrer Adresse kommen. Der Ablauf ist folgender:
![[slaac.excalidraw]]

Eine Router Solicitation ist ein Multicast vom Client, der alle Router auffordert Router Advertisments zu senden. Theoretisch wäre diese nicht nötig, da Router alle 200s eine RA senden.
Das RA enthält das Default-Gateway, den Prefix des Netzes und optional die Managed/Other Flags. Diese bestimmen wie weiter verfahren wird. 
Client bildet Interface ID (EUI64 oder Zufall)

Duplicate Adress Detection (DAD), vergleichbar mit Gratitious ARP

Wenn Other Flag gesetzt => DHCPv6 Request (DNS, Domäne, ...)
Wenn Managed Flag gesetzt => Prefix vom DHCP Server, ev. Adresse nach Hostname/MAC (Prefix im RA wird ignoriert, kann weggelassen werden)
beide setzen unsinnig
## DHCPv6
