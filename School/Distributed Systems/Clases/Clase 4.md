---
tags:
---
Date: 2025-04-01 : 16:21
***
## Módulo 1 (Molina)
### VLAN
#### Introducción
- Para que una compu se hable con otra debe estar en **el mismo segmento de red**.
- Para que se comunicaran usando un switch, este debería estar en el mismo lugar. Pero si están en diferentes pisos. Qué se hace? Ponemos un switch en cada piso y un switch de distribución.
- Nos permite que tengamos una **estructura física** pero con **estructura lógica** diferente.
- Las **VLAN's** se crearon para **disminuir** el re-cableado.

#### Definiciones de Dispositivos
**Segmentación de Red:** 

**Seguridad:** Evita que puedas ver dispositivos de otra vlan.

**Reduce Costos:** No necesitas recablear.

#### Tipos de VLAN
Al comprar un switch, todos los puertos están en **la misma VLAN** esta es la **VLAN nativa predeteriminda**. Siempre esta presente.

**VLAN's de Datos:** Todos los departamentos que tenemos.

**VLAN's de Administración:** Telnet o SSH solo se podrán hacer por esta VLAN.

**VLAN de Voz:** Alta prioridad de QoS.

#### Troncales de VLAN
Cuando llega al gateway del switch un paquete de una VLAN, lo debemos poder distinguir con otro paquete de otra VLAN. Antes, por VLAN se ponían cables. Pero esto se cambió.

En **un mismo cable** metemos tramas de diferentes VLANS y para eso se usa el **protocolo troncal**. Se llama **IEEE 802.1Q**.

#### Protocolo IEEE 802.1Q
Lo que hace es modificar la trama.

Le mete un **tag** que son **4 octetos de mas**. Pone protocolo. Identificador de VLAN.  Pero esta modificación, solo se ve en los switches donde hay troncales

Sale (switch 1) con el tag -> Llega a switch de distribución -> Llega a swicth de acceso final y ahí se le quita el tag.

**Tráfico nativo:** Se pone hub y a el se le conectan computadoras. Si no queremos que se conviertan en tramas vlan truncales, entonces son **tramas nativas**. Al llegar al truncal, no se encapsula.

#### Rangos de VLAN
Normalmente se numeran de: **1 - 1005**. 

#### Configuración
La VLAN no es algo centralizado, por lo que en todos los switches hay que ponerlo.

Seguridad: `switch mode access` obliga a que lo único que se pueda conectar a ese puerto es un dispositivo terminal.

Definir que vlan: Normalmente cada puerto tiene solo un vlan. Es lo más común. Para definir eso: `sss` 

## Módulo Emmanuel
### Modalidades de Servicio
Quién es el responsable? En cada una cambia esa respuesta:

**IaaS:** Nosotros somos responsables de crear cimientos sólidos. Esto, nos da mas libertades. Se cobra por tiempo y recursos. Es difícil predecir, pero menos que el SaaS.

**PaaS:** Por ejemplo firebase. No podemos decirle que sistema operativo, que cpu, que ram. De eso se encarga el proveedor. Esa es una ventaja, pero a la vez una desventaja porque perdemos libertad. 

**SaaS:** Un servicio que usamos. Ejemplo: Google Maps, Netflix. Se cobra por licencia, suscripción o llamada. No es tan sencillo predecir.

### IaaS
Hardware como servicios

Generalmente es **pago por uso**. Renta por aprovisionamiento.

Es más fácil vender un CPU solo para ti que un Google Maps solo para ti.

### PaaS
Generalmente es **pago por uso**.

Limitaciones puestas por el proveedor. 

Administrado por el proveedor.

### SaaS
Apis, consumo web

Pago por uso

Son como una caja negra.

Completamente administrado por el proveedor.

### FaaS
FaaS: Function as a Service.

Serverless: No es que no haya servers. Nosotors no tenemos que **configurar** o **mantener esos servidores**.

FaaS: El proveedor nos dice que lo único de lo que nos tenemos que preocupar es el código.

Ejemplo: Lamda es un FaaS.

### DaaS
DaaS: Database as a Service

Es más cercano a un IaaS que a un PaaS. Pero nos da cierta libertad.

### STaaS
STaaS: Storage as a Service

Tiene dos complejidades:
1. Cantidad de almacenamiento en volumen.
2. Consulta y escritura.

Estas soluciones son **muy baratas**.

### Modelo de Responsabilidad Compartida
Este modelo sale a relucir cuando empiezan a haber **problemas**.

Hay dos caras de montarnos en un probedoor
1. Seguridad **DE** la nube: Lo que vemos cuando todo va bien. Lo que nos gusta. Lo que ya existe. Es muy difícil que falle. Tiene muy buena infraestructura y niveles de calidad.
2. Seguridad **EN** la nube: Perdemos libertades porque delegamos responsabilidad al proveedor. Esto generalmente está oculto. 


### Geográficamente Replicado
Regiones: En algún punto específica.

Diferencia entre región y zona: Zona es una parte de una región. La razón de la existencia de esto es redundancia. No hay un data center, hay varios y ellos son totalmente autónomos, lo que me dice que si se cae una zona, es probable que las otras siguen vivas.

Cuando depende tener diferentes regiones: Cuando tengo usuarios en diferentes regiones.

Cada centro de datos esta sujeto a leyes diferentes: Según país o estado.

### Data Center vs. Site
La principal diferencia es: La calidad.

### Y el cifrado?

- Reposo: Almacenado, escrito.
- En tránsito: Se envía información a través de red.
- En uso: RAM. 

Al igual, el cifrado es una **responsabilidad compratida**.

### Site o Data Center
- Data Center: Requisitos muy estrictos para operar. **ALTA DISPONIBILIDAD**.

### Disponibilidad es Seguridad
La **disponibilidad** nos da **confianza**.

La **latencia** es el tiempo que se tarda en contestar.

Si hay mala **latencia**, no hay disponibilidad.

**Latencia** es tiempo. Desde que envias hasta que regresa.

**Ancho de banda:** Cantidad de info que pasa por red en un tiempo determinado. Eso en realidad no es **ancho de banda**. Eso es **troughput**. 

**Ancho de Banda** Es la capacidad de mi canal para eviar información. La cadntidad de carriles de una carretera. Se relaciona mucho con el **troughput**.

Actualmente el ancho de banda siempre va a fluctuar. Porque pasa por muchas partes. Access points, cableados, etc.

### VPC
Significa: Virtual Private Cloud.

Es una red privada virtual.

Nos da una red no expuesta a internet. Todo lo que pasa ahí adentro, esta resguardado.

Para tener acceso a esto, se nos da una ip pública.

### Firewall
Generalmente vienen como un **servicio implícito** de la VPC.

### Load Balancer
Dejar entrar tráfico. 

Load Balancer: Se orienta al tráfico entrante. Sirven para distribuir el tráfico de manera eficiente.

Hay dos:
- Externos: Ip pública.
- Interno: 

Componentes de red que son **parte fundamental** de la escalabilidad. Hacen que varias máquinas trabajen como una misma.

Pueden ser **directos** o **proxificados**:
- Proxy: Es una especie de representante para salir a internet. Un load balancer así es para ambos lados. Nos sirve como detector de metales. 
- Directo: Un buzón

### NAT
NAT: Varias IP's se traducen a una misma.

Cuando salimos a internet, nuestra IP pública esta nateada, porque no ven nuestra ip privada.

Es una medida de seguridad.

### VPN
Van a través de canal público, pero se encapsulan en un tunel el cual está cifrado.

Dos tipos de VPN:
- Destinada a que dispositivos puedan acceder a nube:
- Site to Site: Servicios o recursos de un sitio se conecten con servicios o recursos de otros. Esto se hace con las **VPN Gateways**. Lo primero que hacen es *enrutar*. Luego Border Gateway Protocol (BGP) ayuda a los enrutadores a armar una tabla de ruteo. Esta es la forma mas barata de conectar sitios físicos com sitios cloud.

### Interconexión dedidaca
**MUY CARO**

Mayor **troughput** porque no dependes del ancho de banda de una VPN.

### API Gateway





