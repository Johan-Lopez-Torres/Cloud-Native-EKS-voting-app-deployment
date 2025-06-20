# Aplicación Web de Votación Nativa en la Nube con Kubernetes

Esta aplicación web nativa en la nube está construida con una combinación de tecnologías. Está diseñada para ser accesible a través de Internet, permitiendo a los usuarios votar por su lenguaje de programación favorito entre seis opciones: C#, Python, JavaScript, Go, Java y NodeJS.

## Stack Tecnológico

- **Frontend**: Desarrollado con React y JavaScript, proporciona una interfaz de usuario amigable y adaptable para emitir votos.
- **Backend y API**: Construido con Go (Golang), actúa como API para manejar solicitudes de votación. MongoDB es la base de datos utilizada, configurada como un replica set para alta disponibilidad y redundancia.

## Recursos de Kubernetes

- **Namespace**: Espacios de nombres para aislar componentes de la aplicación.
- **Secret**: Para almacenar credenciales y datos sensibles de forma segura.
- **Deployment**: Define la cantidad de réplicas de una app y cómo gestionarlas.
- **Service**: Proporciona acceso a la app y balanceo de carga interno.
- **StatefulSet**: Gestiona pods con estado como MongoDB, asegurando identidad única.
- **PersistentVolume y PersistentVolumeClaim**: Para almacenamiento persistente.

## Oportunidades de Aprendizaje

1. **Contenerización**: Uso de Docker para empaquetar apps.
2. **Orquestación con Kubernetes**: Gestión de apps en producción.
3. **Microservicios**: Frontend y backend desacoplados y escalables.
4. **Replica Set de MongoDB**: Redundancia y disponibilidad.
5. **Seguridad con Secrets**: Buenas prácticas de protección de datos.
6. **Aplicaciones con Estado**: Gestión dentro de Kubernetes.
7. **Almacenamiento Persistente**: Cómo funciona en Kubernetes.

---

## **Pasos para Desplegar**

### Crear clúster EKS con NodeGroup (2 nodos t2.medium)
### Crear instancia EC2 t2.micro (opcional)

### Rol IAM para EC2
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": [
      "eks:DescribeCluster",
      "eks:ListClusters",
      "eks:DescribeNodegroup",
      "eks:ListNodegroups",
      "eks:ListUpdates",
      "eks:AccessKubernetesApi"
    ],
    "Resource": "*"
  }]
}
