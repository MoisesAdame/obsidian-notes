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

**IaaS:** Nosotros somos responsables de crear cimientos sólidos. Esto, nos da mas libertades. Se cobra por tiempo y recursos.

**PaaS:** Por ejemplo firebase. No podemos decirle que sistema operativo, que cpu, que ram. De eso se encarga el proveedor. Esa es una ventaja, pero a la vez una desventaja porque perdemos libertad. 

**SaaS:** Un servicio que usamos. Ejemplo: Google Maps, Netflix. Se cobra por licencia, suscripción o llamada.







