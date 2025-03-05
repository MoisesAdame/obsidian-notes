---
tags:
---
Date: 2025-02-24 : 10:32
***
## Semana 1
### Tipos de Desarrollo
#Q  #AOSR/231il
- Los **tres tipos** de desarrollo son :: Tradicional (code), low code y no code #AOSR/231il/s/3bnd

### No Code Development
#Q  #AOSR/s7mj0
- Es un tipo de programación 100% :: Visual. #AOSR/s7mj0/s/3vhf
- Todos los componentes los ponemos usando :: Drag and drop. #AOSR/s7mj0/s/3rhr
- Aplicaciones que podemos hacer :: Dashboards, prototipos, process automation, etc. #AOSR/s7mj0/s/oiul
- La filosofía de estas herramientas es que parten de :: Los datos. #AOSR/s7mj0/s/24b4
- No code se beneficia de la experiencia de usuario generada por el :: Low-code. #AOSR/s7mj0/s/6p68

### Google AppSheet
#Q  #AOSR/9hn63
- Es una plataforma de desarrollo de :: Aplicaciones no-code. #AOSR/9hn63/s/4k0d

#### Beneficios
#Q #AOSR/6471a
- Es **fácil de usar** ya que no requiere :: Experiencia de programación #AOSR/6471a/s/3nli
- Es **rápido y eficiente** ya que nos deja hacer aplicaciones en una fracción de lo que las :: Aplicaciones normales. #AOSR/6471a/s/513s
- Es **barata** ya que no necesitas contratar a :: Un equipo de desarrollo. #AOSR/6471a/s/1mo0

#### Fuente de Datos
#Q  #AOSR/158qg
- Los 4 tipos de **fuentes de datos** de AppSheet son :: Nativo, spreadsheets, bases de datos y otros. #AOSR/158qg/s/31qk
- Nativo son :: AppSheet databases. #AOSR/158qg/s/4vl8
- Spreadsheets son :: Excel o GoogleSheets #AOSR/158qg/s/3dqq
- Bases de datos algunas son :: AWS DynamoDB, MySQL, Oracle, etc. #AOSR/158qg/s/2eb8
- Otros son :: Dropbox, google calendar, forms, etc. #AOSR/158qg/s/4kd4

#### Tipos de Views
#Q 
- **Table** muestra los datos de forma..., similar a una... :: Tabular, hoja de cálculo.
- **Detail** presenta toda la información detallada de un :: Único registro.
- **Formulario** nos permite a los datos :: Editarlos.
- **Tarjeta** muestra... y... en un único elemento visual :: Contenido, acciones.
- **Mapa** sirve para visualizar datos :: Geoespaciales.
- **Gallery** presenta elementos visuales en forma de galería enfocándose en :: Imágenes.
- **Calendario** organiza la información basada en :: Fechas
- El **dashboard** combina :: Múltiples vistas en una.
- El **deck o tarjeta de presentación** presenta datos en un formato de :: Tarjetas apiladas.
- **Onboarding** sirve para guiar a :: Nuevos usuarios.
- **Gráfico o Char** representa los datos de forma :: Visual.

#### Actions
#Q 
- Es una operación... :: Definida
- Les permiten a los usuarios hacer cosas como... :: Modificar datos, navegar entre vistas, etc.
- Generalmente se representan como :: Botones.
- Hay 3 tipos de actions y son :: De aplicación, de datos y externos.

#### Automations
#Q 
- Son un conjunto de herramientas que les permite a los usuarios optimizar... sin intervención... :: Procesos, manual.
- Usa 4 elementos que son :: Bots, eventos, procesos y tareas.
- Los **bots** son las entidades que :: Automatizan tareas.
- Los **eventos o triggers** son las condiciones que :: Activan a un bot.
- Hay 3 tipos de triggers que son :: Basados en datos, programados y externos.
- Los **procesos** son la lógica de la :: Automatización.
- Usualmente los procesos se definen en... y pueden tener... :: Pasos, condiciones.

## Introduction to Google AppSheet
### Overview
#Q  #AOSR/2l8n7
- El concepto de App empieza a existir en el año..., cuando se lanza el... :: 2007, iPhone #AOSR/2l8n7/s/7cs1
- Quién puede usar Google AppSheet :: Citizen Developers (Quien Sea) #AOSR/2l8n7/s/4bvo
- Tipos de trabajadores que pueden usar no-code apps :: End users, process owners (PM y Devs) y decision makers (ejecutivos). #AOSR/2l8n7/s/2j67

### Getting Started
#Q  #AOSR/25t2k
- Para crear tu app lo primero que debes hacer es :: Preparar tu Google Sheets. #AOSR/25t2k/s/r18g
- Cada hoja de tu google sheets es una :: View. #AOSR/25t2k/s/286d
- Las **actions** son los botones que puedes :: Customizar. #AOSR/25t2k/s/1j19
- La forma más simple de **probar** tu app es usando :: App Preview. #AOSR/25t2k/s/1im8

### Leveraging Data
#Q  #AOSR/5okcr
- Cada row debe tener un **key** que es un :: Identificador único. #AOSR/5okcr/s/49ku
- Cada columna podemos elegir que sea o no **label** es decir que se :: Muestre o no su nombre. #AOSR/5okcr/s/3mk5
- Las **virtual columns** son las columnas que al inicio tienen :: Un guión bajo (\_) #AOSR/5okcr/s/5dgl
- Las **imágenes** se almacenan como :: URL o como PATH. #AOSR/5okcr/s/1ngh
- Las **ref** nos sirven para relacionar :: Diferentes hojas o tablas. #AOSR/5okcr/s/2eoh

### User Experience
#Q  #AOSR/7mddq
- Hay **tres tipos** de view que son :: Primary, system y reference. #AOSR/7mddq/s/7tj3
- **Primary views** son las que se pueden acceder :: Desde el menú inferior. #AOSR/7mddq/s/3qeh
- **System views** son las que se generan :: De forma automática. #AOSR/7mddq/s/5juu
- **Reference views** son las que salen al :: Indagar en datos. #AOSR/7mddq/s/2cnn
- Las **format rules** nos sirven para dar cierto formato dada :: Cierta condición. #AOSR/7mddq/s/z610

### Publishing Your App
#Q  #AOSR/4rud5
- Para deployear una app se necesitan seguir **4 pasos** :: 1) Hacer deployment check 2) Resolver problemas 3) Deployear app 4) Testear app como usuario. #AOSR/4rud5/s/2aut
- Los dos **tipos de deployment** son :: Instantáneo y tradicional. #AOSR/4rud5/s/4mmu
- El **deployment instantáneo** consiste en descargar la app en el :: AppSheet Host. #AOSR/4rud5/s/2sni
- El **deployment tradicional** sirve si queremos que la app se consuma a..., para ello hay que crear un..., el cual se sube a la... :: Gran escala, white label, tienda de aplicaciones. #AOSR/4rud5/s/3hf7





## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/Transformación Digital/Guía/Módulo 2.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```