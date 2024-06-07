- Dynamic Host Configuration Protocol, definiert in #RFC2131
- ersetzt BOOTP (Bootstrap Protocol), definiert 1985 in #RFC951
- Läuft über UDP
- Server Port 67, Client Response Port 68 (gleiches bei BOOTP)
Wenn auf DHCP konfiguriert, sendet eine Netzwerkkarte bei Aktivierung DHCP-Requests ins Netzwerk (Broadcast), ein DHCP-Server antwortet darauf mit der Konfiguration für den Client (IP-Adresse aus Adresspool, Default-Gateway, DNS-Server, Hostname, ...)