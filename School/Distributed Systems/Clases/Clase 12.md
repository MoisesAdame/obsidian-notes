---
tags:
---
Date: 2025-05-13 : 17:08
***
## Módulo Molina 
Temas de Examen
1. Como crear VLAN's?
2. Como hacer intervlan routing
3. Levantar OSPF
4. HSRP
5. Levantar server dhcp

## Configuraciones
### Swicth 1
enable
conf t

vlan 10
name Teachers
exit

vlan 20
name Students
exit

interface gig0/1
switchport mode trunk
switchport trunk allowed vlan 10,20
no shut
exit

