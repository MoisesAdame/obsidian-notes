---
tags:
---
Date: 2025-03-06 : 11:59
***
## Introducción al Cómputo en la Nube
### Cómputo en la Nube
#Q  #AOSR/5u5o2
- Antes las compañías tenían un modelo... en el cual tenían que... :: **On-premise**, pagar todo. #AOSR/5u5o2/s/aepq
- La nube son son servicios... por lo que un conjunto grande de equipos... a las empresas :: Compartidos, se renta. #AOSR/5u5o2/s/5npu
- Una de las principales razones por las que la nube funciona es por que :: Es **compartimentalizada**, es decir, no hay comunicación entre los clientes. #AOSR/5u5o2/s/b4in
- Quien da los servicios de cloud se llama :: Cloud provider. #AOSR/5u5o2/s/7lo0

### Consumo Bajo Demanda
#Q  #AOSR/1on0l
- Dependiendo de tu consumo :: Es cuanto te cobro. #AOSR/1on0l/s/3f0h
- Su efecto ha sido la :: **Democratización** del consumo en la nube. #AOSR/1on0l/s/d16g
- La **democratización de la nube** tiene como consecuencia que :: Empresas de todo tamaño la puedan usar. #AOSR/1on0l/s/1ra7

### Nube Privada
#Q  #AOSR/4e4r7
Es cuando una empresa tiene su propio... al que tiene... :: Centro de datos, acceso. #AOSR/4e4r7/s/3puv

### Servicios de Cómputo en la Nube
#Q  #AOSR/436ue
- **On-Site** es lo que la organización tiene que :: Pagar (Almacenamiento, servidores, aplicaciones, etc.) #AOSR/436ue/s/44b3
- **IaaS** el cloud provider se hace cargo de cosas como :: Networking, storage, servers y virtualización. (Bueno para migrar) #AOSR/436ue/s/7c4g
- **PaaS** el cloud provider se hace cargo de cosas como :: Networking, storage, servers, virtualización, O/S, middleware y runtime. Nosotros solo nos hacemos cargo de data y application.
- **SaaS** el cloud provider se hace cargo de :: Todo (Tal vez solo tu te encargas de configurar.)

### Diferencia entre la Nube y una Implementación Local
#Q 
- La nube nos permite tener un **consumo** :: Adecuado.
- Cuando usamos la nube no hay :: Desperdicio, ni uso de mas.
- Todo esto se debe a que la nube es..., lo cual implica que los recursos se... según los cambios en... :: Elástica, expanden o reducen, demanda.

### Terminología Importante
#Q 
- **Alta disponibilidad** de un sistema es la capacidad de este de seguir siendo... aún cuando haya... :: Operacional, fallas.
- **Elasticidad** es la habilidad de la cloud de automáticamente :: Expandir o comprimir recursos de infraestructura.
- **Escalabilidad** sirve para gestionar una mayor... :: Carga de trabajo.
- La **elasticidad** intenta satisfacer necesidades... mientras que la **escalabilidad** intenta satisfacer necesidades... :: Dinámicas, estáticas.

### Beneficios de Cloud Computing
#Q  #AOSR/6f905
- En vez de una inversión de capital los gastos son :: Variables.
- Como cloud provider para que el modelo de negocio funcione debo de vender a..., esto se llama... :: Millones de empresas, economía a escala. #AOSR/6f905/s/1drh
- Tu **time to market** se..., eso quiere decir que puedes ser una empresa mas... :: Reduce (Te ahorras el tiempo de cotizar, instalar y virtualizar y solo te encargas de virtualizar.), competitiva e innovadora.

## Datos
### Introducción
#Q 
- Los números y las letras :: No son datos.
- Los datos **solo son útiles** si tengo :: El contexto.
- Los **datos** son :: Hechos o piezas de información. Es inútil sin el procesamiento apropiado.
- Los **datasets** son :: Datos organizados.
- La **metadata** es la :: Información sobre la información.

### Tipos de Datos
#Q 
- Los datos **cuantitativos** son :: Contables o medibles.
- Los datos **cualitativos** se basan en la :: Interpretación
- Los datos **cuantitativos** nos dicen :: Cuánto?
- Los datos **cualitativos** nos ayudan a entender :: El por qué?

### Data Driven
#Q 
- Consiste en :: Tomar **decisiones** basándose en datos.
- No solo es que tengas **muchos datos** también es que puedas :: Responder ¿cómo? o ¿por qué?

### Bases de Datos
#Q 
- Son una colección :: Lógicamente coherente de datos.

## AppSheet
### AppSheet's DataBase
#Q 
- La columna **search** se encarga del :: Indexado.
- La columna **PII** significa... y se encarga del... :: Personally Identifiable Information, encriptado.
- El atributo **formula** es el :: Business Logic.

### Características de una Buena App
#Q 
- Una bena app debe considerar los siguientes aspectos :: Seguridad, funcionalidad, intuitiva, diseño, estabilidad y portabilidad.
- Que el app sea codeless no significa que esta será..., mas bien eso depende de... y de su... :: Buena, datos, los datos, calidad.
- A veces el área de business considera que el área de... es un... :: Seguridad stopper.

### Low/Less Code Applications
#Q 
- Low code apps son aquellas que si bien no vamos a **escribir** código, si lo tenemos que :: Entender.
- El gran logro de estas apps es que :: **Democratizaron** el desarrollo de aplicaciones.
- Pero, este tipo de aplicaciones son :: La generación pasada de aplicaciones.

## Artificial Intelligence
### Gráfica de Sabiduría
#Q 
- Los niveles son :: 1. Qué? Cuándo? 2. Cómo? 3. Por qué?

### Types of AI
#Q 
- Los dos tipos de de AI son :: Generativa y descriptiva.
- La AI **descriptiva** usa los datos que tenemos y extrae :: Metadata
- La AI **generativa** genera :: Productos y respuestas.

### Áreas en la que la AI Puede Mejorar
#Q 
- Cuales son :: 1. Ética 2. Cyberseguridad 3. Humanidad (empatía, tono, etc.)

## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Transformación Digital/Guía/Módulo 3.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```