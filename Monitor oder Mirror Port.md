Ein Switchport spiegelt den Verkehr eines anderen Ports für Monitoringzwecke. 
Dabei kann oft ein- und ausgehender Traffic auf unterschiedliche Ports gespiegelt werden. Sollte beides auf den gleichen Port gespiegelt werden ist anzumerken, dass aufgrund von Sende- und Empfangsstrom die doppelte Bandbreite genutzt werden würde und der Port das unterstützen sollte. Eine Alternative bieten [[NetFlow und sFlow]].
![[monitor_port.excalidraw]]

Beispielconfig fürs Bild auf Cisco:
```
switch(config)# monitor session 1 source interface FastEthernet0/
switch(config)# monitor session 1 destination interface FastEthernet0/2
```
Cisco bietet auch die Möglichkeit von Remote Mirroring, also einen Monitor Port, welcher den Port eines anderen Switches spiegelt.