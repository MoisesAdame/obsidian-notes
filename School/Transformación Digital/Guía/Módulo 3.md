---
tags:
---
Date: 2025-03-06 : 11:59
***
## Introducción al Cómputo en la Nube
### Cómputo en la Nube
#Q 
- Antes las compañías tenían un modelo... en el cual tenían que... :: **On-premise**, pagar todo.
- La nube son son servicios... por lo que un conjunto grande de equipos... a las empresas :: Compartidos, se renta.
- Una de las principales razones por las que la nube funciona es por que :: Es **compartimentalizada**, es decir, no hay comunicación entre los clientes.
- Quien da los servicios de cloud se llama :: Cloud provider.

### Consumo Bajo Demanda
#Q 
- Dependiendo de tu consumo :: Es cuanto te cobro.
- Su efecto ha sido la :: **Democratización** del consumo en la nube.
- La **democratización de la nube** tiene como consecuencia que :: Empresas de todo tamaño la puedan usar.

### Nube Privada
#Q 
Es cuando una empresa tiene su propio... al que tiene... :: Centro de datos, acceso.

### Servicios de Cómputo en la Nube
#Q 
- **On-Site** es lo que la organización tiene que :: Pagar (Almacenamiento, servidores, aplicaciones, etc.)
- **IaaS** el cloud provider se hace cargo de cosas como :: Networking, storage, servers y virtualización. (Bueno para migrar)
- **PaaS** el cloud provider se hace cargo de cosas como :: Networking, storage, servers, virtualización, O/S, middleware y runtime. Nosotros solo nos hacemos cargo de data y application.
- **SaaS** el cloud provider se hace cargo de :: Todo (Tal vez solo tu te encargas de configurar.)



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