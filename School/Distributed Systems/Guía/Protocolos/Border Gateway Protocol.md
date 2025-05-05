---
tags:
---
Date: 2025-05-05 : 12:56
***
## Subtitle
Value

**Configuration R1**
enable
conf t

interface gig0/0
ip address 172.16.1.1 255.255.255.0
no shutdown
exit

router bgp 65100
neighbor 172.16.1.2 remote-as 65101


**Configuration R2**
enable
conf t

interface gig0/0
ip address 10.1.1.1 255.255.255.0
no shutdown
exit

interface gig0/1
ip address 10.2.2.1 255.255.255.0
no shutdown
exit

interface gig0/2
ip address 192.16.1.2 255.255.255.0
no shutdown
exit

router ospf 10
router-id 2.2.2.2
network 10.0.0.0 0.255.255.255 area 0
exit

router bgp 65101
neighbor 172.16.1.1 remote-as 65100
exit

**Configuration R3**
enable
conf t

interface gig0/0
ip address 10.1.1.2 255.255.255.0
no shutdown
exit

interface gig0/1
ip address 10.2.2.2 255.255.255.0
no shutdown
exit

interface gig0/2
ip address 192.168.1.2 255.255.255.0
no shutdown
exit

router ospf 10
router-id 3.3.3.3
network 10.0.0.0 0.255.255.255 area 0
exit

router bgp 65101
neighbor 192.168.1.1 remote-as 65102
exit

**Configuration R4**
enable
conf t

interface gig0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

router bgp 65102
neighbor 192.168.1.2 remote-as 65101


## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "<% tp.file.path(true) %>",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```