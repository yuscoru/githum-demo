Procedimientos operativos

Procedimientos operativos de la plataforma

Expediente CPP001/24

[]{#_Toc408386624 .anchor}ÍNDICE

# Contents {#contents .TOC-Heading}

[ÍNDICE [2](#_Toc408386624)](#_Toc408386624)

[1 INTRODUCCIÓN [4](#introducción)](#introducción)

[1.1 Objetivo y alcance [4](#objetivo-y-alcance)](#objetivo-y-alcance)

[1.2 Términos y acrónimos
[4](#términos-y-acrónimos)](#términos-y-acrónimos)

[1.3 Contexto arquitectónico
[4](#contexto-arquitectónico)](#contexto-arquitectónico)

[2 2. GOBERNANZA OPERATIVA
[6](#gobernanza-operativa)](#gobernanza-operativa)

[2.1 Modelo RACI [6](#modelo-raci)](#modelo-raci)

[2.2 Gestión del cambio [6](#gestión-del-cambio)](#gestión-del-cambio)

[2.3 KPIs e indicadores [7](#kpis-e-indicadores)](#kpis-e-indicadores)

[2.3.1 Tiempo de disponibilidad
[7](#tiempo-de-disponibilidad)](#tiempo-de-disponibilidad)

[2.3.2 RTO [7](#rto)](#rto)

[2.3.3 RPO [8](#rpo)](#rpo)

[2.3.4 Tiempos de respuesta
[8](#tiempos-de-respuesta)](#tiempos-de-respuesta)

[3 ENTORNOS, PRE-REQUISITOS Y CONTROLES
[9](#entornos-pre-requisitos-y-controles)](#entornos-pre-requisitos-y-controles)

[3.1 Entornos y aislamiento
[9](#entornos-y-aislamiento)](#entornos-y-aislamiento)

[3.2 Cuentas Cloud y estrategia de portabilidad
[9](#cuentas-cloud-y-estrategia-de-portabilidad)](#cuentas-cloud-y-estrategia-de-portabilidad)

[3.3 Gestión de secretos y claves (KMS / Secrets Manager)
[12](#gestión-de-secretos-y-claves-kms-secrets-manager)](#gestión-de-secretos-y-claves-kms-secrets-manager)

[4 4. PROCEDIMIENTOS DE INSTALACIÓN
[13](#procedimientos-de-instalación)](#procedimientos-de-instalación)

[4.1 4.1 Aprovisionamiento base [13](#_Toc219806967)](#_Toc219806967)

[4.2 4.1 Aprovisionamiento base
[13](#aprovisionamiento-base)](#aprovisionamiento-base)

[4.3 Capa de autenticación e IAM
[13](#capa-de-autenticación-e-iam)](#capa-de-autenticación-e-iam)

[4.4 Despliegue de la API de plataforma
[13](#despliegue-de-la-api-de-plataforma)](#despliegue-de-la-api-de-plataforma)

[4.5 Capa de Servicios MCP
[13](#capa-de-servicios-mcp)](#capa-de-servicios-mcp)

[4.6 4.5 Capa de Inferencia (Proxy LiteLLM) y Modelos
[14](#capa-de-inferencia-proxy-litellm-y-modelos)](#capa-de-inferencia-proxy-litellm-y-modelos)

[4.7 Clúster de modelos locales (EKS + vLLM) / Modelos SaaS
[14](#clúster-de-modelos-locales-eks-vllm-modelos-saas)](#clúster-de-modelos-locales-eks-vllm-modelos-saas)

[4.8 4.7 Capa de datos (RDS/Aurora, OpenSearch, DocumentDB, Neptune)
[14](#capa-de-datos-rdsaurora-opensearch-documentdb-neptune)](#capa-de-datos-rdsaurora-opensearch-documentdb-neptune)

[4.9 ETL y cargas iniciales (Airflow): datasources & datastores
[14](#etl-y-cargas-iniciales-airflow-datasources-datastores)](#etl-y-cargas-iniciales-airflow-datasources-datastores)

[4.10 Interfaz de pruebas (Open WebUI) y conexión con Cognito
[14](#interfaz-de-pruebas-open-webui)](#interfaz-de-pruebas-open-webui)

[4.11 Monitorizacion y observabilidad
[15](#monitorizacion-y-observabilidad)](#monitorizacion-y-observabilidad)

[5 5. PROCEDIMIENTOS DE MANTENIMIENTO
[16](#procedimientos-de-mantenimiento)](#procedimientos-de-mantenimiento)

[5.1 Gestión de versiones y despliegues
[16](#gestión-de-versiones-y-despliegues)](#gestión-de-versiones-y-despliegues)

[5.2 Backups y restauración (RDS, OpenSearch, DocumentDB, EBS)
[16](#backups-y-restauración-rds-opensearch-documentdb-ebs)](#backups-y-restauración-rds-opensearch-documentdb-ebs)

[5.2.1 Bases de datos RDS
[16](#bases-de-datos-rds)](#bases-de-datos-rds)

[5.2.2 OpenSearch [16](#opensearch)](#opensearch)

[5.2.3 DocumentDB [16](#documentdb)](#documentdb)

[5.2.4 EBS [16](#ebs)](#ebs)

[5.3 Escalado y capacidad (EKS nodegroups, autoscaling de pods)
[17](#escalado-y-capacidad-eks-nodegroups-autoscaling-de-pods)](#escalado-y-capacidad-eks-nodegroups-autoscaling-de-pods)

[5.4 5.6 Gestión de costes y cuotas LLM (LiteLLM: RPM/TPM, budgets)
[17](#gestión-de-costes-y-cuotas-llm-litellm-rpmtpm-budgets)](#gestión-de-costes-y-cuotas-llm-litellm-rpmtpm-budgets)

[5.5 5.7 Rotación de secretos y certificados
[17](#rotación-de-secretos-y-certificados)](#rotación-de-secretos-y-certificados)

[5.6 Tareas de housekeeping (índices, snapshots, limpieza buckets)
[17](#tareas-de-housekeeping-índices-snapshots-limpieza-buckets)](#tareas-de-housekeeping-índices-snapshots-limpieza-buckets)

[5.7 5.9 Plan de continuidad y DR (RTO/RPO, pruebas periódicas)
[17](#plan-de-continuidad-y-dr-rtorpo-pruebas-periódicas)](#plan-de-continuidad-y-dr-rtorpo-pruebas-periódicas)

[6 6. BUENAS PRÁCTICAS [18](#buenas-prácticas)](#buenas-prácticas)

[6.1 Infraestructura como código y GitOps
[18](#infraestructura-como-código-y-gitops)](#infraestructura-como-código-y-gitops)

[6.2 Hardening de contenedores e imágenes (scanning)
[18](#hardening-de-contenedores-e-imágenes-scanning)](#hardening-de-contenedores-e-imágenes-scanning)

[6.3 Evaluación de prompts y guardrails (seguridad/privacidad)
[18](#evaluación-de-prompts-y-guardrails-seguridadprivacidad)](#evaluación-de-prompts-y-guardrails-seguridadprivacidad)

[6.4 6.6 Optimización de costes de inferencia y almacenamiento
[18](#optimización-de-costes-de-inferencia-y-almacenamiento)](#optimización-de-costes-de-inferencia-y-almacenamiento)

[7 7. CONFIGURACIONES DE SEGURIDAD
[19](#configuraciones-de-seguridad)](#configuraciones-de-seguridad)

[7.1 7.1 IAM (roles por servicio, permisos mínimos, separación de
duties)
[19](#permisos-roles-por-servicio-permisos-mínimos-separación-de-duties)](#permisos-roles-por-servicio-permisos-mínimos-separación-de-duties)

[7.2 7.2 Red (SG, NACL, TLS, ALB/WAF/Shield)
[19](#red-sg-nacl-tls-albwafshield)](#red-sg-nacl-tls-albwafshield)

[7.3 7.3 Cifrado en reposo (KMS) y en tránsito (TLS 1.2+)
[19](#cifrado-en-reposo-kms-y-en-tránsito-tls-1.2)](#cifrado-en-reposo-kms-y-en-tránsito-tls-1.2)

[7.4 7.4 Política de secretos (Secrets Manager, rotación, uso en tiempo
de ejecución)
[19](#política-de-secretos-secrets-manager-rotación-uso-en-tiempo-de-ejecución)](#política-de-secretos-secrets-manager-rotación-uso-en-tiempo-de-ejecución)

[7.5 7.5 Auditoría y logs (API, MCP, inferencia, acceso a datos)
[19](#auditoría-y-logs-api-mcp-inferencia-acceso-a-datos)](#auditoría-y-logs-api-mcp-inferencia-acceso-a-datos)

[7.6 7.6 Gestión de vulnerabilidades (parcheo base, escaneo continuo)
[19](#gestión-de-vulnerabilidades-parcheo-base-escaneo-continuo)](#gestión-de-vulnerabilidades-parcheo-base-escaneo-continuo)

[7.7 7.7 DLP y cumplimiento (GDPR/ISO27001/NIST)
[20](#dlp-y-cumplimiento-gdpriso27001nist)](#dlp-y-cumplimiento-gdpriso27001nist)

[8 8. OPERACIÓN DIARIA (RUNBOOKS)
[21](#operación-diaria-runbooks)](#operación-diaria-runbooks)

[8.1 8.1 Paneles de servicio y verificación diaria
[21](#paneles-de-servicio-y-verificación-diaria)](#paneles-de-servicio-y-verificación-diaria)

[8.2 8.2 Gestión de alertas y respuesta a incidentes
[21](#gestión-de-alertas-y-respuesta-a-incidentes)](#gestión-de-alertas-y-respuesta-a-incidentes)

[8.3 8.3 Playbooks de incidencias comunes
[21](#playbooks-de-incidencias-comunes)](#playbooks-de-incidencias-comunes)

[8.4 8.4 Procedimientos de emergencia y rollback
[21](#procedimientos-de-emergencia-y-rollback)](#procedimientos-de-emergencia-y-rollback)

[9 9. MATRIZ RACI [22](#_Toc219807008)](#_Toc219807008)

[9.1 9.1 Responsabilidades por función (Ops, Sec, Data, ML, Producto)
[22](#_Toc219807009)](#_Toc219807009)

[10 10. ANEXOS [23](#anexos)](#anexos)

[10.1 Checklists de instalación y post-despliegue
[23](#_Toc219807011)](#_Toc219807011)

[10.2 Plantillas de cambios (RFC/CAB)
[23](#plantillas-de-cambios-rfccab)](#plantillas-de-cambios-rfccab)

[10.3 Glosario y referencias
[23](#glosario-y-referencias)](#glosario-y-referencias)

# INTRODUCCIÓN

## Objetivo y alcance

## Términos y acrónimos

## Contexto arquitectónico 

La solución establece una plataforma modular de IA para ciberseguridad
consumible exclusivamente vía API, evitando desarrollar una interfaz
pesada y permitiendo combinar casos de uso, herramientas y modelos con
flexibilidad. Para pruebas se usa una interfaz ligera basada en Open
WebUI cuando la entrada es texto y UIs mínimas cuando el caso lo exige,
sin desviar el foco del núcleo de la plataforma.

Arquitectónicamente, se organiza en capas bien definidas: (1) una API de
casos de uso como único punto de ejecución y orquestación; (2)
autenticación e IAM con AWS Cognito (extensible a IdP externos) para
controlar identidad y grupos; (3) servicios MCP como catálogo y bus de
integración de herramientas y casos de uso; y (4) una capa de permisos
por dominios de conocimiento que limita la visibilidad y la ejecución
por usuario.

El modelo de datos separa claramente "qué" se gestiona de "cómo" se
almacena. Los dominios de datos agrupan datasources y se asocian a
usuarios o grupos (con opción de dominios "públicos"). Los datasources
son la unidad mínima de permiso y agrupan datos homogéneos en formato y
contexto. Los datastores son las materializaciones físicas (p. ej.,
tabla en RDS/Aurora para estructurados, índice en OpenSearch para
vectores, o S3 para documentos). Esta separación facilita la
multitenencia y el control de acceso coherente por cliente o ámbito.

El patrón de recuperación combina filtrado estructurado y RAG: primero
se acotan candidatos en SQL (por producto, versión, etc.) y luego se
refina con búsqueda vectorial sobre texto no estructurado para evaluar
la mejor correspondencia semántica.

Para la integración de capacidades, la plataforma adopta el estándar
Model Context Protocol (MCP), que reduce el problema M×N de
integraciones a M+N y permite a los LLMs acceder a datos, desencadenar
acciones y mantener contexto. Dado que MCP aún presenta limitaciones
(autenticación, registro centralizado de servidores, manejo de
credenciales), la arquitectura incorpora un proxy/registro propio:
centraliza el listado e invocación de MCPs (SSE o stdio), controla
permisos por usuario, permite "levantar" servidores dinámicamente con
parámetros seguros y propaga el token de sesión a lo largo de la cadena
de llamadas.

Como evolución natural, se contempla el paso a un modelo multiagente
donde un agente principal coordina agentes expertos. Se mantiene abierta
la investigación sobre el protocolo A2A (Agent‑to‑Agent) para la
interoperabilidad entre agentes, sin afectar el alcance actual.

La inferencia se centraliza mediante un proxy LiteLLM (API compatible
con OpenAI) que unifica el acceso a modelos locales y en cloud, ofrece
rate limiting, medición/coste y control por usuario. Se exponen
endpoints tipo chat/completions como interfaz estándar. Conviven modelos
SaaS (Gemini, GPT, Claude vía Bedrock) con modelos locales servidos
sobre vLLM en EKS/ALB para optimizar coste y latencia.

El API de la plataforma agrupa capacidades de inferencia, gestión de
usuarios/autenticación, permisos, servicios (listar/invocar MCP) y datos
(listar/gestionar datasources y dominios). Este diseño sitúa a la API
como único "gate" para control, monitorización y auditoría.

La seguridad se aborda en tres frentes: (1) perímetro con AWS WAF y
Shield Standard; (2) acceso a datastores mediante Security Groups, roles
IAM desde contenedores y Secrets Manager para credenciales; y (3)
cifrado en reposo y en tránsito (EBS, RDS, OpenSearch, DocumentDB y
Neptune) gestionado con KMS.

La observabilidad unifica logs en CloudWatch (OpenSearch, Aurora
MySQL/PostgreSQL, DocumentDB, contenedores EC2/EKS), mientras que los
access logs de ALB se almacenan en S3 y pueden analizarse con Athena.

En conjunto, la plataforma se apoya en un único punto de entrada (API),
control de permisos por dominio/datasource, proxy MCP y proxy de
inferencia. Este enfoque proporciona seguridad de extremo a extremo,
trazabilidad operativa, intercambiabilidad de modelos y escalabilidad
sin modificar los casos de uso, alineando el desarrollo con buenas
prácticas de ingeniería y operación.

# 2. GOBERNANZA OPERATIVA

## Modelo RACI

El modelo RACI que se presenta a continuación detalla las
responsabilidades relacionadas con la evolución y el desarrollo del
entorno de la plataforma. La aplicación, concebida con una naturaleza
abierta y acceso exclusivo a través de API, dificulta la inclusión de
los consumidores en la asignación de roles dentro del RACI. No obstante,
se mantiene la presencia del equipo evaluador, que integra a las
entidades validadoras definidas en el proyecto, asegurando así la
supervisión y validación de los procesos implicados.

  --------------------------------------------------------------------------------
  Actividad /       Equipo de      Equipo de      Equipo de         Equipo
  Proceso           Desarrollo     Creación de    Infraestructura   Evaluador
                                   Casos de Uso                     
  ----------------- -------------- -------------- ----------------- --------------
  Análisis de       R              A              C                 I
  requisitos                                                        

  Diseño de         A              I              R                 C
  arquitectura                                                      

  Desarrollo de     R/A            C              I                 I
  funcionalidades                                                   

  Despliegue e      C              I              R/A               I
  integración                                                       

  Definición de     I              R/A            I                 C
  casos de uso                                                      

  Evaluación de     I              C              I                 R/A
  resultados                                                        
  --------------------------------------------------------------------------------

R: Responsable    A: Aprobador    C: Consultado    I: Informado

## Gestión del cambio

Al tratarse de un proyecto de investigación que no produce una
plataforma en producción final, hay ciertos aspectos como los
procedimientos de cambio que se contemplan de forma genérica. Aquí se
expone un procedimiento base de cambio que incluye sugerencias de
ventanas de cambio, procesos, etc.

El proceso de gestión de cambio en la aplicación se inicia con la
identificación y documentación de la necesidad de cambio. Esto puede
originarse a raíz de nuevas funcionalidades, corrección de errores,
actualizaciones de seguridad o mejoras en el rendimiento. Una vez
detectada la necesidad, se elabora una solicitud de cambio que debe ser
revisada por el equipo responsable, quienes evalúan el impacto potencial
en el resto del sistema y la viabilidad técnica de la propuesta.

Tras la evaluación inicial, el siguiente paso consiste en planificar la
implementación del cambio. Esta fase incluye la definición de las tareas
necesarias, la asignación de recursos y la programación de una ventana
de cambio que minimice el impacto en los usuarios. Es fundamental
comunicar a todas las partes interesadas el alcance y la programación
del cambio, asegurando que todos los equipos estén informados y
preparados para cualquier eventualidad durante el proceso.

Para este propósito se utilizará una herramienta de gestión de tickets a
través de la cual se informará el cambio. Además, podrá vincularse a
otros problemas identificados o solicitudes relacionadas.

El siguiente paso consiste en definir una ventana de cambio, la cual
será negociada con las partes involucradas según lo establecido en
nuestra matriz RACI previamente mencionada. Es imprescindible obtener la
aprobación de todos los interesados antes de programar la intervención
de modificación, asegurando que exista un margen temporal suficiente
para su ejecución. Este periodo debe considerar la posibilidad de
imprevistos, por lo que habitualmente no se utiliza la totalidad de la
ventana de cambio.

Finalmente, una vez ejecutado el cambio, se realiza una validación para
verificar que los objetivos se han cumplido sin afectar negativamente a
otras áreas de la aplicación. Se documentan los resultados y, en caso de
detectar incidencias, se activa un plan de contingencia previamente
definido. Todo el proceso queda registrado para futuras auditorías y
para facilitar la mejora continua en la gestión de cambios dentro del
proyecto.

## KPIs e indicadores

Al tratarse de un proyecto de investigación que establece un RTL7 y no
un entorno productivo, no se ofrecerán aquí los valores concretos de
SLAs o KPIS sino un listado de elementos que se consideran importantes
en el salto a producción de esta plataforma.

### Tiempo de disponibilidad 

El tipo de indicador que evalúa el tiempo de disponibilidad de una
plataforma en producción se denomina generalmente SLA (Acuerdo de Nivel
de Servicio) de disponibilidad o, en un enfoque más técnico, SLI
(Indicador de Nivel de Servicio) de disponibilidad. Este indicador mide
el porcentaje de tiempo durante el cual la plataforma está operativa y
accesible para los usuarios finales, comparado con el tiempo total en un
periodo determinado. Un valor típico de disponibilidad en entornos
productivos suele expresarse como un porcentaje anual, por ejemplo,
99,9%, lo que implica un tiempo máximo permitido de inactividad o caídas
no planificadas durante el año.

El objetivo de este indicador es asegurar que la plataforma cumple con
los compromisos de servicio acordados y que los usuarios pueden acceder
al sistema de manera fiable. En caso de que la disponibilidad caiga por
debajo del umbral establecido, pueden aplicarse penalizaciones o planes
de mejora según lo definido en el SLA.

### RTO

El RTO, o \"Recovery Time Objective\" (Objetivo de Tiempo de
Recuperación), es un indicador clave en la gestión de servicios y
plataformas tecnológicas que define el tiempo máximo permitido para
restaurar la operatividad de un servicio tras una interrupción o
incidente. En otras palabras, el RTO establece el plazo en el que se
debe recuperar la funcionalidad mínima aceptable del sistema para
minimizar el impacto negativo en los usuarios y en el negocio. Este
parámetro se negocia y acuerda previamente entre todas las partes
interesadas, y suele estar incluido en los Acuerdos de Nivel de Servicio
(SLA).

La correcta definición del RTO permite planificar los recursos y
procedimientos necesarios para afrontar situaciones de contingencia,
asegurando que el equipo responsable conoce los tiempos límite y las
prioridades de actuación. Además, el cumplimiento del RTO está
directamente relacionado con la percepción de calidad y fiabilidad del
servicio por parte de los usuarios. Un RTO demasiado largo puede
provocar pérdidas económicas y de reputación, mientras que uno demasiado
corto puede requerir inversiones significativas en infraestructura y
personal para garantizar la recuperación en el plazo establecido.

### RPO

El RPO, o \"Recovery Point Objective\" (Objetivo de Punto de
Recuperación), es un indicador fundamental en la gestión de servicios
tecnológicos que determina la cantidad máxima de datos que se puede
perder en caso de una interrupción o desastre antes de que afecte
significativamente al negocio. En otras palabras, el RPO define el
intervalo de tiempo entre la última copia de seguridad válida y el
momento en que ocurre el incidente, estableciendo así cuánto tiempo
puede transcurrir sin que se realice una copia de los datos sin poner en
riesgo la operatividad o la integridad de la información. Una correcta
definición del RPO permite dimensionar las estrategias de respaldo y
recuperación, adaptando la frecuencia de las copias de seguridad a las
necesidades y tolerancia al riesgo de la organización.

### Tiempos de respuesta

El tiempo de respuesta debe mantenerse constante y dentro de parámetros
predecibles durante las interacciones. Si bien no es posible especificar
un valor fijo para casos de uso complejos, sí se pueden establecer
tiempos máximos para procesos intermedios, como el acceso a datos y
otros endpoints de la API de la plataforma que no presenten variabilidad
significativa. La solución contempla distintos procesos, por lo tanto,
es necesario definir tiempos de respuesta máximos para cada endpoint y
posteriormente realizar una monitorización periódica para asegurar el
cumplimiento de dichos estándares.

La monitorización continua de estos tiempos es esencial para la
detección temprana de desviaciones y la adopción de medidas correctivas,
lo que permite mantener la experiencia de usuario dentro de los
parámetros esperados y asegurar la calidad del servicio. Además, los
resultados obtenidos de estos controles deberán integrarse en los
procesos de validación antes de cualquier despliegue en producción,
garantizando la alineación con los estándares definidos y facilitando la
toma de decisiones sobre ajustes en la arquitectura o en la asignación
de recursos. De esta forma, se refuerza la robustez del sistema y se
minimizan los riesgos de degradación del rendimiento en operaciones
críticas.

# ENTORNOS, PRE-REQUISITOS Y CONTROLES

Como se mencionó en etapas anteriores, debido a que este proyecto de
investigación propone un sistema previo a la fase de productividad, es
posible que algunos de los elementos planificados o descritos
posteriormente aún no estén presentes en el entorno TRL7 planteado. No
obstante, el diseño y la concepción de la aplicación permiten
implementar todas estas medidas y buenas prácticas.

Así, el enfoque adoptado en esta fase garantiza que, a medida que el
entorno evolucione hacia niveles superiores de madurez y productividad,
todas las prácticas y controles definidos podrán integrarse de forma
progresiva y efectiva. De este modo, se facilita la transición hacia una
arquitectura robusta y alineada con los requisitos de calidad y
seguridad establecidos, asegurando que tanto los procesos de despliegue
como los mecanismos de validación y monitorización respondan a las
exigencias del entorno productivo. Esta visión anticipa y respalda la
futura consolidación de entornos diferenciados y la implementación de
estrategias de aislamiento, control y automatización que son
fundamentales para la estabilidad y la fiabilidad del sistema.

## Entornos y aislamiento

El desarrollo de la plataforma se basa en la existencia de dos entornos
diferenciados: preproducción (pre) y producción (pro), cada uno con
características y grados de flexibilidad distintos. El código fuente se
gestiona mediante ramas (branches) en un repositorio GIT, lo que permite
mantener separadas las versiones en desarrollo y las versiones estables,
facilitando así la colaboración y el control de cambios.

Para el despliegue de la plataforma y la gestión de la infraestructura
se utiliza Terraform. En el entorno de preproducción, se permite mayor
flexibilidad para realizar pruebas, ajustes y validaciones de nuevas
funcionalidades, ya que aquí es habitual experimentar con
configuraciones y cambios que posteriormente serán revisados antes de
pasar a producción. Por el contrario, el entorno de producción está
configurado para ser más restrictivo y estable, minimizando los cambios
directos y limitando las actualizaciones a aquellas previamente
validadas en pre. Esto garantiza la seguridad, fiabilidad y continuidad
del servicio en el entorno crítico para el negocio.

Las modificaciones en la infraestructura mediante Terraform se llevarán
a cabo durante las ventanas de mantenimiento, según lo establecido
previamente en el documento.

Las diferencias entre ambos entornos no solo afectan a la flexibilidad
de los despliegues, sino también a la gestión de permisos,
monitorización y validaciones automáticas, asegurando que cualquier
cambio significativo pase por un proceso de revisión y pruebas
exhaustivas antes de ser implementado en producción.

## Cuentas Cloud y estrategia de portabilidad

La plataforma está diseñada como una solución robusta y flexible,
preparada para afrontar la indisponibilidad o degradación de cualquier
región de AWS en Europa, sin que ello comprometa el cumplimiento de las
normativas de protección de datos. Se utiliza exclusivamente regiones
europeas que garantizan la total adherencia al RGPD, manteniendo siempre
la soberanía y protección de la información.

La arquitectura implementada contempla redundancia tanto a nivel de
servicios como de datos, asegurando que todos los componentes ---bases
de datos, almacenamiento, cómputo, gestión de identidades y secretos---
están listos para replicarse y restaurarse en regiones alternativas en
caso de contingencia. Toda la infraestructura se define y opera bajo
principios de automatización y portabilidad.

La gestión de accesos, permisos y credenciales es centralizada y
auditada. La replicación de datos y las copias de seguridad se realizan
bajo estrictos controles de cifrado y acceso restringido. La plataforma
incorpora una supervisión activa y monitorización continua de todos los
servicios, lo que permite la detección temprana de incidentes y la
reacción proactiva ante cualquier riesgo operacional o de seguridad.

El diseño de políticas y procedimientos minimiza el impacto sobre la
experiencia de las personas usuarias durante operaciones de failover o
recuperación, y permite iterar sobre la arquitectura conforme
evolucionan las necesidades del negocio, las tecnologías y los marcos
regulatorios.

La plataforma sostiene su funcionamiento ante eventos adversos, mantiene
la calidad del servicio y facilita la rápida migración entre regiones
europeas, todo ello bajo un marco de cumplimiento normativo y mejora
continua.

**Amazon Cognito**: Para portar la plataforma entre regiones, conviene
exportar y versionar las configuraciones de grupos de usuarios y
clientes de aplicaciones en Cognito, utilizando plantillas automatizadas
y scripts que aseguren la consistencia en permisos, políticas y flujos
de autenticación. Es recomendable establecer una replicación segura de
atributos sensibles y sincronizar los endpoints de autenticación,
minimizando la dependencia de recursos regionales.

**AWS WAF**: La migración de reglas y configuraciones de AWS WAF debe
realizarse mediante IaC (Infrastructure as Code), permitiendo reproducir
políticas de seguridad y listas de control de acceso en cualquier
región. Mantener reglas globales y automatizar la actualización de
listas de IPs maliciosas facilita la portabilidad y reduce el riesgo de
brechas en nuevas ubicaciones.

**AWS Shield Standard**: La activación de AWS Shield Standard es
automática en todas las regiones, pero resulta clave revisar las
configuraciones de notificación y respuesta ante ataques DDoS. Se
recomienda documentar los procedimientos de escalado y asegurarse de que
los recursos protegidos estén correctamente etiquetados y monitorizados
en cada región de destino.

**Amazon CloudFront**: Al usar CloudFront, la portabilidad se facilita
gracias a sus puntos de presencia globales. Sin embargo, es esencial
actualizar los orígenes y endpoints tras la migración, validar las
configuraciones de distribución y optimizar las políticas de caché para
cada región, garantizando una experiencia rápida y segura para los
usuarios.

**AWS IAM**: Centralizar la gestión de roles y políticas con IAM
facilita la portabilidad. Es recomendable automatizar la creación y
replicación de grupos, roles y permisos, garantizando que los controles
de acceso permanezcan auditables y consistentes al migrar entre
regiones, además de revisar y actualizar los ARN referenciados. Para
ello, se recomienda utilizar Terraform como herramienta de
Infrastructure as Code (IaC), permitiendo definir y versionar la
configuración de IAM en archivos declarativos. Con Terraform, es posible
desplegar y replicar de manera automatizada los recursos de IAM en
distintas regiones, asegurando la coherencia, trazabilidad y la
posibilidad de auditar cualquier cambio en la gestión de identidades y
accesos.

**AWS Secrets Manager**: Para portar secretos y credenciales, se deben
emplear scripts y plantillas que permitan exportar e importar datos
cifrados, manteniendo la rotación automática y las políticas de acceso
en la nueva región. Es importante validar la compatibilidad de los
endpoints y revisar logs de auditoría tras la migración.

**Amazon RDS**: La migración de bases de datos RDS puede realizarse
mediante snapshots y réplicas cruzadas entre regiones. Es fundamental
verificar la configuración de parámetros, cifrado y backups, así como
adaptar los endpoints de conexión y las políticas de acceso para
mantener la seguridad y disponibilidad.

**Amazon Aurora MySQL**: Para Aurora MySQL, se puede usar un enfoque
similar usando backups pero considerando sus capacidades nativas, se
recomienda usar la funcionalidad multi-región y automatizar la
replicación de clústeres, garantizando la integridad y consistencia de
los datos. Es conveniente monitorizar el estado de la replicación y
preparar procedimientos de failover para minimizar el tiempo de
recuperación.

**Amazon Aurora PostgreSQL**: Similar a Aurora MySQL, Aurora PostgreSQL
se beneficia de la replicación entre regiones y el uso de snapshots
automáticos. Es recomendable validar la compatibilidad de las versiones
y configurar alertas para detectar posibles desviaciones o
interrupciones en la sincronización.

**Amazon S3**: Para asegurar la portabilidad de los datos en S3, se
recomienda habilitar la replicación entre buckets de distintas regiones,
cifrar los objetos y revisar las políticas de acceso. Mantener la
consistencia de los nombres y etiquetas facilita la gestión y
recuperación ante contingencias.

**Amazon OpenSearch**: La migración de índices y clústeres OpenSearch
requiere planificar la exportación/importación de datos y
configuraciones, empleando snapshots y scripts automatizados. Es
importante validar la compatibilidad de plugins y asegurarse de que las
políticas de acceso y monitorización se mantengan tras el traslado.

**Amazon Neptune**: Para portar bases de datos de grafos Neptune, se
recomienda utilizar backups automáticos y scripts de restauración en la
región destino, asegurando la integridad de los datos y las
configuraciones de red. Es esencial revisar la conectividad y los roles
asociados tras la migración.

**Amazon EBS**: La portabilidad de volúmenes EBS se gestiona mediante
snapshots y copias entre regiones. Se aconseja automatizar el proceso y
validar la compatibilidad de tipos de volumen, cifrado y etiquetas,
manteniendo los procedimientos de restauración documentados y probados.

**Amazon EKS**: Para Kubernetes gestionado con EKS, se recomienda
definir los clústeres y recursos mediante manifiestos IaC, facilitando
el despliegue en cualquier región. Es esencial replicar configuraciones,
secretos y volúmenes persistentes, además de adaptar los endpoints y
políticas de acceso según la región.

**Amazon EC2**: La migración de instancias EC2 requiere crear AMIs y
copiar imágenes a la región destino, automatizando la provisión de
recursos y revisando las configuraciones de red, seguridad y
almacenamiento. Es recomendable validar las dependencias y scripts de
inicialización para asegurar el correcto funcionamiento tras el
traslado.

**AWS Application Load Balancer (ALB):** Para migrar configuraciones de
ALB, se recomienda definir listeners, reglas y políticas mediante
plantillas IaC, facilitando su replicación en cualquier región. Si los
load balancers se crean desde despliegues EKS con ingress tipo ALB, no
es necesario migrarlos ya que Kubernetes los gestiona automáticamente en
cada entorno redundado.

**Amazon CloudWatch**: Para mantener la monitorización con CloudWatch,
al estar configurado en cada servicio directamente la creación de log
groups concretos, no es necesario replicar muchas configuraciones en
cloudwatch salvo alarmas, dashboards y métricas personalizadas mediante
scripts y plantillas IaC, asegurando la continuidad de la supervisión y
el envío de notificaciones en la nueva región. Validar la integración
con otros servicios es clave para la portabilidad operativa.

**Amazon CloudWatch**: Para asegurar la continuidad de la monitorización
con CloudWatch en migraciones entre regiones, dado que la configuración
de log groups está definida directamente en cada servicio, no resulta
necesario replicar la mayoría de las configuraciones en CloudWatch,
excepto en el caso de alarmas, paneles de control (dashboards) y
métricas personalizadas. Estas pueden ser gestionadas y reproducidas de
forma segura mediante scripts y plantillas de Infrastructure as Code
(IaC) desarrolladas específicamente con Terraform, garantizando así la
portabilidad de las configuraciones y el mantenimiento de las
notificaciones en la nueva región. Es fundamental validar la integración
con el resto de servicios relacionados para asegurar la operatividad en
el entorno migrado.

## Gestión de secretos y claves (KMS / Secrets Manager)

Gestión de secretos y claves (KMS / Secrets Manager): La gestión de
secretos y claves en AWS se apoya principalmente en dos servicios: AWS
Secrets Manager y AWS Key Management Service (KMS). Secrets Manager está
diseñado para almacenar, gestionar y rotar de forma segura secretos como
contraseñas, tokens de API y credenciales de bases de datos. Permite la
integración automática con otros servicios de AWS y la rotación
periódica de secretos, reduciendo así el riesgo de exposición. Los
secretos se cifran en reposo utilizando claves gestionadas por KMS,
garantizando una protección robusta.

Por otro lado, AWS KMS se encarga de la creación, almacenamiento y
control de acceso a las claves de cifrado utilizadas tanto por los
servicios de AWS como por aplicaciones propias. KMS facilita la
generación de claves maestras (CMK), la gestión de sus permisos mediante
políticas granulares y la auditoría de su uso a través de logs en
CloudTrail. Esto asegura que los datos sensibles permanezcan cifrados y
bajo un control estricto en todo momento.

Opcionalmente, se puede emplear un módulo de seguridad hardware (HSM)
externo, como AWS CloudHSM, para gestionar claves criptográficas fuera
del entorno gestionado por AWS, incrementando el nivel de control y
cumplimiento en escenarios que lo requieran. Este enfoque es
especialmente útil para organizaciones con requisitos regulatorios
estrictos o que deseen mantener la custodia total de sus claves. Además,
en entornos de infraestructura pública, donde existen restricciones de
seguridad más exigentes, esta medida resulta plenamente compatible y
recomendable, ya que permite cumplir con políticas avanzadas de
protección y segregación de claves, asegurando que la gestión
criptográfica se adapte a los estándares requeridos por el sector.

# 4. PROCEDIMIENTOS DE INSTALACIÓN

## Aprovisionamiento base

El aprovisionamiento de los elementos base de la infraestructura AWS de
la aplicación comienza por la creación de una VPC (Virtual Private
Cloud), que define el espacio de red aislado donde se desplegarán los
recursos. En primer lugar, se diseña la VPC especificando el rango de
direcciones IP (CIDR) y, a continuación, se crean las subredes públicas
y privadas según las necesidades de acceso y seguridad: las subredes
públicas suelen alojar componentes expuestos (como ALB), mientras que
las privadas protegen instancias y bases de datos.

Es fundamental configurar los Security Groups (SG), que actúan como
cortafuegos virtuales controlando el tráfico de entrada y salida a nivel
de recurso. Se definen reglas específicas para permitir únicamente el
tráfico necesario entre componentes, minimizando la superficie de
exposición. Adicionalmente, se implementan VPC Endpoints para facilitar
el acceso privado a servicios gestionados de AWS (como S3 o DynamoDB)
sin salir a Internet, reforzando la seguridad y reduciendo la latencia.

La implementación de estos recursos se realiza de manera controlada a
través de Terraform, con el objetivo de establecer una base sólida que
facilite la posterior configuración de los demás servicios.

La implementación de estos recursos se realiza de manera controlada a
través de Terraform, con el objetivo de establecer una base sólida que
facilite la posterior configuración de los demás servicios. Una vez
desplegada la infraestructura base, el siguiente paso consiste en
definir la capa de autenticación y gestión de identidades utilizando AWS
Cognito o integrando un proveedor de identidad externo mediante SAML u
OIDC, siguiendo un procedimiento detallado que incluye validaciones
específicas y la monitorización de KPIs y alertas asociadas para
garantizar la seguridad y el correcto funcionamiento del entorno.

## Capa de autenticación e IAM 

(Cognito / IdP SAML-OIDC si aplica

## Despliegue de la API de plataforma

Despliegue de los contenedores de la plataforma

## Capa de Servicios MCP 

Despliegue de los contenedores MCP y los agentes simples que saben
invocarlos

## Capa de Inferencia (Proxy LiteLLM) y Modelos

Despliegue de contenedores de litellm y configuración de las keys de
servicios cloud de modelos.

## Clúster de modelos locales (EKS + vLLM) / Modelos SaaS

Configuracion de Kubernetes con addons de Nvidia para uso de gpu y time
slicing.

## Capa de datos (RDS/Aurora, OpenSearch, DocumentDB, Neptune)

Configuracion básica de Bases de datos para que la aplicación pueda
usarlos. Almacenamiento en Secrets de credenciales o facilitar su uso
con roles AWS.

## ETL y cargas iniciales (Airflow): datasources & datastores

El proceso de carga de ETL se orquesta desde un pipeline de Azure DevOps
que automatiza el despliegue continuo (CI/CD) de los flujos de trabajo
hacia el entorno de Amazon MWAA (Airflow). Se activa automáticamente
cuando hay cambios en la rama main del repositorio ucap_etl, que
contiene los distintos DAGs, y utiliza un agente con Ubuntu para
interactuar con los servicios de AWS, usando credenciales almacenadas en
variables de entorno para autenticarse y acceder al bucket S3 vinculado
al entorno.

La primera tarea es la sincronización de los DAGs. El script copia la
carpeta local de DAGs al bucket S3, asegurándose de subir los archivos
nuevos y eliminar aquellos que hayan sido borrados en el repositorio.
Esta acción es ligera y no interrumpe el servicio, ya que MWAA detecta
automáticamente los cambios en los archivos de definición de procesos
sin necesidad de reiniciar.

El siguiente paso ejecuta una lógica de optimización para dependencias y
plugins. Antes de subir nada, el pipeline descarga los archivos
requirements.txt y plugins.zip actuales desde S3 y los compara con el
código local. Solo si detecta diferencias reales (usando el comando
diff), procede a empaquetar y subir las nuevas versiones a S3. Esto
evita actualizaciones innecesarias del entorno, las cuales suelen tardar
entre 15 y 30 minutos.

Finalmente, si se detectaron cambios en los plugins o requisitos, el
script gestiona la actualización del entorno MWAA. Obtiene los IDs de
versión de los nuevos objetos en S3 y entra en un bucle de reintentos
para verificar que el estado del entorno sea AVAILABLE. Una vez
confirmado que el entorno está listo, lanza el comando de actualización
para que Airflow instale las nuevas librerías o plugins, garantizando un
despliegue seguro y controlado.

En resumen, solo necesita capturar los DAG de un bucket S3 y verificar
su funcionamiento, todo desde la interfaz de configuración.

## Interfaz de pruebas (Open WebUI) 

Despliegue de contenedor y modificaciones de look and feel

- **Actualización de iconografía**

  - Sustitución de los iconos originales de OpenWebUI por los iconos
    corporativos de Deloitte.El cambio afecta tanto al icono mostrado en
    la parte superior de la barra lateral como al icono del chat.

  - El ajuste de iconos es inmediato en la mayoría de los casos, con la
    excepción del icono del título de la pestaña del navegador.

- **Cambio de nombre de la aplicación**

  - Actualización del nombre de la aplicación.

- **Actualización de identidad visual**

  - Incorporación del color corporativo de Deloitte (verde #86bc25) en
    los siguientes elementos:

    - Selector de modelo.

    - Modelo seleccionado dentro del chat.

    - Sugerencias mostradas en la interfaz.

- **Incorporación de texto informativo en la cabecera**

  - Añadido un texto entre el selector de modelo y la configuración de
    usuario (zona superior central).

- **Restricción de funcionalidades no deseadas**

  - Eliminación de la barra situada bajo el campo de entrada de
    *prompts* que permite la subida de ficheros.

  - Eliminación de la sección de *Code Interpreter.*

- **Incorporación de logotipo institucional**

  - Añadido el logotipo de Incibe en la parte inferior izquierda de la
    interfaz.

## Monitorizacion y observabilidad

Despliegue del Phoenix arize, configuración de la api contra el servicio
de Phoenix.

Cloudwatch, log groups y configuracion de la rotación de logs para
evitar problemas de disco.

# 5. PROCEDIMIENTOS DE MANTENIMIENTO

## Gestión de versiones y despliegues

Como en secciones anteriores, se presenta un proceso alineado con el
entorno operativo. Dado que se trata de un entorno TRL 7 previo a la
fase de producción, este proceso comparte ciertas similitudes con el
desarrollado durante la etapa de investigación; sin embargo, no es
idéntico, ya que las actividades relacionadas con flujos de producción y
releases corresponden a un servicio productivo y se encuentran fuera del
alcance del presente proyecto. Algunas similitudes se basan en
herramientas usadas como azure devops, terraform, etc, pero el proceso
no exacto por las diferencias de alcance.

El proceso de gestión de versiones para el software con infraestructura
asociada se fundamenta en una planificación semestral de releases,
garantizando la continuidad y la estabilidad de los servicios
desplegados en la nube. Cada ciclo de versión comienza con la
identificación de los cambios necesarios en el código y la
infraestructura, abarcando múltiples repositorios alojados en Azure
DevOps. Estos repositorios contienen tanto los componentes de aplicación
como los scripts de automatización y configuración de infraestructura.

Para asegurar la calidad y minimizar riesgos, el plan contempla un
entorno de preproducción donde se realiza el despliegue previo a la
liberación en producción. Este entorno replica las condiciones del
entorno final, permitiendo validar los cambios en un escenario
controlado. El despliegue en AWS se realiza utilizando Terraform, lo que
facilita la gestión declarativa de la infraestructura y el versionado de
los recursos cloud.

La coordinación entre los equipos de desarrollo e infraestructura es
esencial durante el proceso de integración. Cada modificación en los
repositorios de Azure DevOps se somete a revisión y pruebas automáticas,
integrando pipelines que verifican la correcta ejecución de los cambios
propuestos. Además, se utiliza la integración continua para detectar
posibles incidencias en etapas tempranas del ciclo de vida del software.

Previo al salto a producción, se ejecuta un set de pruebas de
funcionalidad básicas en el entorno de preproducción. Estas pruebas
comprueban la operatividad de los servicios principales, la conectividad
entre componentes y la correcta provisión de recursos en AWS. El
objetivo es asegurar que los cambios no introducen regresiones ni
afectan a las funcionalidades críticas del sistema.

Una vez validados los resultados, se planifica la fecha de release
semestral, coordinando el salto a producción con todos los equipos
implicados. El despliegue en producción sigue las mismas pautas que en
preproducción, utilizando Terraform para aplicar los cambios de forma
segura y trazable. En caso de incidencias, se cuenta con mecanismos de
rollback automatizados que permiten revertir rápidamente a una versión
estable anterior.

La documentación de cada release incluye un registro detallado de los
cambios realizados en los repositorios, los resultados de las pruebas de
funcionalidad y las incidencias detectadas durante el proceso. Este
histórico facilita la trazabilidad y el seguimiento de la evolución del
software e infraestructura. Además, se revisan periódicamente los
procedimientos para incorporar mejoras y adaptarse a nuevas necesidades
tecnológicas o normativas.

Por último, el proceso contempla la monitorización continua de los
entornos tras cada salto a producción, utilizando herramientas de
observabilidad integradas en AWS. Esto permite detectar posibles
problemas de forma proactiva y garantizar la disponibilidad y el
rendimiento del sistema, consolidando así un ciclo de versiones robusto
y alineado con las mejores prácticas de DevOps.

## Backups y restauración (RDS, OpenSearch, DocumentDB, EBS)

La estrategia general de backups en AWS se fundamenta en el uso de AWS
Backup como servicio centralizado para la gestión y automatización de
copias de seguridad de recursos cloud. AWS Backup permite definir
políticas de backup recurrentes, programar ventanas de respaldo y
gestionar la retención, facilitando la restauración en caso de pérdida
de datos o incidentes. Para garantizar un RPO (Recovery Point Objective)
de 24 horas, se recomienda programar los backups completos de manera
diaria, combinando las capacidades de AWS Backup con mecanismos nativos
de snapshot y exportación según el tipo de recurso.

### Bases de datos RDS

Para Amazon RDS, la estrategia óptima consiste en habilitar los backups
automáticos diarios mediante AWS Backup, complementados por snapshots
manuales antes de operaciones críticas. Se recomienda configurar una
ventana de backup que asegure la ejecución diaria, ajustando la
retención según los requisitos normativos y operativos. Además, es
posible exportar snapshots a S3 para mayor durabilidad y movilidad entre
regiones. Esta configuración permite restaurar la base de datos a
cualquier punto dentro de las últimas 24 horas, cumpliendo el RPO
establecido.

### OpenSearch

En el caso de OpenSearch, la estrategia de backup se basa en la
utilización de AWS Backup junto con los snapshots automáticos del propio
servicio. Se debe programar la toma de snapshots diarios de cada índice,
almacenándolos en buckets de S3 gestionados por políticas de ciclo de
vida. Asimismo, se recomienda validar periódicamente la integridad de
los backups y automatizar la restauración en entornos de pruebas. Así se
asegura la recuperación de datos hasta el último snapshot diario,
manteniendo el RPO de 24 horas.

### DocumentDB

Para DocumentDB, se debe habilitar la funcionalidad de snapshots
automáticos diarios y gestionar los backups a través de AWS Backup para
centralizar la administración y la retención. Es recomendable realizar
backups manuales antes de cambios mayores en la configuración o
actualizaciones críticas. Los backups automáticos permiten restaurar la
base de datos a cualquier momento dentro de las últimas 24 horas,
garantizando el cumplimiento del RPO definido.

### EBS

La estrategia de backup para volúmenes EBS se basa en la programación de
snapshots diarios con AWS Backup, asegurando que cada volumen crítico
está cubierto por una política de respaldo automatizada. Se aconseja
definir etiquetas para identificar volúmenes esenciales y aplicar
políticas de retención que permitan conservar los backups durante el
tiempo requerido. Esta aproximación garantiza la recuperación de los
datos almacenados en EBS hasta el último snapshot diario, alineándose
con el objetivo de RPO de 24 horas.

## Escalado y capacidad (EKS nodegroups, autoscaling de pods)

En el sistema actual, el despliegue de Amazon EKS (Elastic Kubernetes
Service) con nodegroups gestionados ya está implementado en producción,
lo que garantiza la escalabilidad y resiliencia de los clústeres de
Kubernetes en AWS. Los nodegroups se han definido con características
homogéneas, lo que facilita la administración, actualización y escalado
de los recursos subyacentes. Para optimizar el uso de los recursos y
asignar cargas de trabajo específicas, se han aplicado etiquetas y
taints adecuados en cada nodegroup, permitiendo un control preciso sobre
la distribución de los servicios.

El autoscaling de pods y nodos está configurado para responder
dinámicamente a las variaciones en la demanda de las aplicaciones. En
producción, Kubernetes Horizontal Pod Autoscaler (HPA) ajusta de manera
automática el número de pods según métricas como el uso de CPU y
memoria, mientras que Cluster Autoscaler incrementa o reduce el número
de nodos en función de la carga global del clúster. Los umbrales han
sido calibrados para evitar tanto el sobreaprovisionamiento como la
falta de recursos, y el comportamiento del autoscaling se monitoriza de
forma continua para mantener la eficiencia operativa.

Actualmente, el sistema integra addons como EBS CSI Driver para la
gestión eficiente de volúmenes persistentes, lo que facilita la
provisión dinámica de discos EBS para los pods según las necesidades de
cada servicio. Asimismo, el addon AWS Load Balancer Controller (ALB)
automatiza la creación y gestión de balanceadores de carga de
aplicación, mejorando la disponibilidad y escalabilidad del tráfico
externo hacia los servicios desplegados en EKS. Todos estos addons se
instalaron siguiendo las guías oficiales y se configuran periódicamente
para asegurar el cumplimiento de los requisitos de seguridad y
rendimiento.

En aquellos entornos donde se requieren capacidades de computación
acelerada, ya se ha implantado el NVIDIA Operator para gestionar nodos
con GPU. Este operador se encarga de instalar los drivers y el runtime
de NVIDIA, permitiendo la ejecución eficiente de cargas de trabajo de
inteligencia artificial y procesamiento intensivo en el clúster. Los
nodegroups destinados a GPU se mantienen reservados y las políticas de
scheduling garantizan un aprovechamiento óptimo de estos recursos
especializados.

Como parte de las buenas prácticas de escalado horizontal adoptadas en
producción, se utiliza Karpenter, el autoscaler open source de AWS, que
permite escalar automáticamente los nodos del clúster EKS de forma
rápida y eficiente, aprovisionando instancias óptimas según las
necesidades de los pods. Karpenter se combina con las herramientas
nativas de Kubernetes, como HPA y Cluster Autoscaler, para lograr una
arquitectura elástica, resiliente y coste-eficiente.

## Gestión de costes y cuotas LLM (LiteLLM: RPM/TPM, budgets)

> Hablar del contro y configuración de costes, de como dar de alta api
> keys y usuarios en la plataforma y como controlar sus consumos.

## Rotación de secretos y certificados

Hablar de buenas practicas de rotación y de como se debe actualizar
también en secrets manager cualquier pass.

## Tareas de housekeeping (índices, snapshots, limpieza buckets)

> Evaluacion del tamaño de índices, configuración de retención variable
> para datasources,

## Plan de continuidad y DR (RTO/RPO, pruebas periódicas)

Plan básico que define la migración de una instancia a otra región en el
peor de los casos.

# BUENAS PRÁCTICAS

## Infraestructura como código y GitOps

> Mantener terraform actualizado en git, gestión de bugs y tareas con
> devops y git dentro de devops.

## Hardening de contenedores e imágenes (scanning)

> Uso de ECR para la gestión de imágenes y tags, incluye el scanning
> también de vulnerabilidades.

## Evaluación de prompts y guardrails (seguridad/privacidad)

> Plantear como añadir los guardrails en la capa de litellm, verificar
> que los guardrails no interfieren en las tareas agenticas.

## Optimización de costes de inferencia y almacenamiento

> Activacion de cache en litellm, limites para evitar consumos
> desproporcionados de inferencia en litellm

# 7. CONFIGURACIONES DE SEGURIDAD

## Permisos (roles por servicio, permisos mínimos, separación de duties)

> :

## Red (SG, NACL, TLS, ALB/WAF/Shield)

## Cifrado en reposo (KMS) y en tránsito (TLS 1.2+)

## Política de secretos (Secrets Manager, rotación, uso en tiempo de ejecución)

## Auditoría y logs (API, MCP, inferencia, acceso a datos)

> Descripción:
>
> Procedimiento paso a paso:
>
> Validaciones y salidas esperadas:
>
> KPIs/SLIs y alertas asociadas:

## Gestión de vulnerabilidades (parcheo base, escaneo continuo)

## DLP y cumplimiento (GDPR/ISO27001/NIST)

# 8. OPERACIÓN DIARIA (RUNBOOKS)

## Paneles de servicio y verificación diaria

## Gestión de alertas y respuesta a incidentes

## Playbooks de incidencias comunes

## Procedimientos de emergencia y rollback

# ANEXOS

## Plantillas de cambios (RFC/CAB)

## Glosario y referencias
