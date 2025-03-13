# **AquaSenseCloud**

## Descripción
AquaSenseCloud es una solución basada en la nube para la recopilación, procesamiento y almacenamiento de métricas de temperatura. Utiliza tecnologías de AWS como Lambda, DynamoDB y Fargate para ofrecer una infraestructura escalable y tolerante a fallos.

## Arquitectura
El sistema se compone de los siguientes módulos:

### 1. Pipeline de Datos
- Obtención de métricas de temperatura.
- Procesamiento y combinación de datos.
- Almacenamiento en **AWS DynamoDB**.
- Notificación por **AWS SNS**.

### 2. Servidor Flask
- Conexión con **DynamoDB**.
- Exposición de rutas API.
- Consultas eficientes a la base de datos.
- Implementación como imagen Docker y despliegue en **AWS ECR**.

### 3. Infraestructura
- **Infraestructura de Red**: VPC, Subredes Públicas, Internet Gateway.
- **Clúster y Servicios**: Instancias **Fargate**, tareas y escalabilidad automática.
- **Balanceador de Carga**: Agente de escucha y grupos de destino.
- **Grupos de Seguridad**: Para el balanceador y las tareas.

### 4. Escalabilidad y Tolerancia a Fallos
- **DynamoDB** con políticas de autoescalado.
- **Despliegue en múltiples zonas de disponibilidad** para alta disponibilidad.
- **Replicación de instancias** y balanceo de carga para resiliencia.

## Tecnologías Utilizadas
- **AWS Lambda**
- **AWS DynamoDB**
- **AWS SNS**
- **AWS Fargate**
- **AWS ECR**
- **Flask** (Servidor API)

## Despliegue
1. Construir la imagen Docker del servidor Flask y subirla a AWS ECR.
2. Configurar el clúster Fargate y desplegar las tareas.
3. Configurar políticas de escalabilidad en DynamoDB.
4. Verificar la conectividad con el balanceador de carga.

## Autores
- **Rubén Gil Martínez**
- **Guillermo López Pérez**