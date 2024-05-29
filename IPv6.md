Nach IPv6 Standard muss nur SLAAC implementiert sein, statische Adressen und DHCPv6 sind optionale Features
## SLAAC => Client will Adresse
Client sucht Router => sendet Multicast (Router Solicitation)
Könnte auch warten, da alle 200s Router eine RA schicken
RS triggered RA
RA enthält Prefix (Gateway, linke ~64bit der Adresse, analog zum IPv4 Netz, M/O Flags) bei O weiterhin SLAAC, bei M anders
Client bildet Interface ID (EUI64 oder Zufall)

Duplicate Adress Detection (DAD), vergleichbar mit Gratitious ARP

Wenn Other Flag gesetzt => DHCPv6 Request (DNS, Domäne, ...)
Wenn Managed Flag gesetzt => Prefix vom DHCP Server, ev. Adresse nach Hostname/MAC (Prefix im RA wird ignoriert, kann weggelassen werden)
beide setzen unsinnig
## DHCPv6
