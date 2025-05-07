---
tags:
---
Date: 2025-05-06 : 17:44
***
## Molina 
### DHCPv4
- Generalmente s pone en la red local. En el router gateway que le da servicio a una red interna.
#### Configuración

Para reto tener al menos:
1 DNS
1 DHCP
1 AAA

Extras
1 Email
1 HTTP

## Cloud
### Kubernetes (k8s)
#### Introducción
k8s es un software opensource.

Fue diseñado para vivir en un cluster. No para correr en una sola máquina, su core es el uso de contenedores.

k8s es el **capitan** que gestiona múltiples contenedores.

Docker no administra recursos.

Tareas que k8s hace por nuestros contenedores:
- Scheduling: Se encarga de determinar donde y cuando desplegar los contenedores.
- Ciclo de Vida y Salud: Constantemente le pregunta a contenedores si está vivo o no.
- Escalabilidad: Me faltan recursos?
- Identificación y rastreo: 
- Balanceo de Carga: Debe tener un balanceador de carga nativo.
- Volumenes de Almacenamiento: Que los datos se almacenen en un luggar.
- Logging y monitoreo: K8s nos da un lugar centralizado para ver donde pasan los problemas.
- Identidad y autenticación: Segmenta y regula quien puede hacer todo.

Hay que pensar a K8s como el **sistema operativo** del conjunto de contenedores.

#### Arquitectura
Nodo: Es el anfitrión que le da hospedaje a los contenedores.

Los kubelets son los que siguen las ordenes del panel de control

En el cluster se levanta un master con un apiserver.

#### Master Panel
Tiene cosas como:
- API Server
- etcd: 
- Scheduler
- Controller
- Addons

#### Pods
Es el componente principal al hablar de despliegue.

Es un grupo de **contenedores** y **volúmenes**.

K8s no entiende el concepto de contenedores, sino, pods.

El pod puede comunicarse, tiene volúmnes internos, etc. El contenedor no.

En un cluster de k8s puedo tener 1 o mas pods identicos corriendo.

Son como las instancias de los contenedores.

#### Servicios
Un servicio tiene varios pods, pero todos responden a un url por ejemplo. 

Por ello, los servicios deben tener un balanceador de cargas.

El servicio NO es replicable, ni escalable

