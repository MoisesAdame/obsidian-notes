---
tags:
  - ceneval
  - software-engineering
  - requirements
---
Date: 2025-02-10 : 14:34
***
## ¿Qué son?
- Es lo que quiere el cliente que haga su software.
- Debemos **reducir** la brecha entre lo que **entendemos que quiere el cliente** y lo que **realmente quiere**.

>[!NOTE]
>**"LOS REQUERIMIENTOS SON UNA ESPECIFICACIÓN DE LO QUE DEBERÍA SER IMPLEMENTADO"**
>**"ES ALGO QUE DIRIGE LAS DECISIONES DE DISEÑO".**

## Tipos de Información de los Requerimientos
- Requerimiento de Negocio: Objetivo de alto nivel (nada de programación).
- Regla de Negocio: Políticas del negocio, no es requerimiento, pero es origen de ellos.
- Limitación: Restricciones para el desarrollador en el diseño (recursos, reglas, etc.)
- Requerimiento de Interfaz Externa: Conexión entre sistema y otro usuario, sistema o dispositivo.
- Funcionalidad: Lo que tiene que hacer sistema para resolver problemas.
- Requerimientos Funcionales: Lo que hace el sistema
- Requerimientos No Funcionales: Como lo va a hacer (performance, estilo, )
- Atributo de Calidad: Se dividen en muchos (usabilidad, seguridad, performance, etc.). Son requerimientos no funcionales que describen características de desempeño del sistema.
- Requerimiento de Sistema: Minimo 6 GB de RAM, tal sistema operativo, etc.
- Requermientos de Usuario: Metas que el usuario pueda realizar.

### Requerimientos No Funcionales
- Escalabilidad: Que tan fácil se puede construir sobre el sw.
- Mantenibilidad: Que tan fácil es arreglarlo.
- Disponibilidad: Confianza.
- Seguridad: No solo es que no sea hackeable.

Se dividen en tres:
- Producto: Los más familiares para nosotros. Seguridad, performance, etc.
- Organización: Como se hacen las cosas en la organización (todo a mano, con exceles, etc.). Generalmente buscan automatizar procesos.
- Externos: Cosas como leyes o aspectos éticos

## ¿Para Qué Se Hace Control de Software?
- Utilizar estadísticas de proyectos previos, para planear mejor el siguiente proyecto.
- Estimar bien proyectos y costos.

### Métricas
- Rapidez.
- Tamaño: Cuánto pesa el proyecto (GBs). Costo de la infraestructura en cloud.
- Facilidad de Uso: Usabilidad.
- Fiabilidad: Ver los errores generados y evitarlos
- Robustez: Que tal rápido me recupero de una falla.
- Portabilidad: En cuantos dispositivos diferentes puede funcionar tu plataforma.

>[!WARNING]
>Leer Resumen [Calidad Interna vs Calidad Externa](https://experiencia21.tec.mx/courses/551022/files/217319046?wrap=1)
>Ver video de [User Stories]()

## Técnicas de Elicitación de Requeriminetos
### Entrevistas
Es como con un doctor, hay que tocar y entender los problemas para poder resolverlos. No hablar con tecnicismos, ni ser totalmente informal. Enaltecer tus fortalezas, no las debilidades del otro, no ser arrogante. Ser puntual. Hay que ser un poco **camaleones** a la hora de bajar requerimientos.

La mayor parte de los clientes son como la novia al cenar, "No sé".

Recopilar la mayor cantidad de datos posibles.

### Casos de Uso
Los vimos como UML, pero en metodologías ágiles se ven como Historias de Usario.

Pasos:
1. Identificar alcance de sistema
2. LLuvia de ideas y actores principales
3. Enumerar las metas de usuarios
4. Revisar caso de uso.
5. Expandirlos (uno por uno)
6. Describir el escenario de éxito **Happy Path** (que nada se salga de lo esperado.)
7. Analizar casos alternativos (cosas que no previste)
8. Extraer sub-casos de uso

