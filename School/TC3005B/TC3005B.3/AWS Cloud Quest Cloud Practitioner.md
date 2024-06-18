---
tags:
  - aws
  - cloud-computing
---
Date: 2024-06-12 : 14:27
***

## Amazon S3
#Q  #AOSR/60oto
- Full Name :: Simple Storage Service #AOSR/60oto/s/4q54
- It can store :: Any type of object. #AOSR/60oto/s/3duu
- Thats why it can be used as a :: Static Web Page Server. #AOSR/60oto/s/37b0


## Amazon EC2
#Q  #AOSR/2lhck
- Full Name :: Elastic Compute Cloud. #AOSR/2lhck/s/6ikr
- Se alquilan :: Máquinas virtuales. #AOSR/2lhck/s/z746
- Tiene una capacidad :: Elástica. #AOSR/2lhck/s/7pbk
- Se puede distribuir en diferentes :: Zonas de disponibilidad. #AOSR/2lhck/s/fnhl

### Escalamiento Vertical y Horizontal
#Q  #AOSR/357b7
- El **escalamiento vertical** es añadir :: Poder. #AOSR/357b7/s/4ge7
- El **escalamiento horizontal** es añadir :: Más nodos. #AOSR/357b7/s/7b3j

## Amazon RDS
#Q  #AOSR/6oiv9
- Full Name :: Relational Database Service. #AOSR/6oiv9/s/1bpj
- Zona de disponibilidad múltiple **(multi-AZ deployments)** aprovisiona y mantiene una :: Réplica de la DB en diferentes zonas de disponibilidad. #AOSR/6oiv9/s/5v2h
	- Proporcionan mayor :: Disponibilidad y durabilidad. #AOSR/6oiv9/s/3jfv
- También se pueden hacer réplicas de :: Lectura. #AOSR/6oiv9/s/4ebc
	- Mejoran el desempeño cuando solo se necesitan hacer :: Lecturas. #AOSR/6oiv9/s/aeik

## Amazon VPC
#Q  #AOSR/2f7rq
- Full name :: Virtual Private Cloud. #AOSR/2f7rq/s/74tt
- Provisiona una sección lógicamente aislada de la :: Nube. #AOSR/2f7rq/s/79uc
- Asigna números de IP :: Internos y externos. #AOSR/2f7rq/s/110o

## Amazon DynamoDB
#Q  #AOSR/3q635
- Base de datos de tipo :: No sql. #AOSR/3q635/s/6aiv

## Amazon EFS
#Q  #AOSR/td184
- Full name :: Amazon Elastic File System. #AOSR/td184/s/us3i
- Sirve para el almacenamiento de :: Archivos #AOSR/td184/s/4agn

## Amazon Auto Scaling Groups
#Q  #AOSR/5l3bc
- Es una colección de instancias :: EC2. #AOSR/5l3bc/s/6qvh
- Tiene 2 features que son :: Health check y scaling policies. #AOSR/5l3bc/s/6k1u
- Inicia lanzando las instancias :: Necesarias #AOSR/5l3bc/s/5q66
- Posteriormente si se necesita puede aumentar su capacidad de forma :: Manual o Automática. #AOSR/5l3bc/s/76nu

## Amazon ALB
#Q  #AOSR/1pttv
- Full Name :: Application Load Balancer. #AOSR/1pttv/s/1hob
- Es el único punto de contacto para :: Los clientes. #AOSR/1pttv/s/3e87
- Distribuye el tráfico a múltiples :: EC2's, iP's, zonas de avalability. #AOSR/1pttv/s/z615



## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "School/TC3005B/TC3005B.3/AWS Cloud Quest Cloud Practitioner",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```
