Procedimientos Operativos CRIPTO TRACK — TRL7

Procedimientos operativos del prototipo TRAC / CRIPTO TRACK

Expediente CPP3/Reto4 — Etapa 3

---

# ÍNDICE

1. [INTRODUCCIÓN](#1-introducción)
   - 1.1 [Objetivo y alcance](#11-objetivo-y-alcance)
   - 1.2 [Términos y acrónimos](#12-términos-y-acrónimos)
   - 1.3 [Contexto arquitectónico y componentes](#13-contexto-arquitectónico-y-componentes)
2. [GOBERNANZA OPERATIVA](#2-gobernanza-operativa)
   - 2.1 [Modelo RACI](#21-modelo-raci)
   - 2.2 [Gestión del cambio con Azure DevOps](#22-gestión-del-cambio-con-azure-devops)
   - 2.3 [Trazabilidad y auditoría](#23-trazabilidad-y-auditoría)
3. [ENTORNOS](#3-entornos)
   - 3.1 [Entorno TRL7 operacional (AWS)](#31-entorno-trl7-operacional-aws)
   - 3.2 [Cuentas Cloud y estrategia de red](#32-cuentas-cloud-y-estrategia-de-red)
   - 3.3 [Gestión de secretos y claves (KMS / Secrets Manager)](#33-gestión-de-secretos-y-claves-kms--secrets-manager)
   - 3.4 [Futuros entornos (recomendación)](#34-futuros-entornos-recomendación)
4. [PROCEDIMIENTOS DE INSTALACIÓN Y DESPLIEGUE](#4-procedimientos-de-instalación-y-despliegue)
   - 4.1 [Pre-requisitos y controles previos](#41-pre-requisitos-y-controles-previos)
   - 4.2 [Aprovisionamiento de infraestructura base (IaC / Terraform)](#42-aprovisionamiento-de-infraestructura-base-iac--terraform)
   - 4.3 [IAM y permisos mínimos](#43-iam-y-permisos-mínimos)
   - 4.4 [Gestión de secrets y variables de entorno](#44-gestión-de-secrets-y-variables-de-entorno)
   - 4.5 [Despliegue de módulos (pipelines CI/CD — Azure DevOps)](#45-despliegue-de-módulos-pipelines-cicd--azure-devops)
   - 4.6 [Checklist de instalación](#46-checklist-de-instalación)
5. [VERIFICACIONES POST-DESPLIEGUE Y SMOKE TEST](#5-verificaciones-post-despliegue-y-smoke-test)
   - 5.1 [Smoke test alineado con PE3-0001](#51-smoke-test-alineado-con-pe3-0001)
   - 5.2 [Checklist post-despliegue](#52-checklist-post-despliegue)
6. [OPERACIÓN DIARIA](#6-operación-diaria)
   - 6.1 [Checklist diario](#61-checklist-diario)
   - 6.2 [Rutinas periódicas (semanal / mensual)](#62-rutinas-periódicas-semanal--mensual)
7. [MONITORIZACIÓN Y ALERTAS](#7-monitorización-y-alertas)
   - 7.1 [Infraestructura de monitorización](#71-infraestructura-de-monitorización)
   - 7.2 [PKIs y umbrales operativos](#72-pkis-y-umbrales-operativos)
   - 7.3 [Dashboards](#73-dashboards)
8. [RUNBOOKS — RESOLUCIÓN DE INCIDENCIAS](#8-runbooks--resolución-de-incidencias)
   - 8.1 [Incidencia: fallo o retraso en ingesta BTC/ETH/Polygon](#81-incidencia-fallo-o-retraso-en-ingesta-btcethpolygon)
   - 8.2 [Incidencia: fallo en módulo de enriquecimiento (Airflow/Neo4j)](#82-incidencia-fallo-en-módulo-de-enriquecimiento-airflowneo4j)
   - 8.3 [Incidencia: degradación o fallo del módulo IA](#83-incidencia-degradación-o-fallo-del-módulo-ia)
   - 8.4 [Incidencia: fallo en motor de reglas / gestor de eventos](#84-incidencia-fallo-en-motor-de-reglas--gestor-de-eventos)
   - 8.5 [Incidencia: degradación de recursos EC2 (CPU/RAM/disco)](#85-incidencia-degradación-de-recursos-ec2-cpuramdisco)
   - 8.6 [Incidencia: fallo de conectividad a fuentes externas](#86-incidencia-fallo-de-conectividad-a-fuentes-externas)
   - 8.7 [Procedimiento de backup y restore](#87-procedimiento-de-backup-y-restore)
9. [BACKUPS, RTO, RPO Y CONTINUIDAD](#9-backups-rto-rpo-y-continuidad)
10. [EVIDENCIAS TRL7](#10-evidencias-trl7)
11. [CONFIGURACIONES DE SEGURIDAD](#11-configuraciones-de-seguridad)
12. [REFERENCIAS](#12-referencias)
13. [ANEXOS](#13-anexos)
    - 13.1 [Histórico de modificaciones](#131-histórico-de-modificaciones)
    - 13.2 [Glosario](#132-glosario)

---

# 1. INTRODUCCIÓN

## 1.1 Objetivo y alcance

El presente documento recoge los procedimientos operativos del prototipo **TRAC / CRIPTO TRACK** (CPP3 — Reto 4, Etapa 3) en su nivel de madurez tecnológica **TRL7** (Technology Readiness Level 7): prototipo demostrado en entorno operacional que simula condiciones reales de producción.

El objetivo es proporcionar al equipo operativo un conjunto completo de instrucciones accionables para:

- Desplegar, verificar y operar el sistema TRAC en el entorno AWS designado.
- Gestionar el ciclo de vida del software y la infraestructura mediante **Azure DevOps**.
- Monitorizar el comportamiento del sistema frente a los PKIs y umbrales definidos.
- Resolver las incidencias operativas más frecuentes.
- Generar y custodiar las evidencias requeridas para la demostración TRL7.

**Alcance TRL7.** El entorno operacional del prototipo está desplegado en AWS y gestiona el flujo completo: ingesta de blockchains (Bitcoin, Ethereum, Polygon) → Datalake → Enriquecimiento → Módulo IA → Motor de Reglas/Gestor de Eventos → Frontal Web. Todas las operaciones de este documento aplican a este entorno de demostración operacional. No se describen entornos de preproducción o producción plena, ya que están fuera del alcance actual (véase sección 3.4 para recomendaciones futuras).

**Repositorio Azure DevOps:** `https://dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4`

## 1.2 Términos y acrónimos

| Acrónimo / Término | Descripción |
|---|---|
| TRAC | Sistema de TRAzabilidad de Criptoactivos — nombre del prototipo |
| CRIPTO TRACK | Nombre comercial / de proyecto del prototipo TRAC |
| TRL7 | Technology Readiness Level 7: prototipo demostrado en entorno operacional |
| AWS | Amazon Web Services — proveedor cloud del entorno operacional |
| ADO | Azure DevOps — plataforma de gestión de código, tickets y CI/CD |
| IaC | Infrastructure as Code |
| CI/CD | Continuous Integration / Continuous Delivery |
| EC2 | Amazon Elastic Compute Cloud |
| VPC | Virtual Private Cloud |
| SG | Security Group |
| KMS | AWS Key Management Service |
| IAM | Identity and Access Management |
| ETL | Extract, Transform, Load |
| IA | Inteligencia Artificial |
| PKI | Indicador clave de rendimiento del prototipo (nomenclatura propia del proyecto TRAC; no confundir con *Public Key Infrastructure*). Identificados como PKI-0001, PKI-0002, etc. en el documento de PKIs y Rendimiento |
| RTO | Recovery Time Objective — tiempo máximo de recuperación |
| RPO | Recovery Point Objective — máxima pérdida de datos tolerable |
| BTC | Bitcoin |
| ETH | Ethereum |
| POL | Polygon |
| PE3-xxxx | Caso de prueba de la Etapa 3 (Plan de Validación ENT-0009) |
| RACI | Responsible, Accountable, Consulted, Informed |
| ADO Boards | Módulo de gestión de tareas e incidencias de Azure DevOps |
| ADO Pipelines | Módulo de CI/CD de Azure DevOps |
| ADO Repos | Módulo de repositorios Git de Azure DevOps |

## 1.3 Contexto arquitectónico y componentes

El prototipo TRAC está diseñado para el seguimiento y detección de transacciones de criptoactivos vinculadas a actividades ilícitas (ransomware y campañas de cibercrimen), utilizando técnicas de inteligencia artificial. La arquitectura se organiza en los siguientes módulos funcionales, todos desplegados en instancias EC2 de AWS sobre una VPC privada:

| Módulo | Función | Infraestructura AWS | Tecnologías principales |
|---|---|---|---|
| **Ingesta BTC** | Sincronización y extracción de datos de la blockchain de Bitcoin | EC2 c6a.xlarge (4 vCPU, 8 GB) | Bitcoin Core, Ubuntu 22.04 |
| **Ingesta ETH** | Sincronización y extracción de datos de la blockchain de Ethereum | EC2 c6a.xlarge (4 vCPU, 8 GB) | Reth (ejecución) + Nimbus (consenso), Ubuntu 22.04 |
| **Ingesta Polygon** | Extracción de datos de Polygon vía API | EC2 c6a.xlarge (4 vCPU, 8 GB) | API Alchemy, Ubuntu 22.04 |
| **Datalake** | Almacenamiento y acceso a datos de blockchains y fuentes off-chain | EC2 / RDS | PostgreSQL, Neo4j, API REST |
| **Enriquecimiento** | Ingesta off-chain, correlación de fuentes externas, orquestación ETL | EC2 m6a.xlarge (4 vCPU, 16 GB) | Apache Airflow 2.9.1, Neo4j latest, Docker |
| **Módulo IA (ETL+AI)** | Predicción de peligrosidad de carteras mediante modelos ML | EC2 t3a.xlarge (2 vCPU, 4 GB) | Docker, modelos propietarios |
| **Motor de Reglas / Gestor de Eventos** | Transformación de datos en alertas mediante reglas de negocio | EC2 m6a.2xlarge (8 vCPU, 32 GB) | Apache Kafka 4.0, Apache Flink 2.0, Redis 7, OpenSearch 3.0, Docker |
| **Frontal Web** | Visualización, gestión de wallets, alertas e incidentes | EC2 / contenedor | Aplicación web (CITRA) |

> **Referencia arquitectónica completa:** `CCP3_R4_TRAC_Documento de Arquitectura del prototipo.md`

El flujo de datos de extremo a extremo es:

```
Blockchains (BTC / ETH / POL)
        │
        ▼
   Módulos de Ingesta (EC2 × 3)
        │  datos in-chain
        ▼
     Datalake (PostgreSQL + Neo4j + API)
        │                    ▲
        │              Enriquecimiento
        │         (Airflow + fuentes off-chain)
        ▼
   Módulo IA (predicciones de riesgo ~ cada hora)
        │
        ▼
Motor de Reglas / Gestor de Eventos
(Kafka → Flink → Redis / OpenSearch → alertas)
        │
        ▼
     Frontal Web (operadores / analistas)
```

La gestión del código fuente, versionado, ticketing y pipelines de CI/CD se centraliza en **Azure DevOps** (`https://dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4`).

---

# 2. GOBERNANZA OPERATIVA

## 2.1 Modelo RACI

La siguiente tabla define las responsabilidades operativas para las actividades clave del entorno TRL7:

| Actividad / Proceso | Equipo Infraestructura (ECC) | Equipo Desarrollo / IA (ECC/AirInstitute) | Equipo Ingeniería (Deloitte) | Equipo Evaluador / INCIBE |
|---|---|---|---|---|
| Aprovisionamiento y configuración AWS | R/A | C | C | I |
| Despliegue de releases (ADO Pipelines) | R | A | C | I |
| Gestión de secretos (KMS/Secrets Manager) | R/A | I | C | I |
| Monitorización y respuesta a alertas | R | C | I | I |
| Gestión del cambio (RFC en ADO Boards) | A | R | C | I |
| Resolución de incidencias P1/P2 | R/A | C | C | I |
| Actualización de modelos IA | C | R/A | I | I |
| Validación de evidencias TRL7 | C | C | A | R |
| Gestión de backups y restore | R/A | I | C | I |
| Revisión de PKIs y rendimiento | R | R | C | I |

R: Responsable · A: Aprobador · C: Consultado · I: Informado

## 2.2 Gestión del cambio con Azure DevOps

Todo cambio en código, infraestructura o configuración del entorno TRL7 debe seguir el siguiente ciclo gestionado en **Azure DevOps**:

1. **Creación de Work Item en ADO Boards:** el solicitante crea un ítem de tipo *User Story* o *Bug* con descripción, impacto estimado y módulos afectados.
2. **Revisión y aprobación:** el Equipo de Infraestructura y el Aprobador técnico evalúan el impacto. Para cambios que afecten al entorno operacional, se requiere aprobación explícita antes de ejecutar.
3. **Rama de trabajo en ADO Repos:** los cambios de código se desarrollan en una rama dedicada (`feature/<id>` o `fix/<id>`). Se prohíben commits directos a `main`.
4. **Pull Request y revisión de código:** apertura de PR con al menos un revisor designado. Las políticas de branch protegen `main` con CI obligatorio.
5. **Pipeline CI/CD (ADO Pipelines):** el pipeline automático ejecuta tests, análisis de seguridad y construcción de imágenes Docker. Solo pasa a despliegue si todos los gates están en verde.
6. **Ventana de cambio:** los cambios que afectan a componentes de ingesta o al motor de reglas se programan preferentemente fuera de ventanas de sincronización activa (ej. fuera de bloques de alta actividad BTC). La ventana se comunica a todas las partes con al menos 24 h de antelación.
7. **Despliegue y verificación:** se ejecuta el smoke test (sección 5) y se validan los PKIs durante al menos 30 minutos tras el despliegue.
8. **Cierre del Work Item:** con evidencia del resultado (log de pipeline, captura de dashboard). En caso de incidencia se activa el rollback (sección 8).

## 2.3 Trazabilidad y auditoría

- Todos los cambios de infraestructura (Terraform) se versionan en ADO Repos y cada `terraform apply` genera un registro en el pipeline.
- Los logs de AWS CloudTrail registran todas las llamadas a la API de AWS (creación/modificación de recursos, accesos a KMS, cambios en IAM).
- Los logs de aplicación y sistema se centralizan en **Amazon CloudWatch Logs** con retención configurada por módulo.
- Las ejecuciones de pipelines en ADO generan artefactos y logs que constituyen evidencias de trazabilidad del despliegue.
- Las incidencias se gestionan como Work Items en ADO Boards con estado, asignado, tiempo de resolución y enlace a evidencias.

---

# 3. ENTORNOS

## 3.1 Entorno TRL7 operacional (AWS)

El entorno operacional del prototipo TRAC está desplegado íntegramente en **AWS** (región europea) y constituye el único entorno activo en la Etapa 3. Su propósito es demostrar el funcionamiento del sistema en condiciones operacionales reales, ejecutando el flujo completo de ingesta, enriquecimiento, predicción IA y generación de alertas de forma continua.

**Características del entorno TRL7:**

| Parámetro | Valor |
|---|---|
| Proveedor cloud | AWS (región EU) |
| Modelo de despliegue | Instancias EC2 con contenedores Docker (docker-compose) |
| Gestión de código y CI/CD | Azure DevOps (`https://dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4`) |
| IaC | Terraform (versionado en ADO Repos) |
| Red | VPC privada con subredes públicas (bastion/ALB) y privadas (EC2, datos) |
| Seguridad de acceso | Security Groups, roles IAM, Secrets Manager, KMS |
| Monitorización | Amazon CloudWatch (logs y métricas), dashboards personalizados |
| Disponibilidad objetivo | Best-effort para demostración; sin SLA productivo (ver sección 9) |

**Instancias EC2 del entorno TRL7:**

| Instancia | Tipo | Módulo(s) |
|---|---|---|
| trac-ingest-btc | c6a.xlarge | Ingesta Bitcoin |
| trac-ingest-eth | c6a.xlarge | Ingesta Ethereum |
| trac-ingest-pol | c6a.xlarge | Ingesta Polygon |
| trac-enrich | m6a.xlarge | Enriquecimiento (Airflow + Neo4j) |
| trac-ai | t3a.xlarge | Módulo IA (ETL+AI, predicciones) |
| trac-events | m6a.2xlarge | Motor de Reglas / Gestor de Eventos (Kafka + Flink + Redis + OpenSearch) |
| trac-frontend | (según sizing) | Frontal Web |

Todos los módulos se despliegan mediante **Docker y docker-compose**. Las imágenes se construyen desde los repositorios en ADO Repos y se publican en Amazon ECR.

## 3.2 Cuentas Cloud y estrategia de red

La VPC del entorno TRL7 sigue el siguiente esquema de red:

- **Subredes públicas:** acceso controlado vía ALB y/o bastion host; exponen únicamente los endpoints necesarios para la demostración (frontal web, API).
- **Subredes privadas:** alojan todas las instancias EC2 con los servicios de ingesta, datalake, enriquecimiento, IA y motor de eventos. No tienen acceso directo a Internet.
- **VPC Endpoints:** para acceso privado a S3, Secrets Manager y otros servicios AWS sin salir a Internet.
- **Security Groups:** cada módulo tiene su propio SG con reglas de mínimo privilegio (solo los puertos necesarios entre los componentes que se comunican entre sí).
- **Acceso operativo:** el acceso SSH a las instancias se realiza a través de AWS Systems Manager Session Manager o bastion host, nunca con claves expuestas en código.

El detalle de la configuración de red (CIDR, SG rules, tabla de rutas) se encuentra en los ficheros Terraform del repositorio `infra/` en ADO Repos, y en las tablas de red del documento de arquitectura.

## 3.3 Gestión de secretos y claves (KMS / Secrets Manager)

Todos los secretos operativos (credenciales de bases de datos, claves de API externas, tokens de Alchemy para Polygon, claves SSH de módulos) se almacenan en **AWS Secrets Manager** y se cifran con **AWS KMS**. Ningún secreto debe aparecer en texto plano en repositorios, ficheros `.env` ni logs.

**Procedimiento para uso de secretos en contenedores:**

1. Los contenedores recuperan los secretos en tiempo de arranque mediante llamadas al SDK de AWS (usando el rol IAM de la instancia EC2).
2. El fichero `.env.example` en cada repositorio de módulo sirve como plantilla de referencia; el `.env` real **nunca** se sube al repositorio.
3. La rotación de secretos se realiza en Secrets Manager. Tras la rotación, los contenedores afectados deben reiniciarse para cargar los nuevos valores.
4. Toda operación sobre KMS y Secrets Manager queda auditada en CloudTrail.

## 3.4 Futuros entornos (recomendación)

> **Nota:** Los entornos descritos a continuación **no existen actualmente** y corresponden a una recomendación de evolución futura del sistema hacia un despliegue productivo post-TRL7.

Se recomienda, en fases posteriores al TRL7, establecer los siguientes entornos adicionales:

| Entorno | Propósito | Observaciones |
|---|---|---|
| **PRE (preproducción)** | Validación de cambios antes de su paso al entorno operacional/producción | Réplica fiel del entorno TRL7; ejecuta los mismos pipelines de validación |
| **PRO (producción)** | Servicio productivo para usuarios finales con SLAs definidos | Requiere revisión de sizing, alta disponibilidad, disaster recovery y acuerdos contractuales |

---

# 4. PROCEDIMIENTOS DE INSTALACIÓN Y DESPLIEGUE

## 4.1 Pre-requisitos y controles previos

Antes de iniciar un despliegue (inicial o de actualización) en el entorno TRL7, verificar:

| # | Pre-requisito | Responsable | Verificación |
|---|---|---|---|
| 1 | Cuenta AWS activa con los permisos IAM requeridos | Infraestructura | `aws sts get-caller-identity` retorna el role correcto |
| 2 | Acceso a ADO Repos con rama correcta y PR aprobado | Desarrollo | PR en estado *Completed* o *Approved* en ADO |
| 3 | Pipeline CI de ADO en estado *Succeeded* para el commit a desplegar | Infraestructura | Verde en ADO Pipelines |
| 4 | Secrets actualizados en AWS Secrets Manager | Infraestructura | Verificar versión y fecha de rotación en Secrets Manager |
| 5 | Imágenes Docker publicadas en ECR con el tag correcto | Infraestructura | `aws ecr describe-images` confirma el tag |
| 6 | Estado de instancias EC2 en Running y sin alarmas activas previas | Infraestructura | CloudWatch Alarms sin estado ALARM |
| 7 | Ventana de cambio comunicada y aprobada | Todos | Work Item en ADO Boards en estado *Approved* |
| 8 | Backup reciente validado (para actualizaciones de datalake/BD) | Infraestructura | Snapshot disponible en AWS Backup < 24 h |

## 4.2 Aprovisionamiento de infraestructura base (IaC / Terraform)

La infraestructura AWS del entorno TRL7 se define y gestiona mediante **Terraform**, almacenado en el repositorio `infra/` de ADO Repos.

**Procedimiento de aprovisionamiento (inicial o actualización de infraestructura):**

```bash
# 1. Clonar o actualizar el repositorio de infraestructura desde ADO
git clone https://ES-RA-ECC@dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4/_git/infra
cd infra/

# 2. Inicializar Terraform (backend en S3)
terraform init

# 3. Revisar el plan antes de aplicar
terraform plan -var-file="trl7.tfvars" -out=tfplan

# 4. Revisar el plan y validar que solo se modifican los recursos esperados
# (NUNCA aplicar sin revisión del plan)

# 5. Aplicar (requiere aprobación del Aprobador técnico)
terraform apply tfplan
```

El pipeline de ADO automatiza los pasos 2–5 en los despliegues gestionados. Los `terraform apply` manuales solo se permiten para operaciones de emergencia documentadas como incidencia en ADO Boards.

**Componentes aprovisionados por Terraform:**
- VPC, subredes, Internet Gateway, NAT Gateway, tabla de rutas
- Security Groups por módulo
- Instancias EC2 con AMI base Ubuntu 22.04
- Roles IAM y políticas de mínimo privilegio por instancia
- VPC Endpoints (S3, Secrets Manager, ECR)
- Buckets S3 (artefactos, backups, logs ALB)
- CloudWatch Log Groups y alarmas
- AWS Backup plans

## 4.3 IAM y permisos mínimos

Cada instancia EC2 tiene asignado un **IAM Instance Profile** con un rol específico que solo otorga los permisos estrictamente necesarios para su función:

| Rol IAM | Instancia(s) | Permisos relevantes |
|---|---|---|
| `trac-ingest-role` | trac-ingest-btc/eth/pol | Secrets Manager (lectura), CloudWatch Logs, S3 (escritura bucket datalake) |
| `trac-enrich-role` | trac-enrich | Secrets Manager (lectura), CloudWatch Logs, S3 (lectura/escritura), ECR (pull) |
| `trac-ai-role` | trac-ai | Secrets Manager (lectura), CloudWatch Logs, S3 (lectura/escritura), ECR (pull) |
| `trac-events-role` | trac-events | Secrets Manager (lectura), CloudWatch Logs, ECR (pull) |
| `trac-frontend-role` | trac-frontend | Secrets Manager (lectura), CloudWatch Logs, ECR (pull) |
| `trac-infra-deploy-role` | Agente ADO Pipelines | EC2 (gestión limitada: describe, start/stop instancias del proyecto), ECR (push/pull en repositorios del proyecto), S3 (lectura/escritura en buckets del proyecto), CloudWatch (put metrics/logs), Secrets Manager (lectura de secrets del proyecto). **Los permisos se definen acotados a ARNs específicos en Terraform; nunca se conceden permisos `*` a nivel de cuenta** |

Los roles se definen en Terraform y toda modificación de permisos pasa por el proceso de gestión del cambio (sección 2.2).

## 4.4 Gestión de secrets y variables de entorno

**Para cada módulo, al provisionar o actualizar:**

1. Crear/actualizar el secret en AWS Secrets Manager con el nombre de convenio: `trac/<entorno>/<modulo>/<nombre-secret>` (ej. `trac/trl7/enrich/neo4j-password`).
2. Verificar que la política de recursos del secret permite el acceso desde el rol IAM de la instancia correspondiente.
3. En el fichero `docker-compose.yml` o `entrypoint.sh` de cada módulo, las variables sensibles se recuperan desde Secrets Manager en tiempo de arranque (nunca hardcodeadas).
4. Tras cualquier rotación de secreto, reiniciar el contenedor afectado:
   ```bash
   docker-compose restart <servicio>
   ```
5. Verificar en logs que el servicio arranca correctamente y puede conectar con sus dependencias.

## 4.5 Despliegue de módulos (pipelines CI/CD — Azure DevOps)

Cada módulo del sistema TRAC tiene su propio repositorio en ADO Repos y su pipeline de CI/CD en ADO Pipelines. El pipeline estándar de despliegue ejecuta las siguientes etapas:

```
[Trigger: merge a main]
       │
       ▼
  Stage: Build
  ├── Checkout del código
  ├── Build de imagen Docker
  ├── Tests unitarios / integración
  └── Push de imagen a Amazon ECR (tag: commit SHA + latest)
       │
       ▼
  Stage: Deploy (requiere aprobación manual en TRL7)
  ├── Conexión SSH al agente desplegado en AWS (o SSM)
  ├── Pull de la nueva imagen desde ECR
  ├── docker-compose pull && docker-compose up -d
  └── Verificación de health check del contenedor
       │
       ▼
  Stage: Smoke Test
  └── Ejecución del smoke test automático (ver sección 5.1)
```

**Control de versiones de módulos:**

| Módulo | Repositorio ADO | Rama principal |
|---|---|---|
| Ingesta BTC/ETH/POL | `trac-ingest` | `main` |
| ETL + IA | `trac-etl-ai` | `main` |
| Enriquecimiento | `trac-enrich` | `main` |
| Motor de Reglas | `trac-events` | `main` |
| Frontal Web | `trac-frontend` | `main` |
| Infraestructura | `infra` | `main` |

## 4.6 Checklist de instalación

| # | Tarea | Estado |
|---|---|---|
| 1 | VPC, subredes y SGs creados por Terraform | ☐ |
| 2 | Instancias EC2 en estado Running | ☐ |
| 3 | Roles IAM asignados y verificados (`aws iam simulate-principal-policy`) | ☐ |
| 4 | Secrets creados en Secrets Manager | ☐ |
| 5 | Imágenes Docker publicadas en ECR para todos los módulos | ☐ |
| 6 | Módulo Ingesta BTC arrancado y sincronizando bloques | ☐ |
| 7 | Módulo Ingesta ETH arrancado y sincronizando | ☐ |
| 8 | Módulo Ingesta Polygon arrancado y recibiendo datos vía Alchemy | ☐ |
| 9 | PostgreSQL y Neo4j accesibles desde los módulos de ingesta y enriquecimiento | ☐ |
| 10 | Airflow (enriquecimiento) arrancado y con DAGs visibles | ☐ |
| 11 | Módulo IA (ETL+AI) arrancado y ejecutando predicciones | ☐ |
| 12 | Kafka, Flink, Redis y OpenSearch arrancados en trac-events | ☐ |
| 13 | Motor de reglas procesando eventos de transacciones | ☐ |
| 14 | Frontal Web accesible y mostrando datos | ☐ |
| 15 | CloudWatch Log Groups con logs de todos los módulos | ☐ |
| 16 | Alarmas CloudWatch configuradas y en estado OK | ☐ |
| 17 | Pipeline ADO ejecutado exitosamente para el último commit | ☐ |
| 18 | Smoke test PE3-0001 superado (ver sección 5) | ☐ |

---

# 5. VERIFICACIONES POST-DESPLIEGUE Y SMOKE TEST

## 5.1 Smoke test alineado con PE3-0001

El smoke test verifica la integración global de componentes, alineado con la prueba de validación **PE3-0001** del Plan de Validación Etapa 3 (`CCP3_R4_TRAC_ENT-0009-Plandevalidaciónetapa3.md`).

**Pasos del smoke test:**

| Paso | Acción | Resultado esperado | Evidencia |
|---|---|---|---|
| 1 | Verificar que los nodos de ingesta BTC/ETH/POL están activos y procesando bloques | Logs muestran bloques procesados en los últimos 10 minutos | Log CloudWatch `trac-ingest-*` |
| 2 | Verificar que el Datalake (PostgreSQL) contiene registros recientes de transacciones | Consulta `SELECT COUNT(*) FROM transactions WHERE timestamp > NOW() - INTERVAL '1 hour'` retorna > 0 | Captura de consulta |
| 3 | Verificar que Neo4j contiene nodos y relaciones de las últimas ingesta | Consulta Cypher `MATCH (n) RETURN COUNT(n)` retorna > 0 | Captura de consulta |
| 4 | Verificar que el módulo IA ejecutó predicciones en la última hora | Log de `trac-ai` muestra ejecución completada con duración entre 23–40 min | Log CloudWatch `trac-ai` |
| 5 | Verificar que el motor de eventos procesa transacciones de los topics Kafka | Kafka consumer groups sin lag excesivo (lag < umbral PKI-0013) | Salida de `kafka-consumer-groups.sh --describe` |
| 6 | Verificar que el Frontal Web carga correctamente y muestra alertas y wallets | Respuesta HTTP 200 en la URL del frontal; se visualizan datos en el dashboard | Captura de pantalla |
| 7 | Verificar que el pipeline ADO más reciente está en estado *Succeeded* | ADO Pipelines → último run en verde | URL del pipeline run |

**Criterio de superación:** todos los pasos deben completarse sin errores. Cualquier fallo bloquea el cierre del despliegue y activa el runbook correspondiente.

## 5.2 Checklist post-despliegue

| # | Verificación | Estado |
|---|---|---|
| 1 | Smoke test PE3-0001 completado sin errores | ☐ |
| 2 | Ninguna alarma CloudWatch en estado ALARM | ☐ |
| 3 | Logs de todos los módulos visibles en CloudWatch | ☐ |
| 4 | PKIs de ingesta BTC dentro de umbrales (PKI-0001 a PKI-0005) | ☐ |
| 5 | PKI de IA dentro de umbrales (PKI-0006 a PKI-0010) | ☐ |
| 6 | PKI de enriquecimiento dentro de umbral (PKI-0011) | ☐ |
| 7 | PKI de motor de reglas dentro de umbral (PKI-0012, PKI-0013) | ☐ |
| 8 | Work Item de cambio cerrado en ADO Boards con evidencias adjuntas | ☐ |
| 9 | Resultado del smoke test documentado como evidencia TRL7 | ☐ |

---

# 6. OPERACIÓN DIARIA

## 6.1 Checklist diario

El operador responsable debe revisar los siguientes puntos cada día hábil:

| # | Verificación | Herramienta | Umbral / Acción |
|---|---|---|---|
| 1 | Estado de instancias EC2 | AWS Console / CloudWatch | Todas en estado *running*; si alguna está *stopped*, arrancar y notificar |
| 2 | Logs de ingesta BTC: bloques y transacciones procesadas en las últimas 24 h | CloudWatch Logs → `trac-ingest-btc` | PKI-0003: 4–10 bloques/h; PKI-0004: 6.000–24.000 tx/h |
| 3 | Logs de ingesta ETH y Polygon: sin errores en grep de logs | CloudWatch Logs → `trac-ingest-eth`, `trac-ingest-pol` | Sin errores `ERROR` ni `CRITICAL` en últimas 24 h |
| 4 | Estado de Airflow: DAGs completados sin fallos | Airflow UI / CloudWatch | 0 DAGs en estado *Failed* |
| 5 | Ejecución de predicciones IA: última ejecución reciente y dentro del rango de duración | CloudWatch Logs → `trac-ai` | PKI-0006: duración 23–40 min; PKI-0007: CPU ≤ 25% |
| 6 | Lag de Kafka en el motor de reglas | Kafka metrics / CloudWatch | PKI-0013: lag < umbral operativo (< 1 minuto) |
| 7 | Uso de CPU/RAM en trac-enrich y trac-events | CloudWatch Metrics | PKI-0011: 30–60%; PKI-0012: 40–50%; alerta si > 85% |
| 8 | Revisión de alertas activas en CloudWatch Alarms | CloudWatch Alarms | 0 alarmas en estado ALARM; si existen, escalar según runbook |
| 9 | Revisión de incidencias abiertas en ADO Boards | ADO Boards | Atender las de prioridad Alta/Media en el día |
| 10 | Revisión del último pipeline ADO ejecutado | ADO Pipelines | Si hay pipeline fallido sin resolución pendiente, abrir incidencia |

## 6.2 Rutinas periódicas (semanal / mensual)

| Frecuencia | Tarea | Responsable |
|---|---|---|
| **Semanal** | Revisión de espacio en disco de todas las instancias EC2 | Infraestructura |
| **Semanal** | Revisión de logs de CloudTrail en busca de accesos anómalos | Infraestructura / Seguridad |
| **Semanal** | Verificar que los backups automáticos (AWS Backup) se han ejecutado correctamente | Infraestructura |
| **Semanal** | Actualizar el estado de los Work Items activos en ADO Boards | Equipo de operación |
| **Mensual** | Rotación preventiva de secretos en Secrets Manager | Infraestructura |
| **Mensual** | Revisión de políticas IAM y eliminación de permisos no utilizados | Infraestructura |
| **Mensual** | Revisión de costes AWS y ajuste de sizing si procede | Infraestructura |
| **Mensual** | Prueba de restore de un backup (dry-run) para validar el procedimiento | Infraestructura |
| **Mensual** | Revisión de tendencias de PKIs y actualización de umbrales si la evolución de las blockchains lo requiere | Infraestructura + Desarrollo |
| **Por release** | Ejecución del smoke test completo (PE3-0001) y archivo de evidencias | Infraestructura + Evaluador |

---

# 7. MONITORIZACIÓN Y ALERTAS

## 7.1 Infraestructura de monitorización

El sistema de monitorización del entorno TRL7 se basa en:

- **Amazon CloudWatch Logs:** centralización de logs de todos los módulos (contenedores Docker, sistema operativo). Cada módulo escribe a su Log Group dedicado con retención configurada.
- **Amazon CloudWatch Metrics:** métricas de EC2 (CPU, red, disco), métricas personalizadas de Kafka (lag, mensajes/s), y métricas de la API del datalake.
- **Amazon CloudWatch Alarms:** alarmas configuradas sobre los PKIs definidos que disparan notificaciones por SNS al equipo de operación.
- **Dashboards CloudWatch:** paneles de infraestructura (por EC2) y de negocio (tracking de blockchains, predicciones IA, alertas generadas). Ver sección 7.3.

Adicionalmente, el frontal web incluye métricas de negocio (número de wallets monitorizados, alertas generadas, incidentes abiertos).

## 7.2 PKIs y umbrales operativos

Los siguientes PKIs, extraídos del documento `CCP3_R4_TRAC_PKIs_Rendimiento - REVISAR TODOS.md`, definen el comportamiento esperado del sistema en el entorno TRL7:

| Código | Módulo | Nombre | Métrica | Rango normal | Umbral de alerta | Acción ante alerta |
|---|---|---|---|---|---|---|
| PKI-0001 | Ingesta BTC | Red Entrada | Network In por hora | 250 KB – 4 MB/h | < 100 KB/h ó > 6 MB/h | Verificar nodo Bitcoin Core; revisar conectividad de red |
| PKI-0002 | Ingesta BTC | Red Salida | Network Out por hora | 512 KB – 8 MB/h | > 12 MB/h | Revisar carga de escritura al datalake |
| PKI-0003 | Ingesta BTC | Bloques | Bloques procesados/h | 4 – 10 bloques/h | < 2 bloques/h | Runbook 8.1 — fallo ingesta BTC |
| PKI-0004 | Ingesta BTC | Transacciones | Transacciones/h | 6.000 – 24.000 tx/h | < 1.000 tx/h | Runbook 8.1 — fallo ingesta BTC |
| PKI-0005 | Ingesta BTC | CPU | Uso CPU (4 vCPU) | 5% – 30% | > 80% sostenido 15 min | Revisar carga del nodo; posible crecimiento de la blockchain |
| PKI-0006 | Módulo IA | Duración predicciones | Tiempo de ejecución | 23 – 40 min (media ~25) | > 60 min ó no ejecutado en 2 h | Runbook 8.3 — degradación módulo IA |
| PKI-0007 | Módulo IA | CPU | Uso CPU durante ejecución | ≤ 25% (1 vCPU al 100%) | > 50% CPU total | Revisar paralelismo y recursos del contenedor |
| PKI-0008 | Módulo IA | Red Entrada | Network In por ejecución | ≤ 35 MB | > 100 MB | Revisar volumen de datos recuperados del datalake |
| PKI-0009 | Módulo IA | Red Salida | Network Out por ejecución | ≤ 10 MB | > 30 MB | Revisar volumen de resultados escritos |
| PKI-0010 | Módulo IA | Disco | Consumo de disco por ejecución | ~500 MB | > 1.5 GB | Revisar limpieza de ficheros temporales |
| PKI-0011 | Enriquecimiento | CPU/RAM | Uso CPU/RAM (m6a.xlarge) | 30% – 60% nominal | > 85% sostenido 10 min | Runbook 8.2 — fallo enriquecimiento |
| PKI-0012 | Motor de Reglas | CPU/RAM | Uso CPU/RAM (m6a.2xlarge) | 40% – 50% nominal | > 85% sostenido 10 min | Runbook 8.4 — fallo motor de reglas |
| PKI-0013 | Motor de Reglas | Lag Kafka | Lag de topics Kafka | < 1 min | Lag > umbral operativo (1 min) | Runbook 8.4 — lag Kafka; revisar paralelismo Flink |

> **Nota:** los rangos normales reflejan el comportamiento observado en la Etapa 2 del proyecto. Deben revisarse periódicamente con la evolución de las blockchains.

## 7.3 Dashboards

**Dashboard de infraestructura (por EC2):**
Contiene paneles de CPU, red (in/out), disco y estado de los contenedores para cada instancia EC2 del entorno TRL7. Accesible en CloudWatch Dashboards → `TRAC-TRL7-Infraestructura`.

**Dashboard de negocio (tracking de blockchains):**
Contiene paneles de:
- Bloques y transacciones procesadas por blockchain (BTC/ETH/POL)
- Estado de ejecuciones del módulo IA (duración, frecuencia)
- Lag de Kafka del motor de eventos
- Número de alertas generadas en las últimas 24 h
- Número de incidentes abiertos en el frontal web

Accesible en CloudWatch Dashboards → `TRAC-TRL7-Negocio`.

---

# 8. RUNBOOKS — RESOLUCIÓN DE INCIDENCIAS

## 8.1 Incidencia: fallo o retraso en ingesta BTC/ETH/Polygon

**Síntomas:** PKI-0003 o PKI-0004 por debajo del umbral; logs de `trac-ingest-*` con errores; datalake sin nuevas transacciones.

**Diagnóstico y resolución:**

```bash
# 1. Conectar a la instancia afectada via SSM o bastion
aws ssm start-session --target <instance-id>

# 2. Ver estado del contenedor de ingesta
docker-compose ps
docker-compose logs --tail=100 ingest

# 3. Si el contenedor está stopped o en error, reiniciarlo
docker-compose restart ingest

# 4. Verificar sincronización del nodo BTC (si aplica)
# El nodo Bitcoin Core puede estar en proceso de sincronización inicial
# (IBD — Initial Block Download); verificar el bloque actual vs el bloque
# más reciente en blockchain.com
docker exec -it trac_ingest_1 bitcoin-cli getblockchaininfo | grep -E "blocks|headers|verificationprogress"

# 5. Para ETH: verificar estado de los clientes Reth y Nimbus
docker-compose logs --tail=50 reth
docker-compose logs --tail=50 nimbus

# 6. Para Polygon: verificar que la API key de Alchemy es válida
# (comprobar secreto en Secrets Manager)
aws secretsmanager get-secret-value --secret-id trac/trl7/ingest/alchemy-api-key

# 7. Verificar conectividad de red desde la instancia
curl -s https://blockchain.info/latestblock | python3 -m json.tool

# 8. Si el problema persiste, escalar a Equipo de Desarrollo (CITRA)
```

**Escalado:** si tras 30 minutos no se recupera la ingesta, abrir incidencia P1 en ADO Boards y notificar al Equipo de Desarrollo (CITRA).

## 8.2 Incidencia: fallo en módulo de enriquecimiento (Airflow/Neo4j)

**Síntomas:** PKI-0011 por encima del umbral de alerta (CPU/RAM > 85%); DAGs de Airflow en estado *Failed*; Neo4j sin nuevos nodos.

**Diagnóstico y resolución:**

```bash
# 1. Conectar a trac-enrich via SSM
aws ssm start-session --target <trac-enrich-instance-id>

# 2. Ver estado de los contenedores
docker-compose ps
docker-compose logs --tail=100 airflow
docker-compose logs --tail=100 neo4j

# 3. Revisar DAGs fallidos en la UI de Airflow
# (acceder via tunnel SSH al puerto de la UI de Airflow)
# Identificar el DAG fallido y revisar el log de la tarea

# 4. Verificar uso de recursos
top -bn1 | head -20
df -h

# 5. Si el disco está > 85%, limpiar ficheros temporales de DAGs completados
# y snapshots antiguos de Neo4j no necesarios

# 6. Si Neo4j no responde, reiniciar el contenedor
docker-compose restart neo4j

# 7. Si Airflow tiene DAGs bloqueados, limpiarlos desde la UI o via CLI
docker exec -it trac_airflow_1 airflow dags clear <dag_id> --yes

# 8. Si el problema es de CPU/RAM sostenida, revisar si hay DAGs en bucle
# o consultas Cypher sin optimizar; escalar a Equipo de Desarrollo (CITRA/ECC)
```

## 8.3 Incidencia: degradación o fallo del módulo IA

**Síntomas:** PKI-0006 fuera de rango (duración > 60 min o no ejecutado en > 2 h); PKI-0007 por encima del 50% de CPU total.

**Diagnóstico y resolución:**

```bash
# 1. Conectar a trac-ai via SSM
aws ssm start-session --target <trac-ai-instance-id>

# 2. Ver estado del contenedor de IA
docker-compose ps
docker-compose logs --tail=100 etl_ai

# 3. Verificar si el entrypoint está ejecutándose
docker exec -it trac_etl_ai_1 ps aux | grep python

# 4. Si el proceso está atascado (mismo PID durante > 1 h sin avance en logs):
docker-compose restart etl_ai

# 5. Verificar conectividad con el datalake PostgreSQL
# (el módulo IA necesita recuperar datos de PostgreSQL para las queries)
docker exec -it trac_etl_ai_1 python3 -c "import psycopg2; print('DB OK')"

# 6. Verificar espacio en disco (PKI-0010: ~500 MB por ejecución)
df -h /var/lib/docker

# 7. Si el disco está lleno, limpiar ficheros temporales CSV y Parquet
# de ejecuciones anteriores según la política de retención definida
docker exec -it trac_etl_ai_1 find /app/tmp -name "*.csv" -mtime +1 -delete

# 8. Documentar la incidencia en ADO Boards con: tiempo de detección,
# acciones tomadas, tiempo de recuperación (para métricas RTO)
```

## 8.4 Incidencia: fallo en motor de reglas / gestor de eventos

**Síntomas:** PKI-0012 por encima de 85% (CPU/RAM); PKI-0013 con lag de Kafka elevado (> umbral); alertas no llegan al frontal web.

**Diagnóstico y resolución:**

```bash
# 1. Conectar a trac-events via SSM
aws ssm start-session --target <trac-events-instance-id>

# 2. Ver estado de todos los contenedores del stack de eventos
docker-compose ps

# 3. Revisar lag de Kafka
docker exec -it trac_kafka_1 kafka-consumer-groups.sh \
  --bootstrap-server localhost:9092 \
  --describe --all-groups

# 4. Si el lag es elevado, verificar el estado de los jobs de Flink
docker-compose logs --tail=50 flink-jobmanager
docker-compose logs --tail=50 flink-taskmanager

# 5. Si un job de Flink está en estado FAILED, reiniciarlo desde la UI de Flink
# o via API REST:
curl -X PATCH http://localhost:8081/jobs/<job-id> \
  -H "Content-Type: application/json" \
  -d '{"target-state": "cancel"}'
# y resubmit del jar correspondiente

# 6. Verificar estado de Redis
docker exec -it trac_redis_1 redis-cli ping
# Esperado: PONG

# 7. Verificar estado de OpenSearch
curl -s http://localhost:9200/_cluster/health | python3 -m json.tool
# Esperado: status "green" o "yellow"

# 8. Si el problema es de recursos (CPU/RAM > 85%):
# - Verificar si el módulo IA está ejecutándose simultáneamente
#   (comparte instancia con el motor de reglas)
# - Ajustar el paralelismo de Flink si es necesario

# 9. Si OpenSearch no responde o tiene índices corruptos:
# Ver runbook de restore de OpenSearch (sección 8.7)
```

## 8.5 Incidencia: degradación de recursos EC2 (CPU/RAM/disco)

**Síntomas:** CloudWatch Alarm en estado ALARM por CPU > 80% sostenido, memoria > 90% o disco > 85% en cualquier instancia.

**Diagnóstico y resolución:**

```bash
# 1. Conectar a la instancia afectada
aws ssm start-session --target <instance-id>

# 2. Identificar el proceso que consume más recursos
top -bn1 | sort -k9 -r | head -20   # CPU
free -h                               # Memoria
df -h                                 # Disco

# 3. Para disco lleno:
# - Limpiar logs de Docker antiguos
docker system prune --volumes --force
# - Limpiar ficheros temporales del módulo
# - Revisar si hay snapshots/exportaciones no limpiadas

# 4. Para CPU sostenida alta:
# - Identificar el contenedor culpable: docker stats
# - Revisar si es una situación esperada (ej. IA ejecutando predicciones)
# - Si no es esperado, reiniciar el contenedor afectado

# 5. Registrar la incidencia en ADO Boards y considerar si es necesario
# cambiar el tipo de instancia EC2 (requiere ventana de cambio)
```

## 8.6 Incidencia: fallo de conectividad a fuentes externas

**Síntomas:** módulo de Polygon no recibe datos (API Alchemy inaccesible); módulo de enriquecimiento no puede consultar fuentes OSINT externas; errores de red en logs.

**Diagnóstico y resolución:**

```bash
# 1. Verificar conectividad general desde la instancia afectada
curl -s --max-time 10 https://api.alchemy.com 2>&1
curl -s --max-time 10 https://blockchain.info/latestblock 2>&1

# 2. Verificar que el NAT Gateway de la VPC está operativo
# (las instancias en subredes privadas necesitan NAT para acceso a Internet)
# Desde AWS Console: VPC → NAT Gateways → verificar estado "available"

# 3. Verificar que los Security Groups permiten el tráfico saliente
# necesario (HTTPS/443 hacia Internet)

# 4. Si la API de Alchemy devuelve error de autenticación:
# Verificar que la API key en Secrets Manager es válida y no ha expirado
aws secretsmanager get-secret-value --secret-id trac/trl7/ingest/alchemy-api-key
# Si es necesario, renovar la API key en la plataforma de Alchemy y
# actualizar el secret en Secrets Manager, luego reiniciar el contenedor

# 5. Si el problema es de throttling (rate limit de API externa):
# Revisar la frecuencia de consulta configurada en el módulo correspondiente
# y ajustar si es necesario (requiere Work Item en ADO Boards)

# 6. Registrar la incidencia en ADO Boards con tiempos y acciones
```

## 8.7 Procedimiento de backup y restore

**Backup bajo demanda (antes de operaciones de riesgo):**

```bash
# Snapshot manual de PostgreSQL (datalake)
aws rds create-db-snapshot \
  --db-instance-identifier trac-postgres-trl7 \
  --db-snapshot-identifier trac-manual-$(date +%Y%m%d-%H%M)

# Snapshot manual de volumen EBS de una instancia EC2
aws ec2 create-snapshot \
  --volume-id <volume-id> \
  --description "Manual backup pre-deploy $(date +%Y%m%d)"
```

**Restore de PostgreSQL desde snapshot:**

```bash
# 1. Identificar el snapshot a restaurar
aws rds describe-db-snapshots --db-instance-identifier trac-postgres-trl7

# 2. Restaurar la instancia desde snapshot
aws rds restore-db-instance-from-db-snapshot \
  --db-instance-identifier trac-postgres-trl7-restored \
  --db-snapshot-identifier <snapshot-id>

# 3. Verificar que la instancia restaurada está en estado "available"
aws rds describe-db-instances --db-instance-identifier trac-postgres-trl7-restored

# 4. Actualizar el secret en Secrets Manager con el nuevo endpoint
# y reiniciar los módulos que usan PostgreSQL

# 5. Verificar integridad de los datos restaurados
```

**Restore de Neo4j (desde backup de volumen EBS):**

```bash
# 1. Detener el contenedor de Neo4j
docker-compose stop neo4j

# 2. Restaurar el volumen EBS desde snapshot via AWS Console o CLI

# 3. Montar el volumen restaurado y copiar los datos al directorio
# de datos de Neo4j (habitualmente /data/neo4j)

# 4. Arrancar el contenedor de Neo4j
docker-compose start neo4j

# 5. Verificar integridad: docker exec -it trac_neo4j_1 cypher-shell
# MATCH (n) RETURN COUNT(n)
```

---

# 9. BACKUPS, RTO, RPO Y CONTINUIDAD

## Política de backups

En el entorno TRL7, la estrategia de backups tiene como objetivo preservar la integridad de los datos del prototipo y permitir la recuperación ante fallos operativos durante la demostración. No se aplican SLAs productivos, sino objetivos operativos coherentes con TRL7.

| Recurso | Tipo de backup | Frecuencia | Retención | Herramienta |
|---|---|---|---|---|
| PostgreSQL (datalake) | Snapshot automático | Diario | 7 días | AWS Backup / RDS automated backup |
| Neo4j (grafo) | Snapshot de volumen EBS | Diario | 7 días | AWS Backup |
| Volúmenes EBS de instancias EC2 | Snapshot automático | Diario | 7 días | AWS Backup |
| Código fuente y configuración IaC | Versionado en Git | Continuo (cada commit) | Indefinido | ADO Repos |
| Logs operativos | CloudWatch Logs + exportación S3 (opcional) | Continuo | 30 días en CloudWatch | CloudWatch |
| Artefactos de pipeline (evidencias TRL7) | Almacenados en ADO / S3 | Por cada ejecución | Duración del proyecto | ADO Pipelines / S3 |

## RTO y RPO para el entorno TRL7

En coherencia con la naturaleza de prototipo operacional TRL7 (no servicio productivo), los objetivos de RTO y RPO son los siguientes:

| Parámetro | Objetivo TRL7 | Cómo se mide | Cómo se evidencia |
|---|---|---|---|
| **RTO** (Recovery Time Objective) | < 4 horas para recuperación del servicio operativo tras un fallo | Tiempo entre detección de la incidencia (apertura de Work Item en ADO Boards) y verificación del smoke test exitoso | Log de la incidencia en ADO Boards con timestamps |
| **RPO** (Recovery Point Objective) | < 24 horas (pérdida máxima de datos tolerable) | Antigüedad del último backup válido disponible en el momento del fallo | Registro de backups en AWS Backup console |
| **Disponibilidad** | Best-effort durante periodos de demostración activa; sin objetivo de uptime porcentual en periodos de mantenimiento | Monitorización continua con CloudWatch; análisis mensual de tiempo operativo | Dashboard CloudWatch + revisión mensual |

> **Nota TRL7:** estos objetivos son operativos para el prototipo de demostración. Un entorno productivo futuro (post-TRL7) requerirá definir SLAs contractuales, arquitectura de alta disponibilidad y estrategias de DR formales.

## Plan de continuidad básico

En caso de fallo total de una instancia EC2 que no pueda recuperarse en el plazo de RTO:

1. Crear una nueva instancia EC2 del mismo tipo en la misma VPC/subred desde la AMI base de Ubuntu 22.04.
2. Asignar el IAM Instance Profile y los Security Groups correspondientes al módulo.
3. Restaurar los datos del módulo desde el último backup disponible (ver sección 8.7).
4. Redeploy del módulo desde el pipeline de ADO o manualmente con `docker-compose up -d`.
5. Ejecutar el smoke test para verificar la recuperación.
6. Documentar la incidencia y el tiempo de recuperación real en ADO Boards como evidencia TRL7.

---

# 10. EVIDENCIAS TRL7

El nivel TRL7 requiere demostrar el funcionamiento del prototipo en un entorno operacional. Las siguientes evidencias deben generarse, custodiarse y estar disponibles para el equipo evaluador:

| Tipo de evidencia | Descripción | Dónde se genera | Dónde se almacena |
|---|---|---|---|
| **Logs de ingesta** | Logs de CloudWatch de los módulos de ingesta BTC/ETH/POL mostrando bloques y transacciones procesadas | CloudWatch Logs | CloudWatch Logs / exportación S3 |
| **Dashboards operacionales** | Capturas de los dashboards CloudWatch de infraestructura y de negocio durante ejecución activa | CloudWatch Dashboards | Capturas en S3 / ADO Wiki |
| **Ejecuciones de pipelines ADO** | Historial de ejecuciones de ADO Pipelines con resultado Succeeded para todos los módulos | ADO Pipelines | ADO Pipelines (artefactos + logs) |
| **Resultados del smoke test (PE3-0001)** | Log de ejecución del smoke test con todos los pasos verificados | Verificación manual / automatizada | ADO Boards (adjunto al Work Item de despliegue) |
| **Resultados del plan de validación Etapa 3** | Evidencias de los casos de prueba PE3-0001 a PE3-0014 según el documento ENT-0009 | Ejecución de pruebas | Documento `CCP3_R4_TRAC_ENT-0009-Plandevalidaciónetapa3.md` |
| **Predicciones IA ejecutadas** | Logs del módulo IA con tiempos de ejecución dentro del rango PKI-0006/PKI-0007 | CloudWatch Logs `trac-ai` | CloudWatch Logs |
| **Alertas generadas** | Capturas del frontal web mostrando alertas generadas a partir de transacciones de blockchain reales | Frontal Web | Capturas en S3 / ADO Wiki |
| **Registros de incidencias** | Work Items en ADO Boards de incidencias detectadas y resueltas, con RTO registrado | ADO Boards | ADO Boards |
| **Registros de backups** | Histórico de ejecuciones de AWS Backup con resultado exitoso | AWS Backup Console | Captura mensual en S3 / ADO Wiki |
| **Resultado de prueba de restore** | Evidencia de la prueba mensual de restore de backup con resultado satisfactorio | Ejecución manual | ADO Boards / S3 |

**Procedimiento de custodia de evidencias:**

1. Tras cada jornada de demostración activa, el operador responsable exporta los logs relevantes de CloudWatch al bucket S3 de evidencias (`s3://trac-trl7-evidencias/`).
2. Las capturas de dashboards y del frontal web se adjuntan al Work Item de la jornada en ADO Boards.
3. Al cierre de cada sprint/release, se genera un informe de evidencias resumiendo los resultados de PKIs, disponibilidad y casos de prueba ejecutados.
4. Las evidencias se organizan por fecha y tipo en el bucket S3, con control de acceso restringido al equipo del proyecto.

---

# 11. CONFIGURACIONES DE SEGURIDAD

## IAM y principio de mínimo privilegio

Cada módulo opera con un IAM Role específico (ver sección 4.3). Está prohibido el uso de credenciales de usuario IAM (Access Key + Secret Key) en instancias EC2; siempre se usan Instance Profiles. La revisión de políticas IAM se realiza mensualmente.

## Red y perímetro

- **Security Groups:** tráfico de entrada limitado a los puertos estrictamente necesarios entre módulos. El frontal web es el único punto de entrada desde Internet (a través de ALB, si aplica).
- **Sin claves SSH expuestas en código ni en S3 públicos.** El acceso a instancias se realiza exclusivamente mediante AWS Systems Manager Session Manager.
- **VPC Endpoints** para acceso privado a S3, Secrets Manager y ECR sin tráfico por Internet.

## Cifrado

- **En tránsito:** TLS 1.2+ en todas las comunicaciones externas e internas que soporten TLS (API, frontal web, conexiones a bases de datos).
- **En reposo:** volúmenes EBS cifrados con KMS; buckets S3 con cifrado SSE-S3 o SSE-KMS; secretos en Secrets Manager cifrados con KMS.

## Auditoría

- **AWS CloudTrail** activo en la cuenta, registrando todas las llamadas a la API de AWS.
- **CloudWatch Logs** para todos los módulos con retención mínima de 30 días.
- Revisión semanal de CloudTrail en busca de accesos anómalos o cambios no autorizados.

## Gestión de vulnerabilidades

- Las imágenes Docker se escanean en **Amazon ECR** antes del despliegue (escaneo de vulnerabilidades activado).
- Las actualizaciones de seguridad del SO base (Ubuntu 22.04) se aplican mensualmente mediante el proceso de gestión del cambio.

---

# 12. REFERENCIAS

| Documento | Descripción |
|---|---|
| `Proc-operativo.md` | Procedimientos operativos de la plataforma base (referencia de estructura y estilo) |
| `CCP3_R4_TRAC_Documento de Arquitectura del prototipo.md` | Arquitectura completa del prototipo TRAC: componentes, flujos de datos, infraestructura y gestión del software |
| `CCP3_Proyecto_Ingenieria_R4_TRAC_Deloitte.md` | Proyecto de ingeniería: requisitos (REQ-xxxx) y especificaciones no funcionales (ESN-xxxx) |
| `CCP3_R4_TRAC_ENT-0009-Plandevalidaciónetapa3.md` | Plan de validación Etapa 3: casos de prueba PE3-0001 a PE3-0014 con criterios y evidencias |
| `CCP3_R4_TRAC_PKIs_Rendimiento - REVISAR TODOS.md` | PKIs y métricas de rendimiento por módulo; resultados de pruebas de rendimiento Etapa 2 |
| `https://dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4` | Repositorio Azure DevOps del proyecto: código, pipelines, boards e historial de cambios |

---

# 13. ANEXOS

## 13.1 Histórico de modificaciones

| Versión | Fecha | Autor | Modificaciones |
|---|---|---|---|
| 1.0 | 2026-03-02 | Equipo Infraestructura (ECC) | Creación del documento — procedimientos operativos CRIPTO TRACK TRL7 |

## 13.2 Glosario

| Término | Definición |
|---|---|
| **Blockchain** | Cadena de bloques distribuida e inmutable que registra transacciones de criptoactivos |
| **Wallet / Cartera** | Dirección pública en una blockchain que puede enviar y recibir criptoactivos |
| **Ingesta** | Proceso de sincronización y extracción de datos de una blockchain hacia el datalake del sistema |
| **Datalake** | Repositorio centralizado de datos estructurados (PostgreSQL) y de grafo (Neo4j) del prototipo |
| **Enriquecimiento** | Proceso de incorporación de datos off-chain (fuentes OSINT, DFIR) para contextualizar las transacciones |
| **Predicción de peligrosidad** | Estimación del nivel de riesgo asociado a una cartera o transacción, generada por el módulo IA |
| **Motor de reglas** | Componente que evalúa reglas de negocio sobre los eventos de transacciones y predicciones para generar alertas |
| **Alert / Alerta** | Notificación generada por el motor de reglas cuando una transacción o cartera cumple criterios de riesgo |
| **Incidente** | Alerta escalada a nivel de gestión operativa que requiere intervención de un analista |
| **TRL7** | Technology Readiness Level 7: el sistema ha sido demostrado en entorno operacional real o que simula condiciones reales |
| **PE3-xxxx** | Caso de prueba definido en el Plan de Validación Etapa 3 (ENT-0009) |
| **Dry-run** | Ejecución de prueba de un procedimiento sin impacto real en producción, para validar el procedimiento |
