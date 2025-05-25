# Taller: Una forma más inteligente de trabajar en la CLI con Amazon Q Developer

Repositorio oficial del taller práctico impartido en el AWS User Group Panamá por **Sheyla Leacock**.

## 🎯 Objetivos
- Aprender a instalar y usar Amazon Q Developer CLI
- Aprovechar la inteligencia artificial para simplificar tareas en la terminal
- Automatizar flujos de trabajo comunes en AWS de forma eficiente e inteligente

## ✅ Requisitos Previos
- Tener una cuenta activa en AWS
- AWS CLI instalado y configurado (`aws configure`)
- Node.js y NPM instalados
- Instalar Amazon Q Developer CLI:

```bash
npm install -g @aws/amazon-q-cli
```

---

## 🧪 Laboratorios Prácticos

### 🔹 Laboratorio 1: S3 en acción

```bash
# Crear un bucket S3
amazonq suggest "Crear un bucket S3 llamado taller-q-cli"

# Subir un archivo local
amazonq suggest "Subir el archivo taller.txt al bucket S3 taller-q-cli"

# Listar objetos en el bucket
amazonq suggest "Listar todos los objetos en el bucket taller-q-cli"

# Validar permisos de IAM para acceso a S3
amazonq suggest "Validar que mi usuario IAM tenga permisos de acceso a S3 para leer y escribir en el bucket taller-q-cli"
```

---

### 🔹 Laboratorio 2: Seguridad con IAM y políticas

```bash
# Generar política personalizada para acceso a S3
amazonq suggest "Crear una política IAM que permita acceso solo de lectura a S3"

# Explicar acceso mínimo necesario
amazonq explain "Política JSON que permite s3:GetObject en todos los buckets del usuario"

# Asociar política a un rol
amazonq suggest "Asociar la política anterior a un nuevo rol llamado S3ReadOnlyRole"

# Interpretar errores de permisos
amazonq troubleshoot "aws iam attach-role-policy --role-name S3ReadOnlyRole --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess"
```

---

### 🔹 Laboratorio 3: Automatización EC2

```bash
# Generar script para lanzar una instancia EC2
amazonq suggest "Lanzar instancia EC2 t2.micro en us-east-1 con Amazon Linux"

# Agregar etiquetas a la instancia
amazonq suggest "Agregar etiquetas Name=taller, Env=demo a la instancia EC2"

# Adjuntar volúmenes adicionales
amazonq suggest "Adjuntar volumen EBS de 10GB a la instancia EC2"

# Asociar a un grupo de seguridad
amazonq suggest "Asociar la instancia EC2 a un grupo de seguridad que permita puerto 22 desde mi IP"

# Validar errores comunes en ejecución EC2
amazonq troubleshoot "aws ec2 run-instances ..."
```

---

### 🔹 Laboratorio 4: Redes con Amazon VPC

```bash
# Crear VPC con subred pública
amazonq suggest "Crear una VPC con CIDR 10.0.0.0/16 y una subred pública 10.0.1.0/24"

# Crear y asociar una tabla de rutas
amazonq suggest "Crear tabla de rutas para la VPC que permita salida a internet"

# Asociar un Internet Gateway
amazonq suggest "Crear un Internet Gateway y asociarlo a la VPC creada"

# Validar conectividad
amazonq suggest "Validar conectividad desde una instancia EC2 en la subred pública con ping a 8.8.8.8"
```

---

### 🔹 Laboratorio 5: Costos y facturación con Cost Explorer

```bash
# Activar Cost Explorer (una sola vez por cuenta)
amazonq suggest "Activar AWS Cost Explorer"

# Consultar costos por servicio del último mes
amazonq suggest "Mostrar costos por servicio del mes pasado usando AWS CLI"

# Visualizar uso por etiquetas
amazonq suggest "Ver costos agrupados por etiqueta 'Project'"

# Explicar cómo configurar presupuestos
amazonq suggest "Configurar un presupuesto mensual de $20 y generar alerta por email al superarlo"
```

---

## 👩‍💻 Autora
Sheyla Leacock — AWS User Group Leader | AWS Community Builder (Security)

## 📚 Recursos útiles
- [Amazon Q Developer CLI Documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html)
- [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/index.html)
- [AWS User Group Panamá](https://www.meetup.com/es-ES/aws-user-group-panama/)

---

> Este taller es parte del Meetup 54º de AWS UG Panamá. ¡Gracias por participar!