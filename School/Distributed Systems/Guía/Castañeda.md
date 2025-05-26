---
tags:
---
Date: 2025-05-22 : 12:01
***
## Module 3: Network Security Concepts
### 3.1 Current State of Cybersecurity
#### 3.1.1 Current State of Affairs
#Q 
- **Asset** is anything from the organization that has :: Values-
- **Vulnerability** is a point in a system that is :: Weak.
- **Exploit** is taking advantage of a :: Vulnerability.

#### 3.1.2 Vectors of Network Attacks
#Q 
- **Attack Vector** is the path by which a... can gain... to a server, network, etc. :: Threat actor, access.
- **Attack Vectors** can come from... or... :: Inside, outside of the organization.
- Internal threats can cause **more damage** than :: External ones.

#### 3.1.3 Data Loss
#Q 
- **Data Loss** is when an organization's data is :: Lost, stolen or leaked.
- Data loss can **cause** damage of the..., loss of... actions regarding... :: Reputation, competitive advantage or customers, law.
- Some **data loss vectors** are :: Unencrypted devices, Email/Social Networking, Cloud Storage Devices, Removable Media (USB), Hard Copy (Destroy no longer needed info), Improper Access Control (passwords)

### 3.2 Threat Actors
#### 3.2.1 The Hacker
#Q 
- The **white hat hacker** uses their skills for :: Legal, ethical purposes.
- The **gray hat hacker** does things... but not for... :: Unethical things, personal gain.
- The **black hat hacker** they do... for... :: Unethical things, personal gain.

#### 3.2.2 Evolution of Hackers
#Q 
- When and how did **hacking started** :: In the 1960's with phone phreaking.
- **Script Kiddie** is an inexperiences hacker that uses :: Existing tools.
- **Vulnerability Broker** they are usually... that discover... for a... :: Gray hat hackers, exploits, prize.
- **Hacktivists** they are... hackers that protest by doing things like... :: Gray hat, leaking info.
- **Cyber criminal** is any employed or self-employed :: Black hat hacker.
- **State-Sponsored** are... or... hackers that target..., ... and... :: White, black, governments, terrorists, corporations.
### 3.3 Threat Actors Tools
#### 3.3.1 Threat Actor Tools
#Q 
- One of the many Threat Actor Tools is :: Pen Testing Tools.
- We have many pen-testing tools such as :: Password crackers, packet sniffers.

#### 3.3.2 Introduction to Attack Tools
#Q 
- Over the years **attack tools** have augmented their... but **technical knowledge** has... :: Complexity, decreased.

#### 3.3.3 Evolution of Security Tools
#Q 
- Penetration testing tools help to... if a system is... :: Validate, secure
- **Password crackers** help to :: Crack and recover passwords.
- **Wireless Hacking Tools** are used to hack into a :: Wireless Network.
- **Packet Crafting Tools** are used to forge... and use them to test... :: Packets, firewalls.
- **Vulnerability Exploitation Tools** help... if a remote host is vulnerable to a security attack :: Identify.

#### 3.3.4 Attack Types
#Q 
- **Eavesdropping Attack** is when the threat actor... to the network traffic, it is also called... :: Listens, sniffing.
- **Denial of Service Attacks** can... networks until a shutdown occurs :: Flood.

### 3.4 Malware
#Q 
- Viirus necesita accion humana
- Trojano es programa que parece bueno, pero trae algo malo.
- Ransomware :: Encriopta tu info
- Rootkit :: Gana privilengios de administrador

### 3.5 Common Network Attacks
#Q 
- Ataques de reconocimiento :: Son para obtener info de donde hay vulnerabilidades.
- Ataques de acceso :: Buscan ganar **acceso** a las cuentas. (Hay de password y de spoofing que es falsificar los paquetes)
- Ataques de Ingeniería Social :: Manipular individuos para divulgar info.
- Denial of Service Attack :: Interrumpe la red de dos formas (mucho tráfico o paquetes con un formato malicioso).

### 3.6 IP Vulnerabilities & Threats
#Q 
- Los ataques ICMP :: Pueden servir de reconocimiento
- Amplification and Reflection Attacks :: Are used to create DoS Attacks.
- Address Spoofing  Attacks :: Falsificar IP de los paquetes

### 3.7 TCP and UDP Vulnerabilities
#Q 
- TCP SYN Flood Attack :: El atacante abre varias sesiones TCP pero nunca responde en el handsahke por lo que a usuarios verdaderos el servidor les niega servicio.
- TCP Reset Attack :: Terminar de forma abrupta la sesión TCP.
- TCP Session Hijacking :: Le robas la sesión TCP a alguien.
- UDP Flood Attack :: Crea mucho tráfico y provoca lo mismo que un DoS.

### 3.8 IP Services
#Q 
- El ARP sirve para :: Saber el MAC de un dispositivo con una MAC dada.
- ARP Cache Poisoning sirve para hacer :: Ataques de Man In The Middle.
- DNS Attacks :: Hay **DNS Open Resolver** que es usar un DNS público, **DNS Domain Shadowing Attacks** Crea subdominios maliciosos
- DHCP Attacks :: Es cuando un servidor DHCP falso se pone y da información falsa (como un gateway falso)

### 3.9 Network Security Best Practices
#Q 
- Recordar el Triangulo **CIA** :: Confidencialidad, Integridad y Availability
- Firewalls hacen que las políticas de control de acceso :: Se cumpla.
- AAA Server tiene una base de datos que dice quien :: Puede administar la red.
- ESA siginifica... y sirve para... :: Email Security Appliance, filtrar email.
- IPS monitorea la red buscando :: Malware.

### 3.10 Cryptography
#Q 
- 
## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Distributed Systems/Guía/Castañeda.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```