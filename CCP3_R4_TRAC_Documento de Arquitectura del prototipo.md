CPP3-R4 - TRAC

Solución de Arquitectura del Prototipo

Reto 04

# **ÍNDICE** {#índice .TOC-Heading}

[ÍNDICE DE TABLAS [5](#_Toc408386635)](#_Toc408386635)

[ÍNDICE DE ILUSTRACIONES [5](#_Hlk207785748)](#_Hlk207785748)

[1 INTRODUCCIÓN [8](#introducción)](#introducción)

[1.1 Propósito [8](#propósito)](#propósito)

[1.2 Audiencia [8](#audiencia)](#audiencia)

[1.3 Ámbito [8](#ámbito)](#ámbito)

[1.4 Características de la Solución Desarrollada
[11](#características-de-la-solución-desarrollada)](#características-de-la-solución-desarrollada)

[2 REQUISITOS [13](#requisitos)](#requisitos)

[3 DISEÑO TÉCNICO [15](#diseño-técnico)](#diseño-técnico)

[3.1 Descripción de la Solución Desarrollada
[15](#descripción-de-la-solución-desarrollada)](#descripción-de-la-solución-desarrollada)

[3.2 Diseño Lógico [19](#diseño-lógico)](#diseño-lógico)

[3.2.1 Módulos de la solución
[20](#módulos-de-la-solución)](#módulos-de-la-solución)

[3.2.2 Flujos de datos ^(REQ-0005)^
[21](#flujos-de-datos-req-0005)](#flujos-de-datos-req-0005)

[3.2.3 Otros elementos transversales de la solución
[28](#otros-elementos-transversales-de-la-solución)](#otros-elementos-transversales-de-la-solución)

[3.3 Modos de ejecución de la solución (online vs. histórico)
^(REQ-0005)\ (OBJ-0004)^
[29](#modos-de-ejecución-de-la-solución-online-vs.-histórico-req-0005-obj-0004)](#modos-de-ejecución-de-la-solución-online-vs.-histórico-req-0005-obj-0004)

[4 INGESTA BLOCKCHAINS [31](#ingesta-blockchains)](#ingesta-blockchains)

[4.1 Bitcoin [31](#bitcoin)](#bitcoin)

[4.2 Ethereum [32](#ethereum)](#ethereum)

[4.3 Polygon [34](#polygon)](#polygon)

[5 ENRIQUECIMIENTO DE INFORMACION
[36](#enriquecimiento-de-informacion)](#enriquecimiento-de-informacion)

[5.1 Tipos de integraciones soportados
[37](#tipos-de-integraciones-soportados)](#tipos-de-integraciones-soportados)

[5.2 Componentes funcionales
[40](#componentes-funcionales)](#componentes-funcionales)

[5.3 Agrupación de la información
[42](#agrupación-de-la-información)](#agrupación-de-la-información)

[6 DATALAKE [44](#datalake)](#datalake)

[6.1 Aspectos Generales [44](#aspectos-generales)](#aspectos-generales)

[6.2 Gestión de Datos Relacionales
[45](#gestión-de-datos-relacionales)](#gestión-de-datos-relacionales)

[6.2.1 Bitcoin [46](#bitcoin-1)](#bitcoin-1)

[6.2.2 Ethereum [46](#ethereum-1)](#ethereum-1)

[6.2.3 Polygon [47](#polygon-1)](#polygon-1)

[6.3 Gestión Relaciones Flexibles
[48](#gestión-relaciones-flexibles)](#gestión-relaciones-flexibles)

[6.3.1 Gestión de Billeteras Sospechosas
[50](#gestión-de-billeteras-sospechosas)](#gestión-de-billeteras-sospechosas)

[6.4 API de Acceso [53](#api-de-acceso)](#api-de-acceso)

[7 GESTION DE LA INTELIGENCIA ARTIFICIAL
[56](#gestion-de-la-inteligencia-artificial)](#gestion-de-la-inteligencia-artificial)

[7.1 Introducción [56](#introducción-1)](#introducción-1)

[7.2 Entrada y transformación de datos desde el Datalake
[56](#entrada-y-transformación-de-datos-desde-el-datalake)](#entrada-y-transformación-de-datos-desde-el-datalake)

[7.3 Proceso generación modelos
[67](#proceso-generación-modelos)](#proceso-generación-modelos)

[7.3.1 Bitcoin Etapa Inicial: Exploración de Algoritmos Básicos
[68](#bitcoin-etapa-inicial-exploración-de-algoritmos-básicos)](#bitcoin-etapa-inicial-exploración-de-algoritmos-básicos)

[7.3.2 Bitcoin Etapa de Manejo del Desbalanceo de Clases: Técnicas de
Sampling
[68](#bitcoin-etapa-de-manejo-del-desbalanceo-de-clases-técnicas-de-sampling)](#bitcoin-etapa-de-manejo-del-desbalanceo-de-clases-técnicas-de-sampling)

[7.3.3 Bitcoin Etapa de Optimización: Tuning de Hiperparámetros con
Optuna [69](#_Toc210906446)](#_Toc210906446)

[7.3.4 Bitcoin Etapa Avanzada: Incorporación de Técnicas de Validación y
Prevención de Data Leak
[69](#bitcoin-etapa-avanzada-incorporación-de-técnicas-de-validación-y-prevención-de-data-leak)](#bitcoin-etapa-avanzada-incorporación-de-técnicas-de-validación-y-prevención-de-data-leak)

[7.3.5 Bitcoin Etapa de Ensamblado: Stacking y Ponderación de
Probabilidades
[70](#bitcoin-etapa-de-ensamblado-stacking-y-ponderación-de-probabilidades)](#bitcoin-etapa-de-ensamblado-stacking-y-ponderación-de-probabilidades)

[7.3.6 Bitcoin Etapa Final: Iteraciones en la Metodología de
Entrenamiento para LGBM
[70](#bitcoin-etapa-final-iteraciones-en-la-metodología-de-entrenamiento-para-lgbm)](#bitcoin-etapa-final-iteraciones-en-la-metodología-de-entrenamiento-para-lgbm)

[7.3.7 Bitcoin Resultados [71](#_Toc210906450)](#_Toc210906450)

[7.3.8 Ethereum Estrategia y Metodología
[73](#ethereum-estrategia-y-metodología)](#ethereum-estrategia-y-metodología)

[7.3.9 Gestión de la inteligencia artificial para Polygon
[74](#gestión-de-la-inteligencia-artificial-para-polygon)](#gestión-de-la-inteligencia-artificial-para-polygon)

[8 Gestión DE EVENTOS Y MOTOR DE REGLAS
[76](#gestión-de-eventos-y-motor-de-reglas)](#gestión-de-eventos-y-motor-de-reglas)

[8.1 Introducción [76](#introducción-2)](#introducción-2)

[8.2 Proceso de captura de datos
[77](#proceso-de-captura-de-datos)](#proceso-de-captura-de-datos)

[8.3 Regla de negocio [80](#regla-de-negocio)](#regla-de-negocio)

[8.4 Gestión enriquecida con técnicas de Inteligencia Artificial
[83](#gestión-enriquecida-con-técnicas-de-inteligencia-artificial)](#gestión-enriquecida-con-técnicas-de-inteligencia-artificial)

[8.5 Alertas [84](#alertas)](#alertas)

[9 ARQUITECTURA FíSICA DEL PROTOTIPO
[87](#arquitectura-física-del-prototipo)](#arquitectura-física-del-prototipo)

[9.1 Introducción [87](#introducción-3)](#introducción-3)

[9.1.1 Requisitos de arquitectura y no funcionales
[87](#requisitos-de-arquitectura-y-no-funcionales)](#requisitos-de-arquitectura-y-no-funcionales)

[9.2 Diagrama General de Arquitectura
[88](#diagrama-general-de-arquitectura)](#diagrama-general-de-arquitectura)

[9.3 Módulo de Ingesta [90](#módulo-de-ingesta)](#módulo-de-ingesta)

[9.3.1 Integración de Bitcoin
[90](#integración-de-bitcoin)](#integración-de-bitcoin)

[9.3.2 Detalle Nodo Ingestión
[91](#detalle-nodo-ingestión)](#detalle-nodo-ingestión)

[9.3.3 Integración de Ethereum
[92](#integración-de-ethereum)](#integración-de-ethereum)

[9.3.4 Integración de Polygon
[92](#integración-de-polygon)](#integración-de-polygon)

[9.4 Módulo de Enriquecimiento
[93](#módulo-de-enriquecimiento)](#módulo-de-enriquecimiento)

[9.5 Datalake [94](#datalake-1)](#datalake-1)

[9.5.1 Detalles técnicos [94](#detalles-técnicos)](#detalles-técnicos)

[9.6 Módulo de Inteligencia Artificial
[95](#módulo-de-inteligencia-artificial)](#módulo-de-inteligencia-artificial)

[9.6.1 Detalles técnicos
[95](#detalles-técnicos-1)](#detalles-técnicos-1)

[9.7 Módulo Gestor de Eventos
[96](#módulo-gestor-de-eventos)](#módulo-gestor-de-eventos)

[9.7.1 Detalles técnicos
[96](#detalles-técnicos-2)](#detalles-técnicos-2)

[9.8 Frontal Web y Custodia
[97](#frontal-web-y-custodia)](#frontal-web-y-custodia)

[9.8.1 Detalles técnicos
[98](#detalles-técnicos-3)](#detalles-técnicos-3)

[9.9 Gestión Backups [98](#gestión-backups)](#gestión-backups)

[9.10 Conexiones equipo desarrollo
[99](#conexiones-equipo-desarrollo)](#conexiones-equipo-desarrollo)

[9.11 Solución basada en contenedores
[100](#solución-basada-en-contenedores)](#solución-basada-en-contenedores)

[10 APLICACION WEB Prototipo
[102](#aplicacion-web-prototipo)](#aplicacion-web-prototipo)

[10.1 Introducción [102](#introducción-4)](#introducción-4)

[10.2 Características principales
[102](#características-principales)](#características-principales)

[10.3 Casos de uso [103](#casos-de-uso)](#casos-de-uso)

[10.3.1 Interfaz de usuario ^(ESF-0001)^
[103](#interfaz-de-usuario-esf-0001)](#interfaz-de-usuario-esf-0001)

[10.3.2 Capacidades de búsqueda ^(ESF-0002)^
[105](#capacidades-de-búsqueda-esf-0002)](#capacidades-de-búsqueda-esf-0002)

[10.3.3 Libreta de hallazgos ^(ESF-0003)^
[105](#libreta-de-hallazgos-esf-0003)](#libreta-de-hallazgos-esf-0003)

[10.3.4 Gestor de casos ^(ESF-0004)^
[106](#gestor-de-casos-esf-0004)](#gestor-de-casos-esf-0004)

[10.3.5 Generación de informes ^(ESF-0005)\ y\ (ESF-0006)^
[108](#generación-de-informes-esf-0005-y-esf-0006)](#generación-de-informes-esf-0005-y-esf-0006)

[10.3.6 Detallado de tokens ERC-20 y ERC-721
^(ESF-0018),\ (ESF-0019),\ (ESF-0020)^
[108](#detallado-de-tokens-erc-20-y-erc-721-esf-0018-esf-0019-esf-0020)](#detallado-de-tokens-erc-20-y-erc-721-esf-0018-esf-0019-esf-0020)

[10.3.7 Generación de monitorización ^(ESF-0028)^
[109](#generación-de-monitorización-esf-0028)](#generación-de-monitorización-esf-0028)

[10.3.8 Recomendación de acciones ^(ESF-0022)^
[110](#recomendación-de-acciones-esf-0022)](#recomendación-de-acciones-esf-0022)

[10.3.9 Investigación de actores y comportamiento ^(ESF-0029)^
[110](#investigación-de-actores-y-comportamiento-esf-0029)](#investigación-de-actores-y-comportamiento-esf-0029)

[10.3.10 Custodia de evidencias y sellado ^(ESF-0031)\ y\ (ESF-0033)^
[111](#custodia-de-evidencias-y-sellado-esf-0031-y-esf-0033)](#custodia-de-evidencias-y-sellado-esf-0031-y-esf-0033)

[10.4 Gestión de Autenticación y Autorización
^(ESF-0034)\ y\ (ESF-0037)^
[112](#gestión-de-autenticación-y-autorización-esf-0034-y-esf-0037)](#gestión-de-autenticación-y-autorización-esf-0034-y-esf-0037)

[10.4.1 Autenticación [112](#autenticación)](#autenticación)

[10.4.2 Autorización y control de accesos
[113](#autorización-y-control-de-accesos)](#autorización-y-control-de-accesos)

[10.5 API de Acceso ^(ESF-0036)^
[116](#api-de-acceso-esf-0036)](#api-de-acceso-esf-0036)

[10.5.1 Endpoint /getRules
[116](#endpoint-getrules)](#endpoint-getrules)

[10.5.2 Endpoint /create-alert
[117](#endpoint-create-alert)](#endpoint-create-alert)

[11 MONITORIZACIÓN [119](#monitorización)](#monitorización)

[11.1 Propósito y alcance
[119](#propósito-y-alcance)](#propósito-y-alcance)

[11.2 Visión general de la arquitectura
[120](#visión-general-de-la-arquitectura)](#visión-general-de-la-arquitectura)

[11.3 Flujo de datos de observabilidad
[121](#flujo-de-datos-de-observabilidad)](#flujo-de-datos-de-observabilidad)

[11.4 Diseño lógico [124](#diseño-lógico-1)](#diseño-lógico-1)

[11.4.1 Namespaces, grupos de logs y dimensiones
[124](#namespaces-grupos-de-logs-y-dimensiones)](#namespaces-grupos-de-logs-y-dimensiones)

[11.5 Cloud Logs [125](#cloud-logs)](#cloud-logs)

[11.5.1 Driver awslogs [125](#driver-awslogs)](#driver-awslogs)

[11.5.2 Sidecar Fluent Bit
[125](#sidecar-fluent-bit)](#sidecar-fluent-bit)

[11.6 Métricas [127](#métricas)](#métricas)

[11.6.1 CloudWatch Agent en instancias EC2
[127](#cloudwatch-agent-en-instancias-ec2)](#cloudwatch-agent-en-instancias-ec2)

[11.6.2 Publicación nativa en servicios AWS
[127](#publicación-nativa-en-servicios-aws)](#publicación-nativa-en-servicios-aws)

[11.7 Alarmas [128](#alarmas)](#alarmas)

[11.8 Dashboards y observabilidad
[128](#dashboards-y-observabilidad)](#dashboards-y-observabilidad)

[11.8.1 Dashboards de infraestructura por EC2
[128](#dashboards-de-infraestructura-por-ec2)](#dashboards-de-infraestructura-por-ec2)

[11.8.2 Dashboards de negocio (tracking de blockchains)
[129](#dashboards-de-negocio-tracking-de-blockchains)](#dashboards-de-negocio-tracking-de-blockchains)

[12 GESTION DEL SOFTWARE desarrollado
[131](#gestion-del-software-desarrollado)](#gestion-del-software-desarrollado)

[12.1 Introducción [131](#introducción-5)](#introducción-5)

[12.2 Gestión del software
[132](#gestión-del-software)](#gestión-del-software)

[12.3 Procedimientos de despliegue
[134](#procedimientos-de-despliegue)](#procedimientos-de-despliegue)

[13 PRÓXIMOS PASOS [136](#próximos-pasos)](#próximos-pasos)

[14 REFERENCIAS [137](#referencias)](#referencias)

[ANEXO I. HISTÓRICO DE MODIFICACIONES
[138](#anexo-i.-histórico-de-modificaciones)](#anexo-i.-histórico-de-modificaciones)

[ANEXO II. ENDPOINTS API DATALAKE
[138](#anexo-ii.-endpoints-api-datalake)](#anexo-ii.-endpoints-api-datalake)

[ANEXO III. ENDPOINTS API FRONTEND
[138](#anexo-iii.-endpoints-api-frontend)](#anexo-iii.-endpoints-api-frontend)

[ANEXO IV. RESULTADOS PRUEBAS DE VALIDACION
[139](#anexo-iv.-resultados-pruebas-de-validacion)](#anexo-iv.-resultados-pruebas-de-validacion)

[]{#_Toc408386635 .anchor}ÍNDICE DE TABLAS

[Tabla 1 -- Audiencia [8](#_Toc210906526)](#_Toc210906526)

[Tabla 2 -- Requisitos establecidos para el prototipo
[13](#_Toc210906527)](#_Toc210906527)

[Tabla 3 -- Objetivos científicos establecidos para el prototipo
[13](#_Toc210906528)](#_Toc210906528)

[Tabla 4 -- Integración de fuentes externas off-chain ^(ESF-23)^
[42](#_Toc210906529)](#_Toc210906529)

[Tabla 1 - Volumenes Módulo ETL+AI [58](#_Toc210906530)](#_Toc210906530)

[Tabla 2 - Volúmenes de contenedor mixer
[63](#_Toc210906531)](#_Toc210906531)

[Tabla 3 - Experimentos representativos
[71](#_Toc210906532)](#_Toc210906532)

[Tabla 5 -- Reglas de detección de actividades fraudulentas
[81](#_Toc210906533)](#_Toc210906533)

[Tabla 6 -- Especificaciones no funcionales del prototipo
[88](#_Toc210906534)](#_Toc210906534)

[Tabla 7 -- Detalle de red Servidores Infraestructura
[95](#_Toc210906535)](#_Toc210906535)

[Tabla 8 -- Detalle de red Módulo de IA
[96](#_Toc210906536)](#_Toc210906536)

[Tabla 9 -- Detalle de red Gestor Eventos
[97](#_Toc210906537)](#_Toc210906537)

[Tabla 10 -- Detalle de red Frontal Web
[98](#_Toc210906538)](#_Toc210906538)

[Tabla 11 - Relación funcionalidades con roles
[116](#_Toc210906539)](#_Toc210906539)

[Tabla 12 -- Matrix de cobertura Monitorización
[122](#_Toc210906540)](#_Toc210906540)

[Tabla 13 - Histórico de modificaciones
[138](#_Toc133437760)](#_Toc133437760)

[]{#_Hlk207785748 .anchor}

ÍNDICE DE ILUSTRACIONES

[Ilustración 1 -- Diagrama conceptual del prototipo
[15](#_Toc210906542)](#_Toc210906542)

[Ilustración 2 -- Métodos de Inteligencia Artificial
[17](#_Toc210906543)](#_Toc210906543)

[Ilustración 3 -- Ámbito tecnológico del prototipo
[19](#_Toc210906544)](#_Toc210906544)

[Ilustración 4 -- Flujos de comunicación
[20](#_Toc210906545)](#_Toc210906545)

[Ilustración 5 -- Diagrama conceptual ingesta de datos in-chain
[24](#_Toc210906546)](#_Toc210906546)

[Ilustración 6 -- Diagrama conceptual ingesta de datos off-chain
[25](#_Toc210906547)](#_Toc210906547)

[Ilustración 7 -- Pipeline de transmisión a módulo de IA
[27](#_Toc210906548)](#_Toc210906548)

[Ilustración 8 -- Pipeline de generación de alertas
[28](#_Toc210906549)](#_Toc210906549)

[Ilustración 9 -- Gestión serie temporal histórica
[29](#_Toc210906550)](#_Toc210906550)

[Ilustración 10 - Ingesta Bitcoin [32](#_Toc210906551)](#_Toc210906551)

[Ilustración 11 -- Ingesta Ethereum
[33](#_Toc210906552)](#_Toc210906552)

[Ilustración 12 -- Ingesta Polygon [35](#_Toc210906553)](#_Toc210906553)

[Ilustración 13 -- CLI de carga de información off-chain
[37](#_Toc210906554)](#_Toc210906554)

[Ilustración 14 -- Airflow -- Integraciones programáticas
[38](#_Toc210906555)](#_Toc210906555)

[Ilustración 15 -- Captura Ingesta Telegram
[39](#_Toc210906556)](#_Toc210906556)

[Ilustración 16 -- Diagrama lógico enriquecimiento de datos
[40](#_Toc210906557)](#_Toc210906557)

[Ilustración 17 -- Captura sistema de enriquecimiento
[41](#_Toc210906558)](#_Toc210906558)

[Ilustración 18 -- Ejemplo correlación: países, carteras, entidades OFAC
y Ciberactores [43](#_Toc210906559)](#_Toc210906559)

[Ilustración 19 -- Ejemplo correlación: Ciberactores (gris), CVEs
empleados en ataques (azul) [43](#_Toc210906560)](#_Toc210906560)

[Ilustración 20 -- Fuentes de datos de datalake
[44](#_Toc210906561)](#_Toc210906561)

[Ilustración 21 -- Diagrama relacional Bitcoin
[46](#_Toc210906562)](#_Toc210906562)

[Ilustración 22 -- Diagrama relacional Ethereum
[47](#_Toc210906563)](#_Toc210906563)

[Ilustración 23 -- Diagrama relacional Polygon
[48](#_Toc210906564)](#_Toc210906564)

[Ilustración 24 -- Captura dashboard Ingesta desde Blockchains
[48](#_Toc210906565)](#_Toc210906565)

[Ilustración 25 -- Diagrama de entidad no relacional
[49](#_Toc210906566)](#_Toc210906566)

[Ilustración 26 -- Captura dashboard Fuentes OSINT (I)
[50](#_Toc210906567)](#_Toc210906567)

[Ilustración 27 -- Captura dashboard Fuentes OSINT (II)
[50](#_Toc210906568)](#_Toc210906568)

[Ilustración 28 -- Captura Explorador: Nivel de riesgo de carteras
[52](#_Toc210906569)](#_Toc210906569)

[Ilustración 29 -- Captura Dashboard: Contadores de clasificación de
carteras en el datalake [53](#_Toc210906570)](#_Toc210906570)

[Ilustración 30 -- Consumidores API del Datalake
[53](#_Toc210906571)](#_Toc210906571)

[Ilustración 31 -- Captura API [54](#_Toc210906572)](#_Toc210906572)

[Ilustración 32 -- Gestor de eventos: estructura lógica
[76](#_Toc210906573)](#_Toc210906573)

[Ilustración 33 -- Gestor de eventos: estructura software
[78](#_Toc210906574)](#_Toc210906574)

[Ilustración 34 -- Captura gestor de eventos: Jobs en ejecución
[78](#_Toc210906575)](#_Toc210906575)

[Ilustración 35 -- Captura elementos monitorizados
[79](#_Toc210906576)](#_Toc210906576)

[Ilustración 36 -- Captura elementos monitorizados: búsqueda (1)
[80](#_Toc210906577)](#_Toc210906577)

[Ilustración 37 -- Captura elementos monitorizados: búsqueda (2)
[80](#_Toc210906578)](#_Toc210906578)

[Ilustración 38 -- Captura creación de regla de monitorización en tiempo
real [81](#_Toc210906579)](#_Toc210906579)

[Ilustración 39 -- Captura gestor de eventos: flujo de ejecución
[82](#_Toc210906580)](#_Toc210906580)

[Ilustración 40 -- Captura Gestor de eventos, dependencia de procesos
[83](#_Toc210906581)](#_Toc210906581)

[Ilustración 41 -- Captura alerta generada por sistema de monitorización
[86](#_Toc210906582)](#_Toc210906582)

[Ilustración 42 -- Diagrama general infraestructura física
[89](#_Toc210906583)](#_Toc210906583)

[Ilustración 43 -- Captura listado de servidores EC2
[89](#_Toc210906584)](#_Toc210906584)

[Ilustración 44 -- Diagrama físico Ingesta Bitcoin
[91](#_Toc210906585)](#_Toc210906585)

[Ilustración 45 -- Diagrama físico Ingesta Bitcoin (2)
[91](#_Toc210906586)](#_Toc210906586)

[Ilustración 46 -- Diagrama físico Ingesta Ethereum
[92](#_Toc210906587)](#_Toc210906587)

[Ilustración 47 -- Diagrama físico ingesta Polygon
[93](#_Toc210906588)](#_Toc210906588)

[Ilustración 48 -- Diagrama físico Pipeline
[93](#_Toc210906589)](#_Toc210906589)

[Ilustración 49 -- Diagrama físico API datalake
[94](#_Toc210906590)](#_Toc210906590)

[Ilustración 50 -- Diagrama físico Módulo de IA
[95](#_Toc210906591)](#_Toc210906591)

[Ilustración 51 -- Diagrama físico Gestor de Eventos
[96](#_Toc210906592)](#_Toc210906592)

[Ilustración 52 -- Diagrama físico Frontal Web
[98](#_Toc210906593)](#_Toc210906593)

[Ilustración 53 -- Diagrama físico Backup
[99](#_Toc210906594)](#_Toc210906594)

[Ilustración 54 -- Captura reglas de acceso equipo de desarrollo
[99](#_Toc210906595)](#_Toc210906595)

[Ilustración 55 -- Captura reglas de salida equipo de desarrollo
[100](#_Toc210906596)](#_Toc210906596)

[Ilustración 56 -- Diagrama de arquitectura acceso equipo de desarrollo
[100](#_Toc210906597)](#_Toc210906597)

[Ilustración 57 - Listado de addresses
[104](#_Toc210906598)](#_Toc210906598)

[Ilustración 58 - Detalles de una address
[104](#_Toc210906599)](#_Toc210906599)

[Ilustración 59 - Detalle de una transacción
[105](#_Toc210906600)](#_Toc210906600)

[Ilustración 60 - Buscador y filtros
[105](#_Toc210906601)](#_Toc210906601)

[Ilustración 61 - Libreta de hallazgos
[106](#_Toc210906602)](#_Toc210906602)

[Ilustración 62 - Listado de casos
[106](#_Toc210906603)](#_Toc210906603)

[Ilustración 63 - Información de casos
[106](#_Toc210906604)](#_Toc210906604)

[Ilustración 64 - Árbol de trazabilidad
[107](#_Toc210906605)](#_Toc210906605)

[Ilustración 65 - Grafo de trazabilidad
[107](#_Toc210906606)](#_Toc210906606)

[Ilustración 66 - Adresses incluidas en un caso
[107](#_Toc210906607)](#_Toc210906607)

[Ilustración 67 - Documentación del caso
[108](#_Toc210906608)](#_Toc210906608)

[Ilustración 68 -- Generación de informe
[108](#_Toc210906609)](#_Toc210906609)

[Ilustración 69 - Detalles de una address de Ethereum
[109](#_Toc210906610)](#_Toc210906610)

[Ilustración 70 - Monitorización [109](#_Toc210906611)](#_Toc210906611)

[Ilustración 71 - Alerta generada [110](#_Toc210906612)](#_Toc210906612)

[Ilustración 72 - Acciones recomendadas
[110](#_Toc210906613)](#_Toc210906613)

[Ilustración 73 - Información de entidades
[111](#_Toc210906614)](#_Toc210906614)

[Ilustración 74 - Información de adresses de entidades
[111](#_Toc210906615)](#_Toc210906615)

[Ilustración 75 - Diagrama funcionamiento de autenticación
[112](#_Toc210906616)](#_Toc210906616)

[Ilustración 76 -- Interfaz de usuario: Gestión de usuarios
[114](#_Toc210906617)](#_Toc210906617)

[Ilustración 77 -- Interfaz de usuario: Gestión de permisos
[114](#_Toc210906618)](#_Toc210906618)

[Ilustración 78 - Ejemplo endPoint getRules
[117](#_Toc210906619)](#_Toc210906619)

[Ilustración 79 - Ejemplo endPoint creación de alertas
[118](#_Toc210906620)](#_Toc210906620)

[Ilustración 80 -- Alcance Monitorización
[119](#_Toc210906621)](#_Toc210906621)

[Ilustración 81 -- Captura Visualización de Métricas
[120](#_Toc210906622)](#_Toc210906622)

[Ilustración 82 -- Captura métricas performance
[129](#_Toc210906623)](#_Toc210906623)

[Ilustración 83 -- Captura dashboard rendimiento
[130](#_Toc210906624)](#_Toc210906624)

[Ilustración 84 -- Procedimiento SSDLC
[131](#_Toc210906625)](#_Toc210906625)

[Ilustración 85 -- Captura Portal Azure DevOps
[132](#_Toc210906626)](#_Toc210906626)

[Ilustración 86 -- Repositorios de código
[133](#_Toc210906627)](#_Toc210906627)

[Ilustración 87 -- Captura Listado de Repositorios Azure DevOps
[134](#_Toc210906628)](#_Toc210906628)

[Ilustración 88 -- Procedimiento de despliegue
[135](#_Toc210906629)](#_Toc210906629)

[Ilustración 89 -- Captura Procesos de despliegue
[135](#_Toc210906630)](#_Toc210906630)

# INTRODUCCIÓN

## Propósito

El propósito de este documento es proporcionar una amplia **descripción
de la solución** desarrollada, incluyendo tanto la parte de hardware
como de software. Este documento analiza la solución desde diversos
puntos de vista, proporcionando detalles a nivel de **arquitectura**,
**funcionalidad**, **seguridad, interfaz de usuario**, **gestión de
información e implementación**.

A lo largo de este documento se incluyen **capturas de pantalla del
prototipo** obtenido como resultado de la etapa 2. Estas imágenes tienen
un doble propósito, por un lado la de **mostrar el objeto** que se está
describiendo en cada caso (ya que una imagen puede aportar una claridad
adicional a una descripción textual), y por otro la de **evidenciar el
trabajo realizado** y el nivel de detalle que se ha alcanzado en esta
etapa.

Así mismo, y para facilitar la trazabilidad, se realiza un mapeo entre
los aspectos técnicos de la solución desarrollada, y los puntos del
documento del proyecto de ingeniería entregado en la etapa uno.

## Audiencia

La tabla siguiente proporciona información detallada sobre las
audiencias clave de este documento:

  -----------------------------------------------------------------------
  **Audience**                **Descripción**
  --------------------------- -------------------------------------------
  Equipo de Ingeniería e      Como parte involucrada en el diseño y
  Infraestructura de          desarrollo de la solución funcional del
  Deloitte.                   prototipo, y proveedor de la información
                              que aquí se recoge.

  Equipos de Machine Learning Como parte involucrada en el diseño y
  de AirInstitute             desarrollo de la solución funcional del
                              prototipo, y proveedor de la información
                              que aquí se recoge.

  Equipo de Entidad Usuaria   Para la revisión de los requisitos y
                              necesidades funcionales establecidos.

  Equipos de auditoria        Para verificar el compromiso relativo al
                              TRL de partida y de destino de este
                              proyecto.

  INCIBE                      Como supervisor para garantizar que el
                              proyecto cumple con las directrices del
                              pliego original.
  -----------------------------------------------------------------------

  : []{#_Toc210906526 .anchor}Tabla 1 -- Audiencia

## Ámbito

El proyecto responde al reto: "**Seguimiento de transacciones vinculadas
con ransomware y otras campañas**", perteneciente a la tercera
convocatoria de la Iniciativa estratégica de Compra Pública de
Innovación convocada por el Instituto Nacional de Ciberseguridad
(INCIBE), con el objetivo de impulsar la I+D+i y la creación de
productos y soluciones en el ámbito de la ciberseguridad.

Ciberdelitos como el ransomware mueven anualmente casi 600 millones de
dólares en pagos, lo que hace que organizaciones de seguridad como el
FBI, NSA, FinCEN o Europol generen **acciones para el análisis,
seguimiento, detección y atribución** de las transacciones vinculadas a
este tipo de ataques. Las formas en las que los actores malintencionados
o cibercriminales atacan a los sistemas están siendo cada vez más
sofisticadas y con ello los flujos en los que tratan de esconder los
pagos recibidos por estas acciones. Es por ello por lo que este reto
busca dar **solución a los problemas actuales y futuros** de
trazabilidad, detección y atribución de transacciones debidas a campañas
originadas por el cibercrimen.

En los ataques de ransomware, el ciberdelincuente exige el **pago del
rescate** mediante **criptoactivos**. Esta tecnología presenta una serie
de características que favoreces su utilización para este tipo de
situaciones:

- **Accesibilidad**: que permite que cualquier tipo de persona, aunque
  no se tenga experiencia previa en este tipo de entorno, pueda adquirir
  los conocimientos suficientes para transformar dinero FIAT en la
  cuantía de cripto activos del rescate y hacer el pago.

- **Agilidad**: ya que, al no depender de bancos o entidades centrales,
  está disponible las 24 horas del día para poder tramitar cualquier
  tipo de operación.

- **Anónimo:** aunque las transacciones son públicas y accesibles para
  cualquier usuario, es posible ocultar la identidad real de los
  propietarios de las carteras.

El grupo de **ciberdelincuente**, una vez cometido el acto delictivo y
bloqueado el acceso a los recursos secuestrados, suele facilitar una
nota a su víctima en formato de fichero de texto plano. En esta nota,
normalmente localizada junto con las carpetas y ficheros bloqueados, se
le informa del ataque perpetrado, se suele incluir información sobre la
cantidad y el tipo de los **datos extraídos**; y por último y lo más
importante, facilita información para hacer frente al **pago del
rescate** y de las **consecuencias** de no hacerlo.

Si bien, el hacer frente al **pago** del rescate **no es la opción
recomendada** desde las fuerzas y cuerpos de seguridad del estado, o los
organismos o entidades dedicadas al ámbito de la ciberseguridad, sí hay
ocasiones donde la víctima cae en la extorsión y se ve forzado a
realizarlo. La naturaleza **descentralizada** y el carácter **anónimo**
de las soluciones blockchain, complica la tarea de obtener estadísticas
y disponer de datos reales sobre la volumetría económica de este tipo de
ataque. Esto hace que los datos estadísticos de los que disponemos sean
**aproximaciones**.

En este sentido, resulta fundamental **comprender y analizar** los
mecanismos utilizados para realizar el pago a través de la blockchain y
su posterior seguimiento, con el fin de **fortalecer** las capacidades
de las instituciones públicas y privadas en materia de prevención,
detección y persecución de actividades ilícitas. El desarrollo de una
solución como la que aquí exponemos es prácticamente una necesidad para
disponer de alternativas con las que contrastar los indicadores
existentes sobre la economía sumergida del ransomware y otras
actividades ilícitas.

En el análisis de pagos de ransomware, la elección de las blockchains a
estudiar es clave para entender cómo operan los atacantes y cómo se
pueden trazar sus movimientos financieros. En este contexto, se ha
seleccionado **Bitcoin, Ethereum y Polygon** por ser tres redes que
reflejan tanto la evolución histórica del ransomware como las tendencias
emergentes en el uso criminal de criptomonedas.

**Bitcoin** ha sido la criptomoneda más utilizada en ataques de
ransomware desde los inicios. Su popularidad se debe a su amplia
adopción, liquidez y facilidad de uso para los atacantes. Sin embargo,
la característica más relevante desde el punto de vista forense es que
la blockchain de Bitcoin es pública y transparente, lo que permite
rastrear las transacciones a pesar de los intentos de ofuscación
mediante *mixers* o cadenas de wallets intermedias. Ejemplos claros son
los casos de **WannaCry (2017)**, que exigía pagos en Bitcoin; **Ryuk**,
activo entre 2018 y 2021 con cientos de víctimas en hospitales y
administraciones; y **Conti**, uno de los grupos más agresivos hasta su
disolución en 2022, que utilizaba Bitcoin casi exclusivamente. Estos
casos consolidan a Bitcoin como la red de referencia para el estudio del
ransomware.

**Ethereum**, por su parte, introduce una mayor complejidad al análisis
al permitir el uso de contratos inteligentes y un ecosistema de tokens
(ERC-20, ERC-721). Muchos grupos han comenzado a diversificar sus pagos
hacia esta red, no solo aceptando ETH, sino también stablecoins como
USDT o USDC, que ofrecen mayor estabilidad. Los atacantes aprovechan las
posibilidades de Ethereum para interactuar con *decentralized exchanges*
(DEXs), *bridges* y protocolos DeFi, lo que les permite blanquear fondos
de manera más sofisticada. Ejemplos de su uso se encuentran en grupos
como **DarkSide/BlackMatter**, que además de Bitcoin aceptaban pagos en
Ethereum; o **REvil (Sodinokibi)**, que en sus primeras fases manejó
tanto Bitcoin como Ethereum antes de migrar parcialmente a Monero. Esto
confirma que Ethereum es una pieza fundamental para comprender la
evolución de los métodos de cobro en ransomware.

Finalmente, **Polygon** representa una tendencia más reciente: el uso de
redes de bajo coste y alta velocidad para mover fondos ilícitos.
Polygon, como red de segunda capa compatible con Ethereum (EVM), ofrece
comisiones muy bajas y rapidez, lo que la hace atractiva para los
atacantes. Aunque todavía no se han identificado grupos de ransomware
tan mediáticos que acepten Polygon directamente, informes de
inteligencia (Intel471, 2023) muestran que ya es utilizada en campañas
de malware y estafas, y analistas de Elliptic han detectado su empleo
como red intermedia para convertir pagos recibidos en Bitcoin o Ethereum
hacia stablecoins. Además, su papel en fraudes como *rug pulls*
evidencia que los criminales ya confían en la red, y es previsible que
su uso en ransomware aumente. La existencia de propuestas académicas
para emplear Polygon en el aseguramiento de evidencias digitales
refuerza, además, su relevancia forense.

En conclusión, **Bitcoin, Ethereum y Polygon** abarcan un espectro
amplio de escenarios de pago en ransomware: desde la tradición y volumen
histórico de Bitcoin, pasando por la diversidad y sofisticación de
Ethereum, hasta la eficiencia emergente de Polygon. Todas comparten el
carácter público y transparente de sus blockchains, lo que posibilita su
trazabilidad y análisis forense. Incluir estas tres redes garantiza una
visión integral sobre cómo los ciberdelincuentes reciben, mueven y
ocultan los pagos de sus víctimas, al tiempo que permite fortalecer las
capacidades de investigación y respuesta frente a este tipo de amenazas.

## Características de la Solución Desarrollada

El objeto del proyecto es el **desarrollo de una solución que permita el
seguimiento y detección de transacciones con criptoactivos vinculados
con actividades ilícitas** o incidentes de seguridad **a partir de
técnicas y algoritmos de inteligencia artificial**. Para alcanzarlo, se
propone una solución que integre de manera coordinada los ámbitos de
**blockchain, ciberseguridad, inteligencia artificial y procesamiento de
datos**.

La **tecnología blockchain** constituye el ámbito en el que se
identificarán las operaciones ilícitas; la **ciberseguridad** aportará
información sobre el estado de las amenazas y las campañas en curso por
parte de los ciberdelincuentes; la **inteligencia artificial**
proporcionará los mecanismos necesarios para extraer patrones de
comportamiento; y el **procesamiento de datos** se establecerá como el
método de trabajo que permitirá articular e integrar todos estos
elementos.

Cada uno de estos ámbitos presenta una problemática específica que se
aborda tanto en este documento como en el resto de entregables de esta
etapa. En términos generales, se trata de áreas muy dispares entre sí,
lo que ha hecho necesaria la colaboración de grupos de trabajo altamente
heterogéneos. La coordinación entre estos equipos, junto con la calidad
de su labor, ha permitido trabajar en los objetivos inicialmente
planteados y disponer de un prototipo que cumple con los requisitos
definidos en el documento de ingeniería de la etapa 1. Cada equipo,
dentro de su área de conocimiento, ha trabajado en la búsqueda de la
mejor solución posible, garantizando el cumplimiento de los requisitos
funcionales, no funcionales y de arquitectura establecidos, y teniendo
siempre en cuenta el carácter innovador y retador de la propuesta
impulsada por el INCIBE.

Uno de los primeros objetivos definidos para esta etapa ha sido la
búsqueda de una **definición óptima de los módulos** que conforman el
sistema. Para ello, se ha realizado una **transposición de los cuatro
ámbitos principales** ---*blockchain*, ciberseguridad, inteligencia
artificial y procesamiento de datos--- en **cuatro módulos
específicos**, complementados con **otros tres módulos adicionales**
destinados a garantizar la conectividad entre ellos. Este enfoque
permite ofrecer un **diseño coherente y funcional**, alineado tanto con
los **objetivos del proyecto** como con sus **requisitos técnicos**
establecidos.

Los módulos mencionados constituyen el **marco estructural** dentro del
cual se integran las distintas funcionalidades previstas. En este
sentido, el presente documento describe las **características y
particularidades de cada módulo**, así como los **aspectos
arquitectónicos del prototipo implementado**.

La exposición sigue la lógica del **flujo de procesamiento de datos**,
abarcando desde las **etapas iniciales de ingesta** ---tanto desde las
*blockchains* establecidas para este proyecto como desde **fuentes
off-chain**--- hasta la **detección y seguimiento de actividades
maliciosas** vinculadas a casos de *ransomware.*

Cabe recordar que el **documento de ingeniería presentado en la Etapa
1** ya detalla los **requisitos generales**, así como las
**especificaciones funcionales y no funcionales** necesarias para el
desarrollo del sistema, no obstante, en este documento se enlazarán los
elementos más relevantes.

A lo largo de este documento se presenta la **descripción del diseño e
implementación** de la solución propuesta, incluyendo la **información
técnica** relativa a las distintas **capas y componentes** del sistema,
sus **principales características** y los **requisitos asociados** en
cada caso. También se incluirán referencia al resto de entregables de
esta etapa, ofreciendo una visión general del sistema, y facilitando el
acceso al detalle cuando así lo requiera el lector.

# REQUISITOS

El detalle de los requisitos y aspectos funcionales y no funcionales se
encuentra recogido dentro del documento de proyecto de ingeniería
entregado en la etapa 1. Para facilitar su uso y acceso a los miembros
de este equipo, se ha procedido a generar un repositorio dentro de Azure
DevOps: <https://dev.azure.com/ES-RA-ECC/INCIBE_CPP3_Reto4>

  ------------------------------------------------------------------
  **Id**        **Nombre**
  ------------- ----------------------------------------------------
  REQ-0001      Ingesta de información de blockchains

  REQ-0002      Enriquecimiento desde fuentes externas

  REQ-0003      Correlación de información y descubrimiento
                potenciado por inteligencia artificial

  REQ-0004      Trazabilidad y atribución potenciada por
                inteligencia artificial

  REQ-0005      Monitorización continua

  REQ-0006      Reporting, investigación y soporte a operativas de
                servicio

  REQ-0007      Sistema de custodia de evidencias

  REQ-0008      Interfaz de usuario para investigación de casos e
                Interoperabilidad

  REQ-0009      Gobierno del sistema
  ------------------------------------------------------------------

A modo de resumen, véase la siguiente tabla con los requisitos
establecidos:

[]{#_Toc210906527 .anchor}Tabla 2 -- Requisitos establecidos para el
prototipo

Adicionalmente, aquí se recopilan los objetivos científicos:

  -------------------------------------------------------------------
  Identificador   Nombre
  --------------- ---------------------------------------------------
  OBJ-0001        Captura, transformación y almacenamiento de
                  información procedente de las redes *blockchain*
                  seleccionadas (Bitcoin, Ethereum, Polygon)

  OBJ-0002        Inteligencia artificial aplicada al análisis de
                  carteras

  OBJ-0003        Agrupación inteligente de información

  OBJ-0004        Capacidad de Simulación y ejecutar series de datos
                  históricos

  OBJ-0005        Optimización de Detección de Anomalías en Tiempo
                  Real
  -------------------------------------------------------------------

  : []{#_Toc210906528 .anchor}Tabla 3 -- Objetivos científicos
  establecidos para el prototipo

A lo largo de este documento se incluirán referencias a los requisitos y
objetivos científicos, así como a las especificaciones funcionales y no
funcionales. Esta indexación proporciona trazabilidad y permite
identificar la relación entre los puntos establecidos en la
documentación original del proyecto y los elementos de arquitectura e
implementación incluidos en el prototipo final presentado como resultado
obtenido de la etapa 2.

# DISEÑO TÉCNICO

## Descripción de la Solución Desarrollada

El objetivo de la etapa 2, es el de implementar una solución de acuerdo
con las necesidades establecidas en la documentación entregada en la
etapa 1. Es decir, la **creación de un prototipo que, a partir de
técnicas y algoritmos de inteligencia artificial, permita la detección
de movimientos en las blockchains vinculadas con actividades
relacionadas con ransomware.** Con este objetivo, la solución planteada
parte de las blockchains bajo el ámbito de este proyecto (Bitcoin,
Ethereum y Polygon) y presentan una arquitectura de solución que permita
su recopilación y procesamiento, enriquecimiento desde fuentes
adicionales, y procesamiento mediante técnicas de inteligencia
artificial para la identificación de actividad maliciosa.

La propia complejidad del problema hace que se haya tenido que tomar la
decisión de generar diversos **módulos que interactúan entre sí.** Cada
uno de estos módulos se centra en resolver los problemas y necesidades
específicos de un área concreta, y ofrece una serie de interfaces
específicos que facilitan la iteración con el resto de elementos que
forman la solución.

![[]{#_Toc210906542 .anchor}Ilustración 1 -- Diagrama conceptual del
prototipo](media/image5.png){width="6.093055555555556in"
height="2.813720472440945in"}

La imagen anterior responde al propósito de ofrecer al lector una idea
general y una nomenclatura para los distintos componentes de la
solución. En ella se observa un diagrama conceptual de las distintas
**etapas lógicas** involucradas en el prototipo. Principalmente el
sistema cuenta con dos fuentes de información: **información procedente
de las blockchains**, correspondiente a la información de bloques,
transacciones y sus metadatos ^(REQ-0001)^; e información recuperada de
**fuentes externas** (*denominado internet en el diagrama*),
correspondiente a información pública pero relacionada con el
cibercrimen ^(REQ-0002)^. Dentro de las secciones "4. Ingesta
Blockchains" y "5. Enriquecimiento de Información" se hace un análisis
más detallado de estos dos módulos. ^(OBJ-0001)^

Estas fuentes de información son transformados y almacenados dentro de
un **Datalake** ^(REQ-0003)^, que facilita el almacenamiento y
recuperación orquestada de la información. (sección "6. Datalake")
^(OBJ-0003)^

Toda esta información pasa al **módulo de inteligencia artificial**.
Este módulo presenta una misión doble:

- Durante la **fase de preparación y entrenamiento,** el equipo de
  Inteligencia Artificial ha estado realizando la labor de adaptación de
  los datos proporcionados por las fuentes anteriores y generar un
  dataset con el que facilitar la generación de los modelos bajo estudio
  y evaluación. ^(REQ-0003)\ (OBJ-0002)^

- Posteriormente, una vez evaluados los podemos y seleccionados los que
  mejor se adaptan a las características del prototipo final, se han
  integrado dentro de una solución que permiten su uso en un entorno de
  integración, realizando predicciones para la identificación de
  patrones de comportamiento asociados a casos de ransomware.
  ^(REQ-0004)\ (OBJ-0004)^

Este módulo queda descrito en la sección "*7. Gestión de la inteligencia
Artificial*".

Hasta este punto, los **primeros módulos** descritos obedecen a la parte
más **científica y de investigación** del proyecto. Partiendo del estado
del arte, se han realizado diversos estudios y pruebas de concepto para
identificar soluciones óptimas, y basadas en inteligencia artificial
para la identificación de patrones relacionados con actividades
maliciosas en la blockchain. El **resto de los módulos** de la solución
presentan un carácter más **innovador y técnico**. Donde, haciendo uso
de las capas anteriores, se responde a la necesidades y casos de uso
planteados por las entidades usuarias establecidos.

Siguiendo la estructura del diagrama, se dispone de un penúltimo
componente que permite la ejecución **coordinada de los componentes
anteriores en tiempo real**. Su misión es la ir procesando la unión de
la información procedente de las *blockchains* en estudio, junto con la
información de enriquecimiento recuperada de las fuentes externas, para
poder lanzar los modelos de inteligencia artificial y poder identificar
posibles casos (transacciones) vinculadas con actividades delictivas.
^(REQ-0005)\ (OBJ-0005)^

Véase la sección *8. Gestión de Eventos y Motor de Reglas* para más
detalle.

Por último, se dispone de una **solución web** a la que podrán acceder
los usuarios para poder modificar las parametrizaciones de los módulos
anteriores con el objetivo de mejorar su rendimiento y consumir la
información. ^(REQ-0006,\ REQ-0007,\ REQ-0008)^

*Sección 10. Aplicación Web Prototipo.*

Adicionalmente, el prototipo cuenta con un **módulo adicional,
Monitorización**, donde se realiza el control y supervisión, así como la
trazabilidad y control de performance y rendimiento de cada uno de los
elementos anteriores, y del prototipo en su conjunto. Vease la sección
*11. Monitorización* para más detalle.

A lo largo de este documento, dentro de la sección establecidas para
cada módulo, se realizará una revisión más detallada de las
características y objetivos establecidos a cada módulo.

**Inteligencia Artificial** ^(REQ-0004)^

Antes de continuar, es importante destacar que el **carácter diferencial
de este proyecto** radica en el **uso de técnicas y modelos de
inteligencia artificial** orientados a la **detección de actividades
ilícitas relacionadas con el ransomware** dentro de las *blockchains*
objeto de estudio.

En este contexto, el **módulo de Inteligencia Artificial** tiene la
responsabilidad de **analizar la información procedente del *datalake***
---que integra tanto los bloques publicados en las *blockchains* como
contenidos **off-chain**--- con el objetivo de **generar modelos capaces
de identificar comportamientos sospechosos** asociados a las carteras
que registran actividad en la cadena de bloques.

Dicha información, que incluye **transacciones en diversas
*blockchains***, **indicadores de ciberseguridad** y **otras fuentes
complementarias**, es procesada mediante los **algoritmos de
inteligencia artificial seleccionados**, los cuales, a partir de una
**parametrización definida durante las fases de entrenamiento y
evaluación**, asignan una **valoración numérica (predicción)** a cada
dirección en función de su comportamiento observado.

Aunque en la sección específica dedicada al módulo de Inteligencia
Artificial se ofrece una explicación más detallada sobre los
procedimientos empleados, resulta pertinente adelantar aquí una **visión
general de las técnicas y la metodología** aplicadas en el diseño y
desarrollo de esta solución.

![[]{#_Toc210906543 .anchor}Ilustración 2 -- Métodos de Inteligencia
Artificial](media/image6.png){width="4.950694444444444in"
height="2.0730872703412073in"}

La inteligencia artificial ha experimentado en los últimos años un
**crecimiento exponencial**, impulsado por el auge de las técnicas de
generación automática de contenidos (texto, imágenes, vídeo, etc.) y por
el desarrollo de agentes autónomos inteligentes. No obstante, en el
marco de este proyecto se ha optado por un enfoque **orientado a la
detección de patrones y comportamientos anómalos en datos
transaccionales**, utilizando para ello **algoritmos de aprendizaje
automático supervisado** (*supervised machine learning*).

Los **algoritmos de aprendizaje supervisado** son técnicas de
inteligencia artificial que se entrenan a partir de **datos previamente
etiquetados**, es decir, conjuntos en los que se conoce la respuesta o
categoría correcta. Su objetivo es **aprender patrones que permitan
predecir o clasificar nuevos casos desconocidos**.

En este proyecto, el *datalake* constituye el **componente central para
la generación de los *datasets* y el entrenamiento de los modelos**, al
proporcionar toda la información necesaria para dichas tareas. Además de
los datos procedentes de las *blockchains* analizadas, el datalake
integra información sobre **ataques previos**, **indicadores de
ciberseguridad** y **metadatos adicionales**, todos ellos puestos a
disposición de los modelos para su evaluación y mejora continua.

**Ámbito del entorno de Arquitectura e Infraestructura**

A parte de los grandes bloques comentados anteriormente: blockchain,
ciberseguridad, analítica de datos e inteligencia artificial, es
necesario establecer un **marco tecnológico que permita la
intercomunicación y procesado de la información de manera coordinada**.
Uno de los grandes retos transversales dentro de este proyecto ha sido
el de establecer una solución de arquitectura acorde a los requisitos
planteados especialmente "*REQ-0005: Monitorización en tiempo real*". El
cual establece unas condicionantes sobre la solución tecnológica, así
como la gestión de los flujos de comunicación. En este sentido, el resto
de las secciones relativas a los flujos de comunicación y los elementos
de arquitectura y monitorización, hacen referencia constante a las
necesidades particulares en este sentido y soluciones implementadas.

El siguiente diagrama, muestra una visión general de las soluciones de
infraestructura y tecnología en uso en este proyecto.

![[]{#_Toc210906544 .anchor}Ilustración 3 -- Ámbito tecnológico del
prototipo](media/image7.png){width="5.8625in"
height="2.8075754593175852in"}

Tengo en las secciones particulares de cada módulo, como dentro de la
sección *9. Arquitectura física del prototipo,* se hace una revisión de
la arquitectura final del prototipo, incluyendo los diagramadas y
componentes empleados en cada caso.

## Diseño Lógico

En la sección *3.1 Objetivos de la solución,* se han listado los
distintos componentes implicados en el diseño y la implementación de
este prototipo. Ahora, en el siguiente diagrama se hace un **esbozo de
los distintos módulos y las comunicaciones** entre los mismos. Estos
componentes corresponden con la estructuración lógica anteriormente
establecida, proporcionando una visión aun conceptual, pero más cercana
a los aspectos relativos a la arquitectura final del sistema. Este
diagrama se puede utilizar como **referencia para ayudar en la posterior
exposición de los módulos de la solución implementada**. De manera
general, la plataforma carga información de **dos tipos de fuentes**
principalmente: **blockchains y fuentes de información OSINT**.
Posteriormente **procesa esta información**, y la **transforma** de
acuerdo con las necesidades del módulo de **Inteligencia Artificial** y
las necesidades funcionales de la capa de presentación de resultados que
es la capa de consumen los usuarios finales de la solución.

![](media/image8.png){width="6.2375in" height="3.2548326771653544in"}

[]{#_Toc210906545 .anchor}Ilustración 4 -- Flujos de comunicación

### Módulos de la solución

A partir del diagrama anterior, téngase aquí una primera definición de
los módulos establecidos en el prototipo:

- **Ingesta de Datos** ^(REQ-0001)^

Módulo encargado de acceder y procesar la información procedente de las
distintas blockchains. Este módulo está formado principalmente por el
software requerido para acceder a cada blockchain. Junto con esto, se
dispondrá con los distintos scripts de procesamiento de datos para el
procesamiento de los datos y su posterior volcado dentro de los sistemas
de almacenamiento que proceda.

- **Enriquecimiento** ^(REQ-0002)^

Encargado de obtener los datos OSINT, y otras fuentes externas. Estas
fuentes se emplean dentro de la fase de enriquecimiento de la
información, agregando información adicional al modelo que
posteriormente va a ser empleada tanto para el módulo de inteligencia,
como desde el interfaz de usuario.

- **Módulo de gestión de datos (*DATALAKE*)** ^(REQ-0003)^

Repositorio de información donde se unifica la información procedente de
las distintas blockchains gestionados desde el módulo de ingesta de
datos, como de los módulos de recuperación de información externa.

La información almacenada en este sistema puede ser consumida a través
de una API REST. Esta API facilita el acceso a los datos, proporcionando
una puerta de acceso única y centralizada, así como una definición
coherente de las funcionalidades propuestas desde este módulo

- **Módulo de Inteligencia Artificial** ^(REQ-0004)^

Sistema de machine learning responsable del procesamiento de los datos y
la identificación de patrones. Este sistema es el encargado de
identificar el nivel de riesgo de una cartera, en base a las
transacciones en las que se ha visto envuelto y al resto de información
disponible (ciberinteligencia, fuentes externas y la propia blockchain).

- **Gestor de Eventos** ^(REQ-0005)^

Módulo encargado del procesamiento y seguimiento en tiempo real de la
información procedente de las distintas blockchains. Este módulo es el
responsable de la generación automática de alertas a partir a las
predicciones obtenidas por los modelos de IA haciendo uso de los datos
gestionados desde el módulo de datalake.

- **Solución Web** ^(REQ-0006\ y\ REQ-0008)^

Aplicación web a la que accederán los usuarios para consumir la
información gestionada dentro de esta plataforma. Esta aplicación
response a los casos de uso y funcionalidades establecidas, para el tipo
de usuario final (entidad usuaria) como los equipos de servicio de
Deloitte.

- **Módulo de Evidencias ^(REQ-0007)^**

En relación con el uso que se puede realizar de las evidencias y alertas
generadas a través del módulo de eventos, y el informe generado tras su
análisis, se establece un módulo que permite sellar digitalmente estas
evidencias, facilitando así su trazabilidad en caso de ser requerido por
un tercero o caso judicial.

- **Módulo de Monitorización** ^(REQ-0009)^

Módulo encargado de realizar el control y monitorización de la actividad
de la aplicación. Garantizando el correcto funcionamiento sincronizado
de todos los componentes, generando métricas y alarmas en los casos en
los que se detecte un comportamiento anormal de este prototipo.

### Flujos de datos ^(REQ-0005)^

La necesidad **de tiempo real** establecido por el requisito
*REQ-0005* - *Monitorización Continua*, obliga a tomar unas decisiones y
definir una **arquitectura para soportar los mecanismos y flujos de
comunicación entre los distintos módulos** de la solución de la manera
más eficiente posible.

Los módulos anteriores descritos (*3.2.1 Módulos de la solución*)
interactúan entre si estableciendo flujos de información que se van
propagando por todo el prototipo. Estos flujos van asociados con la
propia transformación del dato que, desde el origen de información, se
va adaptando a las necesidades establecidas en cada módulo de acuerdo
con los objetivos planteados en el proyecto. De esta forma, **cada
módulo es responsable de: recuperar el dato (si procede), procesarlo,
transformarlo y dejarlo disponible en los repositorios establecidos para
que los siguientes componentes de la solución puedan acceder a él y
procesarlo de la misma manera**.

La orquestación de estos flujos se realiza de acuerdo con las
tecnologías seleccionadas para este prototipo y que se describen en la
sección *9. Arquitectura Física del Prototipo*. Debido a la naturaleza
heterogénea de las distintas fuentes, las necesidades particulares de
cada módulo, la orquestación se tiene que adaptar en cada caso a las
necesidades particulares del flujo y de cada módulo concreto. Esta
adaptación se traduce en el uso particular del subconjunto de
tecnologías dentro del marco tecnológico establecido.

Veamos ahora los principales retos dentro de los flujos establecidos en
la solución, así como su modo de funcionamiento y características
principales:

**Pipeline de carga de datos de las blockchains**

Entre los objetivos principales destaca la necesidad de crear un dataset
centralizado de información, donde se vaya recopilando los datos
procedentes de las distintas blockchains, más toda la información de
enriquecimiento de fuentes externas. Centrándonos en las distintas
blockchains, se requiere el procesamiento de información de tres
blockchains diferentes (Bitcoin, Ethereum y Polygon). Cada una de estas
blockchains presentan una naturaleza y unas especificaciones
específicas, esto hace que se haga necesario realizar una integración
específica para cada caso, de acuerdo con las especificaciones
funcionales y técnicas de cada caso.

A continuación, se describen las características más relevantes de cada
blockchain desde el punto de vista de la ingesta de datos:

**Bitcoin** ^(ESF-0007)^

- **Naturaleza**: Bitcoin es una blockchain de propósito específico
  centrada exclusivamente en la transferencia de valor. Se caracteriza
  por una estructura simple basada en UTXOs (Unspent Transaction
  Outputs), lo que facilita el análisis de flujos de dinero, pero limita
  la expresividad respecto a otras blockchains con soporte de contratos
  inteligentes.

- **Ritmo de carga de datos**: La red de Bitcoin produce un bloque
  aproximadamente cada 10 minutos, lo que implica un ritmo de generación
  de datos más predecible y constante.

- **Volumetría**: Aunque el tamaño individual de las transacciones es
  generalmente menor que en Ethereum o Polygon, el alto número de
  transacciones diarias y el historial extenso de la cadena requiere
  mecanismos eficientes de indexado y almacenamiento incremental.

- **Tipo de operaciones**: Exclusivamente transacciones financieras
  (transferencias de BTC). No existen contratos inteligentes ni
  operaciones complejas a nivel de capa 1.

**Ethereum** ^(ESF-0008)^

- **Naturaleza**: Blockchain de propósito general que soporta contratos
  inteligentes (smart contracts) a través de la Ethereum Virtual Machine
  (EVM). Esto permite una gran variedad de operaciones más allá de
  simples transferencias de valor.

- **Ritmo de carga de datos**: Ethereum tiene un bloque nuevo
  aproximadamente cada 12 segundos, lo que genera un flujo de datos más
  constante y denso en comparación con Bitcoin.

- **Volumetría**: La variedad y complejidad de las transacciones
  (incluyendo interacciones con contratos, eventos, y tokens) implica
  una carga de datos significativamente mayor y estructuralmente más
  diversa.

- **Tipo de operaciones**: Transferencias de ETH, interacciones con
  contratos inteligentes, transacciones de tokens ERC-20 y ERC-721
  (NFTs), entre otras. Esto requiere un análisis más profundo del
  contenido de cada transacción.

**Polygon** ^(ESF-0009)^

- **Naturaleza**: Capa 2 o cadena lateral compatible con Ethereum que
  ofrece una solución de escalado basada en Proof of Stake (PoS). Está
  diseñada para ofrecer transacciones más rápidas y con menor coste.

- **Ritmo de carga de datos**: La red de Polygon produce bloques de
  forma muy rápida (cada 2-3 segundos), lo que representa un desafío en
  términos de ingesta continua y procesamiento casi en tiempo real.

- **Volumetría**: Debido a sus bajos costes y alta adopción para
  aplicaciones descentralizadas (dApps), Polygon maneja un gran volumen
  de transacciones diarias, con estructuras similares a Ethereum pero
  con una frecuencia y dispersión temporal considerablemente mayores.

- **Tipo de operaciones**: Al igual que Ethereum, incluye operaciones
  con tokens, contratos inteligentes, y aplicaciones DeFi y NFT. La
  compatibilidad con EVM permite reutilizar estructuras de análisis,
  aunque con consideraciones específicas de red.

Las características principales de este proceso son:

- Procesamiento de las blockchains de manera ágil y coordinada, en
  consonancia con la propia naturaleza y volumetría de estas.

- Volcar la información procesada dentro de un dataset con un interfaz
  unificado para facilitar el acceso y gestión de la información.

- Capacidad de monitorización

- Capacidad de auditoria

![[]{#_Toc210906546 .anchor}Ilustración 5 -- Diagrama conceptual ingesta
de datos in-chain](media/image9.png){width="5.416666666666667in"
height="3.0585804899387576in"}

Dentro de los documentos *ENT-0003*, *ENT-0003.1, ENT-0003.2 y
ENT-0003.3 -- Estudio alternativas de ingesta* se describen los
pormenores del estudio realizado para cada caso, y las decisiones
tomadas para cubrir este requisito. Por otro lado, en la *sección 4 --
Ingesta blockchains*. Se describe el estado final.

**Pipeline de carga de datos off-chain**

Además de la información proveniente directamente de las redes
blockchain, el sistema requiere la integración de fuentes de datos
externas (off-chain) que aporten contexto, enriquecimiento y
trazabilidad a los análisis realizados. Este módulo tiene como objetivo
incorporar información complementaria, esencial para el entendimiento
completo de ciertas actividades sospechosas dentro del ecosistema
cripto, especialmente aquellas relacionadas con **campañas de
ransomware,** ciberamenazas y operaciones de blanqueo de capitales.

Las fuentes off-chain que se integran en este pipeline pueden
clasificarse en dos grandes categorías:

- **Fuentes de ciberinteligencia propias** ^(ESF-0016,\ ESF-0017)^:
  Información estructurada y no estructurada proporcionada por los
  equipos de ciberseguridad de Deloitte. Este conocimiento incluye
  indicadores de compromiso (IOCs), patrones de comportamiento asociados
  a actores maliciosos, direcciones de wallets vinculadas a actividades
  ilícitas, entre otros datos clave para la atribución de eventos en la
  cadena.

- **Fuentes gubernamentales y open source (OSINT)**
  ^(ESF-0016,\ ESF-0017)^: Repositorios públicos o institucionales que
  publican listas negras, alertas sobre campañas activas, registros de
  sanciones, y otras bases de datos relevantes para el análisis
  financiero forense. Estas fuentes permiten ampliar el marco de
  referencia y correlacionar eventos on-chain con entidades o
  actividades monitorizadas por organismos oficiales.

- **Otras fuentes adicionales** ^(ESF-0016,\ ESF-0015)^: Repositorios y
  fuentes de información privados, disponibles de acuerdo con las
  necesidades particulares de los usuarios y clientes de la solución.

Este pipeline se encarga de orquestar la recolección, normalización,
validación y almacenamiento de estos datos off-chain, permitiendo su
integración dentro del **Datalake** del proyecto ^(ESF-0011)^. Su
correcta implementación es fundamental para enriquecer las capacidades
analíticas del sistema, facilitando un enfoque de análisis híbrido
(on-chain y off-chain) necesario para investigaciones avanzadas en
ciberseguridad y cumplimiento normativo.

Las características principales de este módulo son:

- Actualización constante de la información a través de conectores que
  recurrentemente van procesando esas fuentes

- Trazabilidad de la fuente de información, para facilitar así su
  gestión.

- Capacidad de adaptación a nuevas fuentes y formatos

- Capacidad de monitorización

- Capacidad de auditoría y trazabilidad de la información

![[]{#_Toc210906547 .anchor}Ilustración 6 -- Diagrama conceptual ingesta
de datos off-chain](media/image10.png){width="4.160775371828522in"
height="2.4097222222222223in"}

En este caso, el entregable *ENT-0004 --* *Estudio de alternativas para
el pipeline de datos* habla de las alternativas evaluadas, y establece
el estudio realizado y el marco tecnológico para soportar las operativas
de conectividad y carga de datos desde diversas fuentes distintas.

**Pipeline de entrada al módulo de inteligencia**

El módulo de inteligencia artificial (IA) constituye uno de los
componentes estratégicos del sistema, ya que aporta capacidades
avanzadas de análisis, detección y predicción sobre los datos blockchain
y off-chain integrados en el Data Lake. Para habilitar su
funcionamiento, se ha desarrollado un **pipeline de entrada** que actúa
como puente entre el entorno de almacenamiento masivo y el motor de
modelos de IA, facilitando un flujo de datos eficiente y estructurado.

Este pipeline está diseñado para cubrir dos casos de uso principales:

- **Entrenamiento iterativo de modelos** ^(ESF-0024)^: El sistema debe
  permitir la extracción selectiva de datos históricos y etiquetados
  desde el Data Lake, necesarios para entrenar modelos supervisados o no
  supervisados. Esta información puede incluir patrones transaccionales,
  comportamientos de wallets, indicadores de campañas de ransomware y
  otros factores de riesgo identificados previamente. El pipeline se
  encarga de transformar estos datos en formatos compatibles con los
  entornos de entrenamiento, incluyendo procesos de agregación,
  limpieza, balanceo y etiquetado.

- **Ejecución de modelos (predicción)**: Una vez desplegados, los
  modelos de IA necesitan acceso a datos actuales o en tiempo casi real
  para realizar inferencias. El pipeline permite alimentar estos modelos
  con información reciente extraída del Datalake, ya sea para ejecutar
  análisis programados o responder a eventos desencadenantes. El
  objetivo principal en esta etapa es la **detección automática y
  temprana de patrones asociados a campañas de ransomware** u otras
  amenazas relevantes en el contexto de las blockchains monitorizadas.

Este componente garantiza así una **conectividad robusta y flexible
entre el sistema de almacenamiento y los modelos de IA**, asegurando la
trazabilidad y la calidad de los datos utilizados tanto para la mejora
continua del rendimiento algorítmico como para la toma de decisiones
automatizadas en el entorno de análisis forense y ciberinteligencia
financiera.

Estos dos casos de uso presentan ciertas similitudes que permiten la
creación de una solución genérica de integración para el pipeline de
datos. Los requisitos principales son:

- Permitir la ejecución automática del modelo con los bloques publicados
  en la blockchain en un rango de tiempo establecido.

- Permitir seleccionar otros rangos distintos, si fuese necesario lanzar
  reevaluaciones si se dispone de más información.

- Generación de los de auditoria para facilitar la trazabilidad

![[]{#_Toc210906548 .anchor}Ilustración 7 -- Pipeline de transmisión a
módulo de IA](media/image11.png){width="5.102777777777778in"
height="2.361613079615048in"}

Además de ahondar en el análisis de los modelos entrenados y sus
características, dentro de la sección dedicada al módulo de inteligencia
artificial (sección 7) se hace una revisión sobre los aspectos técnicos
de esta integración.

**Pipeline de procesado de información y generación de alertas**
^(ESF-0028)^

El objetivo principal de este proyecto es el de crear una solución que
permita identificar, mediante técnicas de inteligencia artificial,
actividad maliciosa relacionada con casos y campañas de ransomware
dentro de las blockchains.

Complementando este caso de uso, existen otras capacidades adicionales
como el seguimiento del estado de una cartera, o la relación que se
pueda identificar entre una determinada transacción, y el blanqueo de
capitales.

Estos hallazgos se gestionarán con el nombre de alerta. Una alerta
corresponde con la identificación de una casuística concreta,
estableciendo unas propiedades y descripciones acordes al elemento
identificado.

Desde una perspectiva técnica, existe una necesidad de establecer
mecanismos para el procesamiento de los elementos gestionados dentro del
datalake, y el módulo de inteligencia artificial, para la identificación
de los eventos concretos que tengan que ser publicados como alertas que
luego tengan que ser gestionados.

Las características principales de este sistema son:

- Procesamiento en tiempo real: monitorización del *datalake*,
  incluyendo los flujos de datos correspondientes a las distintas
  blockchains, información de enriquecimiento y motor de inteligencia
  artificial.

- Gestión de reglas de negocio sobre las características esperadas en
  las alertas a generar

- Capacidad de establecer relaciones entre eventos con el objetivo de
  poder generar alertas avanzadas

![[]{#_Toc210906549 .anchor}Ilustración 8 -- Pipeline de generación de
alertas](media/image12.png){width="4.724609580052493in"
height="2.464253062117235in"}

Dentro de la sección de *Gestión de Eventos y Motor de Reglas* de este
mismo documento, se entre en detalle de las características internas y
capacidades de este módulo, así como de las interrelaciones con otros
subsistemas de la aplicación.

### Otros elementos transversales de la solución

La **trazabilidad** ^(ESF-0035)^ es fundamental a la hora de garantizar
el seguimiento de cada transacción, permitiendo reconstruir con
precisión el recorrido completo de los datos desde su origen hasta su
procesamiento final. Este aspecto resulta crítico no solo para fines de
auditoría y verificación, sino también para **detectar anomalías** en
tiempo real y anticipar posibles incidentes.

Asimismo, el control de las volumetrías de datos se convierte en un
desafío adicional, ya que el sistema debe ser capaz de gestionar y
analizar un flujo constante y creciente de información sin comprometer
su rendimiento. La monitorización continua de estos volúmenes posibilita
detectar picos inusuales de actividad que podrían estar asociados a
intentos de fraude o ataques coordinados.

El **seguimiento extremo a extremo** de los flujos garantiza que todas
las etapas ---desde la ingesta de datos en el datalake hasta la
generación de predicciones en los modelos de inteligencia artificial---
estén sujetas a un control exhaustivo, evitando puntos ciegos y
asegurando la coherencia de la información procesada. En este contexto,
la monitorización deja de ser un simple complemento para convertirse en
un componente esencial de la solución, aportando confianza,
transparencia y capacidad de respuesta frente a las amenazas.

## Modos de ejecución de la solución (online vs. histórico) ^(REQ-0005)\ (OBJ-0004)^

La plataforma opera en **dos modos** complementarios:

- **Online / tiempo real**: ingesta continua desde las blockchains
  (bloques / transacciones) y fuentes off‑chain, procesado inmediato,
  enriquecimiento y evaluación por el **módulo de IA** y el **motor de
  eventos y reglas**, con generación de **alertas** en tiempo real. Ver
  esqueda en la sección 8 "*Gestor de eventos y motor de reglas*".

- **Histórico**: ejecución parametrizada por **rango de bloques**
  (bloque_inicio--bloque_fin) para re‑procesar datos pasados. Se ejecuta
  en **paralelo** al online dentro de un **pipeline aislado** (Airflow)
  para no interferir con el modo en tiempo real. Esta modo o tipo de
  ejecución cubre uno de los objetivos del proyecto ^(OBJ-0004)^ y
  provee a este sistema de la capacidad simular y ejecutar bloques
  históricos.

![[]{#_Toc210906550 .anchor}Ilustración 9 -- Gestión serie temporal
histórica](media/image13.png){alt="A diagram of a flowchart AI-generated content may be incorrect."
width="6.102083333333334in" height="3.432638888888889in"}

**Implementación modo histórico (alto nivel)**

- **Orquestación**: **Airflow** lanza jobs de ingesta histórica,
  coordina dependencias y despliegue de **instancias dedicadas** del
  evaluador de eventos/IA para ese rango.

- **Aislamiento**: publicación en **tópicos Kafka específicos** para
  entrar en el sistema de forma aislada y que sean evaluados en las
  instancias dedicadas al modo histórico.

- **Procesado**: los mismos módulos de **IA** y **reglas** se ejecutan
  con **config a medida** (rango/versión de modelo) sobre el histórico.

- **Salida**: resultados / alertas **separados** (p. ej.,
  índices/streams alerts.historic.\*) y **logs** en **Log Groups**
  dedicados (sufijo -historic).

# INGESTA BLOCKCHAINS 

El proceso de ingesta, es decir, de obtención de los datos de las
blockchains públicas de Bitcoin, Ethereum y Polygon es un proceso
complejo, pues cada una tiene su contexto, diferencias técnicas y
propósito. Es por ello, que para facilitar la tarea debido a la
complejidad e ir avanzando en otros aspectos del proceso se ha realizado
en el orden que se indicará a continuación, donde se verá resumido cada
proceso. Si se quiere ver el proceso más en detalle véase el entregable
0003-01 *Ingesta Bitcoin* para Bitcoin, 0003-02 *Ingesta Ethereum* para
Ethereum y 0003-03 *Ingesta Polygon* para Polygon.

## Bitcoin

Las principales características técnicas que afectan al proceso de
ingesta son las siguientes:

- Sistema de consenso: Proof of Work

- Ratio de publicación de bloques: 10 minutos

- Media de transacciones por bloque: 3.500

- Transacciones por segundo: 6

En octubre del 2025, cuando se realiza este informe, el estado general
de la blockchain es el siguiente:

- Tamaño total: 690 GB

- Total bloques: 916 mil

- Total transacciones: 1.250 mil millones

Se han detectado tres áreas en las que elegir tecnologías y se han
elegido las siguientes:

- [Fuente de datos]{.underline}: se ha elegido Bitcoin Core, pues la
  fuente oficial y pública de datos de Bitcoin, por ende la más
  transparente y fiable.

- [Sistema de almacenamiento]{.underline}: se eligió el gestor de base
  de datos relacional Postgres por la buena gestión que hace de grandes
  volúmenes de datos.

- [Obtención de datos]{.underline}: se ha elegido Python para realizar
  un script ya que es un lenguaje de programación moderno, actualizado y
  con muchas librerías para conectar con el nodo Bitcoin.

> El producto final de la ingesta se verá en alto nivel en el siguiente
> diagrama:

![[]{#_Toc210906551 .anchor}Ilustración 10 - Ingesta
Bitcoin](media/image14.png){alt="A diagram of a flowchart AI-generated content may be incorrect."
width="3.2256649168853895in" height="4.483333333333333in"}

El proceso consiste básicamente en la obtención de datos de un bloque,
procesado y almacenado tanto en base de datos, como en sistema de
archivos y posterior envío a Kafka para ser procesado en tiempo real.

## Ethereum

Ethereum supone un cambio de paradigma de las blockchain no solo en
cuanto a capacidades técnicas como se verá a continuación sino porque
introduce el concepto de ejecución de código con los Smart Contracts lo
que multiplica de las posibilidades de uso de la misma y también su
complejidad, tanto en extracción como en almacenado y procesado. A pesar
de este aumento de la dificultad, los aprendizajes realizados en Bitcoin
en cuanto a procesado de datos y limitaciones han sido clave para la
optimización de este proceso.

Las principales características técnicas que afectan al proceso de
ingesta son las siguientes:

- Sistema de consenso: Proof of Stake (tuvo Proof of Work hasta 2022).

- Ratio de publicación de bloques: 12 segundos

- Media de transacciones por bloque: 170

- Transacciones por segundo: 16

En octubre del 2025, cuando se realiza este informe, el estado general
de la blockchain es el siguiente:

- Tamaño total: 1.45 TB

- Total bloques: 23 millones

- Total transacciones: 3.02 mil millones

Se han detectado tres áreas en las que elegir tecnologías y se han
elegido las siguientes:

- [Fuente de datos]{.underline}: se ha elegido Reth como cliente de
  ejecución y Nimbus como cliente de consenso, ambos produciendo una
  buena combinación entre velocidad y eficiencia en la gestión de
  recursos.

- [Sistema de almacenamiento]{.underline}: se eligió el gestor de base
  de datos relacional Postgres por la buena gestión que hace de grandes
  volúmenes de datos.

- [Obtención de datos]{.underline}: se ha elegido Python para realizar
  un script ya que es un lenguaje de programación moderno, actualizado y
  con muchas librerías para conectar con el nodo de Ethereum.

> El producto final de la ingesta se verá en alto nivel en el siguiente
> diagrama:

![[]{#_Toc210906552 .anchor}Ilustración 11 -- Ingesta
Ethereum](media/image15.png){alt="A diagram of a diagram AI-generated content may be incorrect."
width="3.4in" height="5.465096237970254in"}

El proceso consiste en obtener datos de varias estructuras, como
bloques, *receipts* o logs del nodo de forma concurrente, se procesan y
se almacenan en sistema de archivos, base de datos y se envían a Kafka
para procesado en tiempo real.

Además, se han obtenido mediante fuentes externas datos sobre tokens
fungibles y NFTs para hacer un seguimiento de los más relevantes de
forma fiable. Los criterios que se han utilizado para la selección de
tokens son de índole económica.

## Polygon

Dado que Polygon es un ecosistema con varias blockchains, con ese nombre
nos referiremos ahora a Polygon PoS, una cadena de bloques tipo
sidechain de Ethereum compatible con EVM, el motor ejecutor de código de
Ethereum cuyo método de consenso es Proof of Stake y su token nativo es
Polygon Ecosystem Token o POL, anteriormente conocido como MATIC.

Las principales características técnicas que afectan al proceso de
ingesta son las siguientes:

- Sistema de consenso: Proof of Stake

- Ratio de publicación de bloques: 2 segundos

- Media de transacciones por bloque: 83

- Transacciones por segundo: 40

En octubre del 2025, cuando se realiza este informe, el estado general
de la blockchain es el siguiente:

- Tamaño total: 4.1 TB (abril 2024)

- Total bloques: 77 millones

- Total transacciones: 5.7 mil millones

Es capaz de procesar 6 veces más transacciones que Ethereum y requiere
de muchas más capacidades técnicas como se pondrá a continuación.
Además, el hecho de ser muy novedosa hace que los cibercriminales no la
hayan adoptado como activo a usar y tenga muy pocas transacciones
maliciosas, como se detalla en el entregable ENT-0006 *Estudio
comparativo de técnicas de inteligencia artificial para clasificación
automática de actores*, por lo que no se hará un proceso de ingesta como
en Bitcoin o Ethereum, sino que se proveerá de datos al motor de tiempo
real de Kafka únicamente, sin almacenado en base de datos o sistema de
archivos.

Se han detectado tres áreas en las que elegir tecnologías y se han
elegido las siguientes:

- [Fuente de datos]{.underline}: se ha elegido la API de Alchemy, pues
  se trata de un proveedor asentado en el mercado de las criptomonedas
  al tener datos de toda índole.

- [Sistema de almacenamiento]{.underline}: se eligió el gestor de base
  de datos relacional Postgres por comodidad y armonizar con el resto
  del sistema, pues no se van a manejar grandes volúmenes de datos.

- [Obtención de datos]{.underline}: se ha elegido Python para realizar
  un script ya que es un lenguaje de programación moderno, actualizado y
  con muchas librerías.

> El producto final de la ingesta se verá en alto nivel en el siguiente
> diagrama:

![[]{#_Toc210906553 .anchor}Ilustración 12 -- Ingesta
Polygon](media/image16.png){alt="A diagram of a process AI-generated content may be incorrect."
width="3.5166666666666666in" height="4.13619750656168in"}

El obtiene datos de los bloques de Polygon de la API, se procesan y se
envían a Kafka para procesado en tiempo real.

Al igual que en Ethereum, se han obtenido mediante fuentes externas
datos sobre tokens fungibles y NFTs para hacer un seguimiento de los más
relevantes de forma fiable.

# ENRIQUECIMIENTO DE INFORMACION

Dentro de los requisitos establecidos para este proyecto se encuentra el
disponer de un subsistema que permita el enriquecimiento desde fuentes
externas.

La solución de ingeniería propuesta para la detección automática de
actividad de *ransomware* en la *blockchain* mediante Inteligencia
Artificial (IA) subraya la **dependencia de fuentes de datos externas.**
^REQ-0002^

**El Valor Estratégico de los Datos Externos**

La integración de estos datos adicionales es **esencial** por múltiples
motivos, que aporta valor en distintas fases del sistema:

1.  **Entrenamiento y Creación de *Datasets***: Actúan como una de las
    fuentes primarias de información para **generar los *datasets***
    (conjuntos de datos) empleados en el entrenamiento de los modelos de
    IA.

2.  **Validación y Solidez del Sistema**: Permiten **refrendar y validar
    los resultados** (*outputs*) generados por la IA. Esto aporta una
    mayor **solidez y confianza** al sistema de detección y la
    generación de métricas para evaluar su rendimiento.

3.  **Valor al Usuario Final o Analista**: La información obtenida puede
    ser **consultada por los usuarios**, enriqueciendo su experiencia y
    ofreciendo valor añadido, de acuerdo con los criterios de negocio
    como pueden ser el estudio y la correlación de distintas fuentes de
    información.

4.  **Información Actualizada**. Los propios sistemas de
    enriquecimiento, que se ejecutan de manera autónoma y programada,
    permiten que el propio sistema incluya información que vaya
    ampliando la base de conocimiento existente.

De acuerdo con el procedimiento establecido, dentro de los documentos
ENT-0004 *Estudio de alternativas para el pipeline de datos* y ENT-0005
*Estudio comparativo de alternativas de enriquecimiento*, se abordan
temas relativos a los estudios de identificación de las fuentes por un
lado, y de evaluación de la solución técnica que mejor se ajusta a las
necesidades planteadas.

En este documento se describe la solución de ingeniería aplicada, así
como otros aspectos singulares que han sido identificados tras este
desarrollo.

Dentro de las **necesidades** establecidas para este módulo está la de
**establecer mecanismos para la ingesta** de información de fuentes de
diversa naturaleza, así como su procesamiento y alojamiento dentro del
Datalake a través de los mecanismos que se han establecido.

Dentro del *estudio de fuentes de información* se ha observado que
existe una gran diversidad de tipos de fuentes: API REST, acceso a
páginas web, procesamiento de documentos, ingesta manual. Esta
diversidad hace que la solución de tecnología tenga que ser lo
suficientemente versátil y adaptable a los distintos casos. En el
siguiente punto listaremos los mecanismos de ingesta establecidos dentro
de este prototipo.

## Tipos de integraciones soportados 

La herramienta desarrollada para la trazabilidad de pagos de ransomware
incorpora un conjunto variado de integraciones que permiten la ingesta y
monitorización de direcciones de wallets procedentes de diferentes
fuentes. El objetivo es garantizar que la información relevante pueda
ser recogida de manera flexible, independientemente de dónde se publique
o difunda.

A continuación, se describen los principales tipos de integraciones
soportados.

**Ingesta manual (CLI)**

La integración manual permite introducir direcciones de wallets de forma
directa mediante línea de comandos. Esta modalidad resulta útil en
situaciones donde un analista necesita añadir rápidamente información
procedente de un informe, alerta o investigación puntual.

- Facilita la incorporación inmediata de direcciones críticas.

- No depende de conectores externos.

- Se utiliza principalmente en escenarios de respuesta a incidentes.

![[]{#_Toc210906554 .anchor}Ilustración 13 -- CLI de carga de
información
off-chain](media/image17.png){alt="A black screen with white text AI-generated content may be incorrect."
width="6.102083333333334in" height="1.0421303587051618in"}

**Integraciones automáticas**

La herramienta soporta la automatización de la ingesta a través de
procesos programados. De este modo, las nuevas direcciones pueden ser
incorporadas de manera continua sin intervención manual.

- Reduce la carga de trabajo de los analistas.

- Garantiza actualizaciones periódicas y consistentes.

- Escalable para manejar grandes volúmenes de información.

![[]{#_Toc210906555 .anchor}Ilustración 14 -- Airflow -- Integraciones
programáticas](media/image18.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.459417104111986in"}

**Acceso a páginas web**

El scraping de sitios web es otro de los mecanismos de integración.
Muchas fuentes públicas (blogs, foros, páginas de noticias de
ciberseguridad o incluso sitios vinculados a grupos criminales) publican
direcciones de wallets que pueden ser extraídas de forma automática.

- Permite acceder a información sin necesidad de API.

- Se adapta a distintos formatos (HTML, PDF, foros).

- Aumenta la cobertura de inteligencia disponible.

**Acceso a APIs**

La integración con APIs externas representa uno de los mecanismos más
robustos. La herramienta puede conectarse a servicios especializados en
blockchain e inteligencia de amenazas para obtener datos en tiempo real.

- Soporte para APIs de exploradores de blockchain (Etherscan,
  Blockchain.com, etc.).

- Conexión con proveedores de inteligencia (Chainalysis, Arkham).

- Posibilidad de enriquecer las wallets con metadatos (tags, histórico
  de transacciones, balances).

**Acceso a redes sociales**

Las redes sociales se han convertido en un canal donde se difunde
información relevante. Actores criminales, investigadores de seguridad o
víctimas publican direcciones de pago en plataformas como Twitter/X,
Telegram o Discord.

- Permite capturar información en tiempo real.

- Cubre tanto publicaciones públicas como privadas (previa integración).

- Complementa la inteligencia procedente de fuentes tradicionales.

![[]{#_Toc210906556 .anchor}Ilustración 15 -- Captura Ingesta
Telegram](media/image19.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="4.642361111111111in"}

**Acceso a la dark web**

Finalmente, la herramienta cuenta con conectores para recopilar
información en la dark web. En este espacio se localizan muchas de las
publicaciones directas de los grupos de ransomware, incluyendo paneles
de víctimas, notas de rescate o foros clandestinos.

- Permite acceder a sitios onion y foros especializados.

- Identifica direcciones publicadas directamente por actores criminales.

- Aporta inteligencia de difícil acceso y alto valor para las
  investigaciones.

**Conclusión**

El enfoque de la herramienta permite combinar la ingesta manual, la
automatización y la conexión con múltiples fuentes de información.
Gracias a esta flexibilidad, es posible centralizar y monitorizar en un
único entorno direcciones de wallets procedentes de canales abiertos,
APIs especializadas, redes sociales y la dark web.

**De esta manera, el sistema asegura una cobertura integral frente a las
diferentes formas en que los actores de ransomware difunden sus
direcciones de pago.**

## Componentes funcionales

La siguiente imagen muestra las características principales de la
solución que se ha propuesto.

![[]{#_Toc210906557 .anchor}Ilustración 16 -- Diagrama lógico
enriquecimiento de datos](media/image20.png){width="5.576080489938757in"
height="2.947826990376203in"}

La orquestación y automatización de flujos de trabajo se ha utilizado
Apache Airflow. Airflow es una plataforma open source diseñada para
programar, monitorizar y gestionar **flujos de trabajo complejos a
través de una interfaz declarativa** basada en Python. Permite definir
dependencias entre tareas, programar ejecuciones periódicas y manejar la
lógica de reintentos o notificaciones en caso de fallos. Gracias a su
arquitectura modular y extensible, Airflow se integra fácilmente con
múltiples sistemas y herramientas (como bases de datos, APIs, servicios
cloud o sistemas de archivos), lo que lo convierte en una solución
robusta y flexible para gestionar procesos de integración de datos, ETL
y pipelines de machine learning dentro del ecosistema del proyecto.

![[]{#_Toc210906558 .anchor}Ilustración 17 -- Captura sistema de
enriquecimiento](media/image21.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.5083333333333333in"}

En la sección de arquitectura física se detalla el conjunto de elementos
integrados dentro de Airflow.

  ----------------------------------------------------------------------------------------------
  **Nombre**                   **Proposito de         **Period..(\*)**   **Modo**   **código**
                               Integración**                                        
  ---------------------------- ---------------------- ------------------ ---------- ------------
  20_ingest_ransomwhe_re       Obtención de la        24 horas           API        ESF-0016
                               información                                          
                               proporcionada por este                               
                               proveedor                                            

  21_ingest_ofac               Obtención de           24 horas           PDF        ESF-0021
                               información de                                       
                               entidades y carteras                                 
                               de criptoactivos                                     
                               sancionados                                          

  22_ingest_chainabuse         Obtención de           24 horas           Crawler    ESF-0016
                               información de                                       
                               carteras empleadas                                   
                               para la recepción de                                 
                               pagos de ransomware                                  

  23_ingest_ransomlook         Obtención de           24 horas           Crawler    ESF-0017
                               información                                          
                               proporcionada por                                    
                               ransomlook                                           

  24_telegram                  Descarga de contenidos 8 horas            API        ESF-0015
                               de canales de Telegram                               

  25_ingest_ectfsl_countries   Descarga lista de      24 horas           PDF        ESF-0021
                               países sancionados por                               
                               la UE                                                

  60_blockdaemon               Enriquecimiento de     1 hora             API        ESF-0016
                               información                                          
                               proporcionada por                                    
                               blockdaemon                                          

  61_enrich_etherscan          Enriquecimiento de     1 hora             API        ESF-0016
                               información                                          
                               proporcionada por                                    
                               Etherscan                                            

  90_tools                     Informacion OSINT      8 horas            API        ESF-0017
                               Tools empleadsa para                                 
                               ransomware                                           

  91_actores                   Información the Threat 8 horas            API        ESF-0021
                               Actors con actividad                                 
                               de ransomware                                        

  92_events                    Información de         8 horas            API        ESF-0014
                               campañas y otros                                     
                               eventos de ransomware                                
  ----------------------------------------------------------------------------------------------

  : []{#_Toc210906529 .anchor}Tabla 4 -- Integración de fuentes externas
  off-chain ^(ESF-23)^

Nota (\*): Las Apache Airflow incluye un mecanismo de reintentos si la
operación falla por algún motivo.

## Agrupación de la información

Tal como se mencionó previamente, una de las capacidades clave del
sistema reside en la **automatización y programación de los
conectores**. Esto permite mantener actualizada la información, ya sea
incorporando datos de nuevas campañas o eventos, o mejorando aquellas
que no son tan recientes.

**Correlación de datos**

El diseño del sistema facilita de manera nativa la **correlación entre
múltiples fuentes de información**. Cada fuente incorpora entidades
junto con su metainformación, la cual puede variar en nivel de detalle
según el origen y la naturaleza del dato.

Para maximizar el valor de esta información, el sistema ejecuta procesos
de exploración continua sobre los datos ya cargados, identificando
vínculos potenciales con otros elementos provenientes de diferentes
fuentes. Este mecanismo habilita la **generación automática de clústeres
de entidades relacionadas**, aunque su procedencia sea diversa.

El resultado es un **aumento exponencial del valor analítico**, ya que
la información correlacionada permite ejecutar rastreos más precisos
dentro del *datalake*, además de mejorar la capacidad de atribución de
hallazgos, reforzando tanto la detección como el análisis de amenazas.

![[]{#_Toc210906559 .anchor}Ilustración 18 -- Ejemplo correlación:
países, carteras, entidades OFAC y
Ciberactores](media/image22.png){alt="A diagram of a network AI-generated content may be incorrect."
width="6.102083333333334in" height="2.997916666666667in"}

![[]{#_Toc210906560 .anchor}Ilustración 19 -- Ejemplo correlación:
Ciberactores (gris), CVEs empleados en ataques
(azul)](media/image23.png){alt="A screenshot of a computer screen AI-generated content may be incorrect."
width="6.102083333333334in" height="2.9375in"}

Dentro de la sección *6. Datalake* se describe con más detalle el
esquema de la información, describiendo las entidades, sus metadatos y
relaciones entre ellas.

# DATALAKE

## Aspectos Generales

Dentro de las características requeridas para este proyecto, se incluye
la necesidad de generar una **capa de persistencia en el que ir cargando
y gestionando la información procedente de los distintos orígenes
establecidos**. Dentro de la sección de flujos de datos de este
documento ya se ha entrado en detalle a aclarar las características y
aspectos más generales de estos procesos de ingesta de información.
Estos datos ingestados pasan a través de los procesos de transformación
(ETL) para luego ser almacenados dentro del datalake de este prototipo.

El **datalake** constituye el **repositorio central de información** del
proyecto, integrando datos **on-chain** y **off-chain** de diversas
fuentes. En él se concentra el **conocimiento acumulado por los equipos
de ciberseguridad de Deloitte** durante los últimos años, incluyendo
información histórica de campañas y fuentes OSINT. Esta combinación
convierte al datalake en una **pieza única y de gran valor**, esencial
para el entrenamiento y aplicación de los modelos de inteligencia
artificial del sistema.

![[]{#_Toc210906561 .anchor}Ilustración 20 -- Fuentes de datos de
datalake](media/image24.png){width="3.095833333333333in"
height="1.9020570866141733in"}

Existe una gran **diversidad y heterogeneidad** entre las distintas
fuentes de datos. Dentro de las necesidades del proyecto se identifican
fuentes con una fuerte componente jerárquica y relacional. En este tipo
de fuente se incluyen los datos relativos a bloques, transacciones,
billeteras, de las distintas blockchains incluidas en este proyecto.
Adicionalmente también se dispone de otros datos donde, si bien si
existe una necesidad relacional, no presenta una componente jerárquica.
Aquí se incluyen datos como países, ciber delincuentes, CVEs, IPs,
campañas de ransomware, etc. Esta diversidad tanto de formato, como de
la propia naturaleza del dato provoca que la misma **capa de
persistencia tenga que cubrir una gran diversidad de escenarios y
casuísticas de gestión y acceso**. Por un lado, datos como los propios
de la **blockchain** encajan dentro de un **modelo relacional**
tradicional, donde la información se almacena dentro de una base de
datos (PostgreSQL) en una serie de tablas e índices que faciliten su
gestión y acceso. Por otro lado, la naturaleza más genérica y amplia de
los datos proporcionados durante el enriquecimiento de información
requieren un modelo de gestión donde, si bien es necesario establecer
relaciones entre elementos, estas relaciones no están asociadas con un
metamodelo, sino de los propios elementos en sí. Para esta situación
hacemos uso de una base de datos de grafos (neo4j).

Adicionalmente, se establecen otras soluciones de persistencia dentro
del datalake, como un sistema de fichero, para almacenar otros tipos de
recursos que se puedan adaptar a este tipo de solución. En este tipo de
almacenamiento se incluye la información en crudo de los datasources,
así como otros elementos intermedios generados durante los procesos de
transformación.

## Gestión de Datos Relacionales 

Las tecnologías blockchain han transformado la manera en que se concibe
el almacenamiento y la transmisión de información en entornos
distribuidos y descentralizados. Entre las redes más representativas se
encuentran **Bitcoin**, **Ethereum** y **Polygon**, cada una con
particularidades técnicas que responden a distintos casos de uso dentro
del ecosistema cripto. Bitcoin se orienta principalmente a la
transferencia de valor de forma segura y sin intermediarios. Ethereum,
por su parte, introduce la computación distribuida mediante contratos
inteligentes, lo que amplía significativamente sus capacidades. Polygon
actúa como una solución de escalabilidad para Ethereum, proporcionando
transacciones más rápidas y económicas, sin renunciar a la
compatibilidad con la máquina virtual de Ethereum (EVM).

**El volumen de información** generado por estas redes, en forma de
bloques, transacciones, contratos, eventos y direcciones, plantea **un
reto significativo en cuanto a su almacenamiento, indexación y
recuperación eficiente**. Aunque las blockchains están diseñadas como
sistemas de almacenamiento distribuido e inmutable, no están optimizadas
para consultas complejas o búsquedas flexibles desde el punto de vista
analítico o exploratorio.

En este contexto, se ha propuesto un **modelo de base de datos
relacional que permita almacenar y consultar datos provenientes de estas
tres cadenas**. Al aprovechar las capacidades de PostgreSQL ---un
sistema de gestión de bases de datos robusto, extensible y conforme al
estándar SQL--- se facilita la normalización, integridad referencial y
eficiencia en las consultas. Este enfoque permite abstraer las
diferencias técnicas entre las blockchains y ofrecer una estructura
homogénea para el análisis transversal, la visualización de métricas o
el desarrollo de herramientas basadas en datos históricos y en tiempo
real.

Dentro de los entregables ENT-0003 *Ingesta desde blockchain*, 0003-01
*Ingesta* *Bitcoin*, 0003-02 *Ingesta Ethereum* y 0003-03 *Ingesta
Polygon*, se encuentran la descripción y el análisis efectuado hasta
llegar a esta solución de ingeniería.

La base de datos PostgreSQL cumple el propósito de almacenar e indexar
^(ESF-0013)^ la información *in-chain* procedente de las distintas
*blockchains* requeridas, proporcionando mecanismos para el acceso a los
datos requeridos de manera eficiente, así como la generación de
estadísticas, o cuadros contables de las direcciones o billeteras
seleccionadas.

La gran volumetría de información, así como los distintos ritmos de
almacenamiento ha provocado que se utilice una instancia separada por
cada blockchain. Permitiendo así gestionar los datos y establecer las
claves de acceso más acordes a las especificaciones de cada blockchain.

A continuación, se expondrán los modelos de datos usados para cada una
de las blockchains:

### Bitcoin

Se ha hecho una distinción de los distintos tipos de datos y se han
separado en tablas. Además, se ha añadido una tabla para hacer sumas y
consultas optimizadas en cuanto a balances de direcciones y datos sobre
trazabilidad y transacciones en la tabla ACCOUNT_BALANCES, donde hay una
entrada para cada input o output, teniendo el valor positivo si es un
output, pues se reciben divisas o negativo si es input, pues se envían.

Este enfoque hace que no haya demasiada redundancia de información, pero
se cumplan unas consultas rápidas gracias a los índices situados en las
columnas de mayor uso necesarias para las búsquedas, como fechas,
direcciones o id de transacciones.

![[]{#_Toc210906562 .anchor}Ilustración 21 -- Diagrama relacional
Bitcoin](media/image25.png){width="6.102083333333334in"
height="3.5748009623797024in"}

### Ethereum

La evolución de la blockchain en complejidad es notable y queda
reflejado en el modelo de datos. Como se ha mencionado ya, esta base de
datos no solo se enriquece con el proceso de ingesta, la parte de tokens
se obtiene mediante un script dedicado que obtiene la información de
fuentes externas. La información de tokens se ha desacoplado para
facilitar la flexibilidad de los mismos y que sea más sencillo de cara a
futuros cambios que pueda haber.

Para agilizar el proceso de ingesta, dada la complejidad de la misma y
el coste, se ha reforzado el proceso de inserción para evitar duplicados
mediante identificadores que son hashes generados por el algoritmo
Keccak-256, lo que permite que desactivando los índices de las tablas de
transacciones, bloques y transacciones de tokens fungibles y NFTs se
logre un rendimiento adecuado para realizar el volcado en base de datos
en tiempos prudentes. Para favorecer la robustez, una vez llegado a la
cabeza de cadena el proceso de ingesta, se reindexarán para revisar los
duplicados o posibles errores si los hubiera.

Al igual que en Bitcoin, se planificado los índices para las columnas
más utilizadas y así agilizar las consultas.

![[]{#_Toc210906563 .anchor}Ilustración 22 -- Diagrama relacional
Ethereum](media/image26.png){alt="A diagram of a diagram AI-generated content may be incorrect."
width="6.102083333333334in" height="3.8267639982502186in"}

### Polygon

Dado que no se va a hacer un proceso de ingesta al uso, como se ha
mencionado, el modelo de datos es muy sencillo, al igual que en Ethereum
se almacena la información obtenida por fuentes externas referente a
tokens fungibles y NFTs, de forma que se pueda hacer un buen seguimiento
de los mismos.

![[]{#_Toc210906564 .anchor}Ilustración 23 -- Diagrama relacional
Polygon](media/image27.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="4.079879702537183in" height="2.5555555555555554in"}

El frontal web no obtendrá datos de Polygon de la base de datos, este
proceso se expondrá más en detalle en el punto correspondiente de la API
del Datalake.

![[]{#_Toc210906565 .anchor}Ilustración 24 -- Captura dashboard Ingesta
desde
Blockchains](media/image28.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.472916666666667in"}

## Gestión Relaciones Flexibles 

Adicionalmente existen otras **fuentes de información *off-chain***
(como pueden ser fuentes OSINT, fuentes de datos externos, etc...), que
también son almacenadas e indexadas dentro de la capa de persistencia de
este prototipo. Estas fuentes, de diversas naturalezas y
características, requieren de una capa de persistencia que, permitiendo
generar relaciones entre estos elementos, aporte un mayor grado de
flexibilidad y adaptabilidad a nuevos escenarios o situaciones que se
puedan presentar.

La capa de procesamiento ETL es la encargada de solicitar e ingerir la
información desde las fuentes externas correspondientes. Estos procesos
transforman los datos procedentes de las distintas fuentes, generando un
modelo consistente bajo el paradigma de las bases de datos de grafo.
^(ESF-0012)^

Este tipo de base de datos nos ofrece por un lado la versatilidad de
generar cualquier tipo de relación entre entidades, y por otro la
capacidad de definir algoritmos y mecanismos para recorrer la base de
datos de manera óptima.

De esta forma, gracias al diseño de arquitectura de la base de datos de
grafos, desde cualquiera de las entidades, podremos obtener los
elementos relacionados, así como la profundidad o el camino necesario
para llegar a ella.

En la siguiente imagen se puede ver la estructura de la metainformación
gestionado dentro de la base de datos Neo4j:

![[]{#_Toc210906566 .anchor}Ilustración 25 -- Diagrama de entidad no
relacional](media/image29.png){width="6.076802274715661in"
height="2.4in"}

Esta sería una explicación de los distintos datos almacenados:

- ***Actor***: Threat Actors, o grupos de ciberdelicuentes, relacionados
  con casos de ransomware en general.

- ***Tool***: Aplicaciones o malwares empleados en los ataques

- ***Event***: Distintas campañas de ransomware identificadas por los
  equipos de inteligencia.

- ***Entity***: Entidad, procedente de los listados OFAC, relacionados
  con casos de ciberdelincuencia.

- ***Exchange***: Información de exchanges

- ***Address***: Dirección de una billetera relacionada con un caso de
  ransomware o el blanqueo de capitales.

- ***Transaction***: Transacciones dentro de la blockchain que tienen
  algún tipo de relación con un caso de ransomware (directa o
  indirectamente)

- ***Country***: Cada uno de los países bajo el radar, o directamente
  atacados en casos de ransomware.

- ***Industry***: Cada una de las industrias bajo el radar o
  directamente atacadas en casos de ransomware.

- ***CVE***: CVE empleado por un actor, evento o aplicación para dentro
  de un ataque de ransomware.

- ***IP***: Correspondiente a información de direcciones IP asociadas
  con las actividades ilícitas identificadas.

- ***Dominio***: Correspondiente a información de dominios web asociados
  con las actividades ilícitas identificadas.

![[]{#_Toc210906567 .anchor}Ilustración 26 -- Captura dashboard Fuentes
OSINT
(I)](media/image30.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.2263888888888888in"}

![[]{#_Toc210906568 .anchor}Ilustración 27 -- Captura dashboard Fuentes
OSINT
(II)](media/image31.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.0076388888888888in"}

### Gestión de Billeteras Sospechosas

Si bien cada tipo de entidad presenta sus propios atributos específicos,
en el caso particular de las Billeteras (Addresses) existe la necesidad
de **marcar el grado de peligrosidad del elemento**. Esta característica
va relacionada con los factores establecidos por el equipo de ciber
seguridad en relación con las actividades fraudulentas de la billetera.
Tiene un doble propósito dentro de esta solución: por un lado se ha
**empleado en los procesos de entrenamiento** de los modelos de
inteligencia artificial; por otro al **tratarse de elementos
inherentemente fraudulentos**, son utilizados para generar alertas en
base a las necesidades de negocio.

La gestión de las carteras sospechosas se realiza a través de dos
propiedades:

**SuspiciousLevel**

Para las billeteras, y otros elementos almacenados en esta base de
datos, se establece un atributo con una valoración numérica de su
**grado de sospecha** o carácter delictivo. Este valor marca lo
**implicada que puede estar esa dirección en una determinada
organización de ciberdelincuentes**, ciberactor o entidad sancionada por
la OFAC. Los valores posibles son: 3, 2, 1 o 0 (valor por defecto si no
está asignado). El valor asignado a una determinada billetera va
establecido por una de esas dos opciones:

- Se aplica el valor 3 en aquellos casos en los que la **billetera ha
  sido identificada por alguna fuente de información como parte en un
  caso de ransomware**. O en aquellos casos en los que la billetera ha
  sido reportada como activo sancionado por la OFAC (independientemente
  que sea por motivos de ransomware, blanqueo de capitales u otro
  motivo)

- Se aplica un valor 2 a aquellas billeteras a las que se hayan movido
  fondos desde una billetera marcada como 3.

  - Estas billeteras forman parte del flujo seguido por el delincuente
    para gestionar o blanquear los fondos adquiridos.

- Se aplica el valor de 2 a aquellas billeteras que en una transferencia
  envíen fondos junto a una billetera marcada como 3.

- Se aplica un valor de 1 a aquellas billeteras a las que se hayan
  movido fondos desde una billetera marcada como 2.

Este valor se establece automática durante el proceso de carga de
información en la base de datos neo4j, o a través de procesos asíncronos
de verificación de los datos disponibles.

**SuspiciousReason**

Si bien el atributo anterior marca la peligrosidad de una determinada
cartera, en ciertos casos es necesario identificar a qué **tipo de
riesgo** nos estamos refiriendo. Siendo el objetivo principal el
proyecto la identificación y categorización de casos de ransomware en
las blockchains bajo estudio, la solución también puede contribuir en el
seguimiento de los flujos de salida tras una transacción, y la
identificación de blanqueo de capitales o colaboración con el
terrorismo. Para cubrir estos escenarios, y otros que pudieran aparecer
en el futuro, se proporciona un nuevo campo *suspiciousReason* donde
poder reflejar esta condición. En una primera revisión se van a
establecer 3 posibles valores. Una cartera, donde el *suspiciousLevel*
sea mayor o igual a dos, tendrá que presentar al menos uno de estos 3
valores (siendo posible que presente más de uno):

- *RANSOM*

- *CYBER*

- *LAUNDRY*

El valor que asociar a este atributo queda establecido por el siguiente
pseudo-algoritmo:

- Una billetera tendrá la marca *CYBER*, si tiene un *suspiciousLevel*
  igual o mayor a 2, y está asociada a algún elemento con la marca de
  *CYBER*.

- Una billetera tendrá la marca de *RANSOM*, si tiene un
  *suspiciousLevel* igual o mayor a 2, y está asociado a algún elemento
  con la marca de *RANSOM*.

- Una billetera tendrá la marca de *LAUNDRY*, si tiene un
  *suspiciousLevel* igual o mayor a 2, y está asociado a algún elemento
  con la marca de *LAUNDRY*.

En el momento de crear un elemento (Actor, Tool, Entity) se le podrá
asociar los valores de *suspiciousReason* que corresponden dependiendo
de la actividad identificada. En ese sentido, para actores y tools, que
proceden de fuente OSINT de ciber inteligencia asociado a casos de
ransomware, quedan marcados directamente a RANSOM, de forma que las
billeteras que cuelgan de ellas también adquieren este valor.

En el caso de entidades procedentes de listados como la OFAC, la
categoría a aplicar depende del tipo de sanción que se le haya aplicado.

Con todo esto, esto sería un diagrama que muestra un ejemplo de la
relación entre las billeteras, así como los valores de suspiciousLevel y
suspiciousReasons que se aplicaría en cada caso

![[]{#_Toc210906569 .anchor}Ilustración 28 -- Captura Explorador: Nivel
de riesgo de
carteras](media/image32.png){alt="A diagram of a network AI-generated content may be incorrect."
width="6.102083333333334in" height="2.407638888888889in"}

Esta información de *suspicious* es **empleada posteriormente durante
los procesos de entrenamiento en el módulo de inteligencia artificial**.
Este valor está relacionado con el output a predecir por el modelo a la
hora de categorizar una cartera, o una determinada actividad como
potencialmente ilícita o no.

![[]{#_Toc210906570 .anchor}Ilustración 29 -- Captura Dashboard:
Contadores de clasificación de carteras en el
datalake](media/image33.png){alt="A screenshot of a computer screen AI-generated content may be incorrect."
width="6.102083333333334in" height="1.882638888888889in"}

## API de Acceso

Si bien la carga de información se realiza a través de unos pipelines
que transforman para luego poder persistir la información dentro del
datalake. El **acceso para consumir esta información se realiza a través
de una API REST centralizada** ^(ESF-0036)^. Esta API y sus
funcionalidades disponibles, responde a las necesidades particulares del
proyecto, ofreciendo estructuras de datos optimizadas para los casos de
uso definidos. La API expone **respuestas normalizadas y estructuradas
que permiten consumir la información de forma analítica**, tanto desde
los módulos de Inteligencia Artificial y el gestor de eventos, como
desde el frontal web

![[]{#_Toc210906571 .anchor}Ilustración 30 -- Consumidores API del
Datalake](media/image34.png){width="3.25in"
height="2.294520997375328in"}

Pasemos aquí a abstraer sus conceptos principales:

- **Acceso a los datos de las distintas blockchains.** Permitiendo
  acceder a la información por:

  - Billetera. Información de una billetera, así como su estado global
    de acuerdo con el avance, relaciones con otras billeteras, etc.

  - Transacción: Información de una transacción, así como las entradas y
    salidas, y relaciones de estas.

  - Bloque: Información de los metadatos asociados a un bloque.

- **Información Offchain.** Permitiendo lanzar queries avanzadas sobre
  la base de datos neo4j en relación con:

  - Billetera: Estado de seguridad, sabiendo si la misma ha estado
    involucrada en algún caso conocido de ransomware o de otras
    actividades ilícitas

  - Información de Transacciones, que permiten saber su relación en
    casos de mixers conocidos.

  - Información sobre otros nodos. Como por ejemplo cyberactores,
    campañas de ransomware, países involucrados en un ataque, o CVEs
    empleados.

Cabe destacar que el acceso y consumo a esta API está debidamente
monitorizado y seguro. Todas las **peticiones son debidamente
registradas y monitorizadas**, con el objetivo de identificar riesgos de
manera prematura.

![[]{#_Toc210906572 .anchor}Ilustración 31 -- Captura
API](media/image35.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.9430555555555555in"}

**Información de Blockchains - Polygon**

Es importante destacar el proceso de obtención de datos mediante la API
en los casos de Bitcoin, Ethereum y Polygon, ya que cada uno presenta
particularidades técnicas y operativas que condicionan la arquitectura
general de la solución.

En los casos de Bitcoin y Ethereum, el proceso de ingesta ha consistido
en volcar la totalidad de los datos de sus respectivas blockchains en
una base de datos interna, que actúa como fuente principal de
información. A partir de esta base, la API desarrollada en el proyecto
permite recuperar los datos necesarios para los distintos casos de uso
de forma eficiente y controlada.

El caso de Polygon, sin embargo, presenta un escenario sustancialmente
distinto. Tal como se describe en la sección dedicada a la ingesta, la
volumetría de transacciones en Polygon (3.2.2 Flujos de datos: Ingesta)
es considerablemente superior a la de Bitcoin y Ethereum, lo que supone
retos de infraestructura significativos en términos de almacenamiento,
procesamiento y mantenimiento.

A esta complejidad técnica se suma que el coste de desplegar y mantener
un nodo completo de Polygon resulta notablemente más elevado que el
asociado a nodos de Bitcoin o Ethereum. Este factor económico cobra
especial relevancia en el contexto del proyecto, donde la eficiencia
operativa y la optimización de recursos son criterios fundamentales para
garantizar la sostenibilidad y escalabilidad de la solución.

Si bien Ethereum y Polygon comparten la misma base tecnológica, al estar
ambos basados en la Ethereum Virtual Machine (EVM), las diferencias en
volumen de datos y costes de infraestructura hacen inviable aplicar la
misma estrategia de ingesta. Por ello, en el caso de Polygon se ha
optado por un enfoque alternativo, en el que no se realiza un volcado
completo de la blockchain, sino que los datos se recuperan bajo demanda
mediante una API externa de Etherscan, permitiendo mantener la
eficiencia y reducir los costes operativos.

De esta forma, aunque el proceso de obtención de datos difiere, la
compatibilidad entre Polygon y Ethereum a nivel EVM permite que, en
etapas posteriores del proyecto, los modelos de inteligencia artificial
desarrollados para Ethereum puedan aplicarse también sobre Polygon,
aprovechando las similitudes estructurales entre ambas redes y
maximizando la reutilización de los componentes ya implementados.

# GESTION DE LA INTELIGENCIA ARTIFICIAL 

## Introducción

El aspecto más singular y distintivo de este proyecto radica en el uso
de técnicas de inteligencia artificial para la identificación de
actividades vinculadas al pago y posterior blanqueo de transacciones
asociadas al ransomware.

Asimismo, resulta relevante destacar que, aunque es posible disponer de
datasets procedentes de otros experimentos y pruebas de concepto
desarrolladas a nivel experimental, el verdadero valor diferencial del
presente trabajo reside en los datos empleados para el entrenamiento y
la generación de los modelos. Estos datos incorporan una base histórica
de campañas y fuentes OSINT recopiladas por los equipos profesionales de
ciberseguridad de Deloitte durante los últimos años, conformando un
dataset de alto valor.

En esta sección se abordarán ambos aspectos en detalle. Por un lado, se
analizarán los mecanismos de integración entre el dataset y el módulo de
inteligencia artificial; por otro, se presentarán los experimentos y
pruebas realizados, junto con los resultados obtenidos, las capacidades
de los modelos generados y las métricas empleadas para su evaluación.

Referencias adicionales a esta sección son los entregables *ENT-0006
Estudio comparativo de técnicas de inteligencia artificial* y ENT-0007
*Estudio de técnicas para la monitorización de la inteligencia
artificial*. Estos dos estudios complementan el discurso que aquí se
proporciona, aportando claridad sobre el análisis efectuado del estado
del arte por un lado, y de los temas de cumplimiento regulatorio en
relación a las directivas de la Unión Europea.

## Entrada y transformación de datos desde el Datalake

El módulo de IA dota al sistema de capacidades analíticas avanzadas para
el reconocimiento de patrones complejos y la predicción automática de
riesgos sobre grandes volúmenes de datos transaccionales. A través de un
pipeline de datos robusto, este módulo conecta el Data Lake
(almacenamiento masivo de datos blockchain y off-chain) con el motor de
modelos de machine learning. Así, posibilita tanto el entrenamiento
iterativo de modelos a partir de datos históricos y etiquetados, como la
ejecución de inferencias en tiempo real para detectar y anticipar nuevas
amenazas. Su diseño asegura la trazabilidad, calidad y estructuración de
los datos en todas las etapas, permitiendo su integración transparente
en procesos de análisis forense, auditoría y toma de decisiones
automatizadas en el ámbito de la ciberinteligencia financiera.

Por otro lado, el módulo de Mixers complementa la estrategia de análisis
desde un enfoque determinista y forense, especializado en la detección
de transacciones asociadas a protocolos y servicios de mezcla (mixing)
en la red Bitcoin. Este módulo implementa un motor de reglas heurísticas
capaz de identificar patrones característicos de CoinJoin, servicios
centralizados, peel chains, fan-in/fan-out y otras técnicas de
anonimización, sin depender de modelos de machine learning. Gracias a su
lógica explícita y configurable, el módulo de Mixers permite una
detección inmediata y explicable de posibles operaciones de lavado de
dinero o encubrimiento de fondos, aportando evidencias claras y
reproducibles para la investigación y el cumplimiento regulatorio.
Además, su diseño flexible permite la incorporación dinámica de nuevas
reglas, umbrales y fuentes externas de inteligencia (listas negras,
bases de direcciones, comisiones, etc.), adaptándose a la rápida
evolución del ecosistema blockchain.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image36.png){width="5.1123950131233595in"
height="2.3660640857392825in"}

***Ilustración 7 -- Pipeline de transmisión a módulo de IA***

Integración del Módulo ETL+AI

El sistema TRAC integra un pipeline ETL avanzado para la extracción,
procesamiento y análisis de transacciones anómalas en Bitcoin, diseñado
para operar tanto en entornos de desarrollo local como en despliegues
productivos completamente dockerizados. El pipeline, junto con el módulo
de IA para la detección de anomalías, se articula como una única unidad
orquestable, pensada para una integración sencilla en entornos de
análisis, permitiendo su operación tanto por línea de comandos como
mediante servicios automatizados.

El sistema se distribuye como una solución dockerizada basada en un
enfoque monolítico modular, donde todos los componentes (ETL, modelos de
IA, gestión de datos y logs) coexisten en un mismo contenedor o servicio
Docker. Esto simplifica la gestión, el despliegue y la integración con
otros módulos de la arquitectura general del sistema TRAC.

Componentes Principales:

- ETL Pipeline: Incluye extracción, limpieza, transformación y carga de
  datos transaccionales.

- Módulo de AI: Aplicación de modelos entrenados para la detección de
  anomalías.

- Gestión de Logs y persistencia: Volúmenes Docker para logs y datos,
  fácilmente montables en el host.

- Interfaz de entrada (EntryPoint): Script entrypoint.sh y comandos
  accesibles por CLI/Docker.

I.  **Construcción y Configuración**

El módulo dispone de un Dockerfile específico (/BTC/Dockerfile) que
define el entorno de ejecución, la instalación de dependencias, y la
copia del código fuente, modelos y scripts auxiliares.

Aunque este proceso es habitualmente es realizado de forma automatizada
y gestionada por el docker-compose, la imagen puede construirse de la
siguiente forma (desde el directorio raíz de BTC)

  ----------------------------------------------------------------------
               docker build -t trac_etl_ai -f Dockerfile .

  ----------------------------------------------------------------------

Para facilitar la configuración inicial y asegurar buenas prácticas de
seguridad, el repositorio incluye un archivo "**.env.example**" como
plantilla de referencia para las variables de entorno necesarias. Este
archivo contiene todos los nombres de variables requeridos, pero no debe
contener valores sensibles ni credenciales reales.

Antes de iniciar el despliegue, es imprescindible copiar este archivo y
renombrarlo como ".env", completando los valores correspondientes según
el entorno (desarrollo, pruebas o producción). Recuerda que el archivo
"**.env**" debe mantenerse fuera del control de versiones (por ejemplo,
protegido por ".gitignore") para evitar la exposición de información
sensible.

Esta práctica asegura que cada entorno disponga de su propia
configuración segura, y permite una gestión sencilla de las variables
necesarias para el funcionamiento del sistema ETL+IA.

  ----------------------------------------------------------------------
                           cp .env.example .env

  ----------------------------------------------------------------------

II. **Volúmenes y Persistencia**

El módulo ETL+IA utiliza volúmenes para persistencia de datos, modelos y
logs, facilitando el acceso y la auditoría posterior desde el host.

Las rutas montadas son:

  -----------------------------------------------------------------------------------
          **Ruta Host**               **Ruta                **Explicación**
                                   Contenedor**    
  ----------------------------- ------------------ ----------------------------------
   **deploy/host-data/data/**     /app/BTC/data/   Datos operativos y resultados del
                                                    pipeline (procesados y outputs).

   **deploy/host-data/logs/**     /app/BTC/logs/   Logs de ejecución y auditoría del
                                                                sistema.

   **deploy/host-config/.env**      /app/.env            Variables de entorno y
                                                        configuración sensible.

   **deploy/host-config/ssh/**      /app/.ssh/      Claves SSH para acceso seguro y
                                                           extracción remota.
  -----------------------------------------------------------------------------------

  : []{#_Toc210906530 .anchor}Tabla 1 - Volumenes Módulo ETL+AI

III. **Lanzamiento y uso**

El módulo ETL+IA de TRAC se controla completamente a través de un script
de entrada (*entrypoint.sh*), que se encuentra en la raíz del entorno
dentro del contenedor (/app/entrypoint.sh). Este entrypoint es el único
punto de acceso recomendado para operar el sistema dentro del contenedor
Docker, y está diseñado para garantizar que todos los requisitos de
entorno, carpetas y dependencias estén inicializados antes de ejecutar
cualquier operación sobre la blockchain.

Cuando el contenedor arranca, el entrypoint se ejecuta automáticamente,
mostrando un banner informativo y dejando el sistema en un estado
\"listo para recibir comandos\", pero sin ejecutar ninguna tarea pesada
hasta que lo solicite el usuario o un sistema externo.

El comando de ejecución estándar para lanzar el pipeline completo es:

  ----------------------------------------------------------------------
  docker compose exec btc-etl bash /app/entrypoint.sh start -s 750000 -n
  5 \--download yes \--process yes \--ai yes \--model ortbit_model.pkl

  ----------------------------------------------------------------------

Este comando realiza lo siguiente:

> Ejecuta el pipeline completo: desde la extracción de datos del bloque
> inicial especificado (**-s 750000**), pasando por el procesamiento de
> órbitas y grafos, hasta la aplicación del modelo de IA sobre los
> resultados, en un total de 5 lotes consecutivos (**-n 5**).
>
> El parámetro **\--download yes** asegura que se descargan y preparan
> los datos; **\--process yes** activa el procesamiento y extracción de
> órbitas; **\--ai yes** habilita la inferencia con el modelo IA
> especificado.
>
> \-**-model ortbit_model.pkl** permite seleccionar el modelo de machine
> learning concreto a emplear para las predicciones (puede usarse
> cualquier modelo válido que esté incluido en /app/BTC/models/).

Todas estas opciones pueden combinarse a conveniencia, permitiendo
lanzar solo una fase (por ejemplo, solo la IA sobre datos ya descargados
y procesados, o solo la descarga de datos).

A la hora de introducir el comando, se puede introducir diferentes
opciones en forma de argumentos:

- -s, \--start-block Define el número de bloque de Bitcoin desde el cual
  iniciar el procesamiento. Es fundamental para determinar el rango de
  datos a analizar y para permitir reinicios o ejecuciones
  incrementales.

- -n, \--num-batches Número de \"batches\" o lotes de bloques a
  procesar. Esto define la cantidad de datos que se manejarán en una
  ejecución, permitiendo escalar entre ejecuciones rápidas de prueba y
  procesamientos masivos.

- \--download Activa o desactiva la fase de adquisición de datos
  remotos. Si se pone en no, se asume que los datos ya están preparados
  localmente.

- \--process Habilita el procesamiento de datos brutos para el cálculo
  de órbitas y generación de las estructuras de grafo sobre las que se
  aplicarán las heurísticas y el análisis.

- \--ai Si está en yes, ejecuta la predicción utilizando el modelo de IA
  sobre los datos previamente procesados.

- \--model Indica el archivo de modelo de machine learning
  (habitualmente en formato .pkl) que será cargado y ejecutado en la
  fase de predicción. Puede seleccionarse el modelo óptimo para cada
  caso de uso.

Además, el entrypoint dispone de otras utilidades, como la siguiente, la
cual permite ver todas las opciones y ayudas disponibles en el sistema,
permitiendo ver una lista completa de comandos, argumentos obligatorios,
opcionales, ejemplos prácticos y un listado completo de todos los
modelos disponibles en el contenedor.

  ----------------------------------------------------------------------
  docker compose exec btc-etl bash /app/entrypoint.sh help

  ----------------------------------------------------------------------

El diseño del módulo ETL+IA es flexible y adaptable a diferentes
escenarios operativos:

- **Modo Batch**

Es el modo más común para pruebas, re-procesamiento histórico, o cuando
se requiere analizar rangos específicos de la blockchain. Cada ejecución
procesa un número limitado de bloques/lotes, tras lo cual el proceso
termina. Es ideal para cargas controladas o procesamiento en ventanas de
tiempo específicas (por ejemplo, por la noche o en ventanas de bajo uso
de recursos).

+-------------------------------------------------------------------+
| > docker compose exec btc-etl bash /app/entrypoint.sh start -s    |
| > 760000 -n 2 \--download yes \--process yes \--ai yes            |
+-------------------------------------------------------------------+

> **Modo Continuo (Automatizado/Scheduler):**

En producción o integración con pipelines externos, suele ser necesario
procesar nuevos bloques conforme aparecen en la red, de manera
automatizada y sin intervención manual.

Esto se consigue programando el comando de lanzamiento para ejecutarse
de forma periódica (cada 10 minutos, cada hora, etc.), por ejemplo,
mediante un cron, un orquestador externo (Airflow, Jenkins), o cualquier
sistema de scheduling.

Ejemplo de entrada en crontab para lanzar el proceso cada 10 minutos:

+-------------------------------------------------------------------+
| > \*/10 \* \* \* \* docker compose exec btc-etl bash              |
| > /app/entrypoint.sh start -s \$(date \'+%s\' \|                  |
| > ./block_height_from_timestamp.sh) -n 1 \--download yes          |
| > \--process yes \--ai yes                                        |
+-------------------------------------------------------------------+

El sistema está pensado para ser **idempotente** y capaz de continuar
desde el último bloque procesado, evitando reprocesar datos antiguos.

IV. **Buenas Prácticas Operativas**

Para garantizar la fiabilidad y el rendimiento óptimo del módulo ETL+IA,
es fundamental mantener una supervisión constante de los logs generados
durante cada ejecución. Estos registros, almacenados en la ruta
/app/BTC/logs/, permiten identificar de manera temprana posibles
errores, bloqueos inesperados o cuellos de botella en el procesamiento.
El análisis regular de los logs facilita la detección proactiva de
incidencias y contribuye a la mejora continua del pipeline.

La eficiencia del procesamiento depende en gran medida de una
configuración adecuada de los parámetros de lote y concurrencia. Es
recomendable ajustar el tamaño de los batches y el número de workers
(-b, -w) en función de la capacidad de la máquina o entorno donde se
despliegue el sistema. Esta optimización no solo mejora los tiempos de
ejecución, sino que también previene la sobrecarga de recursos y
minimiza el riesgo de interrupciones durante la operación.

Antes de ejecutar procesos masivos o de larga duración, resulta
imprescindible verificar la disponibilidad y los permisos correctos de
las claves SSH utilizadas para la extracción remota, así como las
credenciales de acceso a bases de datos y el espacio disponible en
disco. Estos chequeos previos son esenciales para evitar fallos en la
extracción o almacenamiento de datos, y ayudan a mantener la integridad
del flujo de trabajo.

Durante las fases de desarrollo e integración, se aconseja realizar
pruebas utilizando la opción ***\--ai no***, lo que permite depurar y
validar el pipeline de adquisición y procesamiento de datos sin ejecutar
la inferencia de modelos de IA. De este modo, se agiliza el ciclo de
pruebas y se facilita la detección de posibles problemas en las primeras
etapas. Posteriormente, una vez validado el procesamiento, se puede
lanzar la fase de IA sobre los datos ya generados para obtener los
resultados finales.

Por último, en escenarios de ejecución continua o automatizada, es
altamente recomendable implementar un sistema de checkpoint que registre
el último bloque procesado. Esta práctica permite reanudar el pipeline
correctamente en caso de caídas, reinicios inesperados o mantenimientos,
evitando la duplicidad de procesos y asegurando la consistencia del
análisis a lo largo del tiempo.

Integración del Módulo Mixers

El módulo Mixers de TRAC es un sistema avanzado de detección basado en
reglas, enfocado en identificar y analizar actividades de mixing en
transacciones Bitcoin. Opera de manera completamente autónoma,
implementando heurísticas y detectores sofisticados para marcar
transacciones potencialmente sospechosas asociadas a servicios de mixing
(CoinJoin, mixers centralizados, patrones de anonimización, etc.). El
módulo está diseñado para ser flexible y eficiente tanto en entornos de
desarrollo como en producción, y puede integrarse de forma independiente
o junto a otros módulos del ecosistema TRAC

El sistema sigue una arquitectura por capas y un pipeline de dos etapas:

> **Data Pipeline**:
>
> Se encarga de la extracción y preprocesamiento de los datos,
> obteniendo transacciones y enriqueciendo la información con
> inteligencia (direcciones de mixers, denominaciones estándar, patrones
> de comisiones, etc.), usando conexiones tanto a PostgreSQL como a
> Neo4j.
>
> **Detection Pipeline**:
>
> Orquesta el análisis transaccional mediante un motor de reglas y
> detectores, evaluando patrones estructurales, temporales, de fees y de
> entidades. Permite la agregación de resultados, scoring avanzado y la
> clasificación de transacciones por riesgo.

El ciclo de ejecución es gestionado por el orquestador principal (App) y
expuesto a través de una interfaz de línea de comandos (main.py). Se
soportan múltiples modos de operación: análisis por rango de bloques o
por lista de transacciones específicas, permitiendo análisis masivo y
casos de investigación puntual.

I.  **Construcción y Configuración**

El despliegue del módulo Mixers se realiza mediante un Dockerfile
propio, ubicado en el directorio correspondiente (habitualmente
*/BTC/src/mixers/Dockerfile*). Este se puede crear mediante una
construcción manual del contenedor:

  ----------------------------------------------------------------------
               docker build -t trac_mixers -f Dockerfile .

  ----------------------------------------------------------------------

El módulo utiliza un archivo .env para definir todos los parámetros de
configuración y credenciales necesarias. Para facilitar la puesta en
marcha, el repositorio incluye una plantilla .env.example, que debe
copiarse y completarse con los valores adecuados.

  ----------------------------------------------------------------------
                           p .env.example .env

  ----------------------------------------------------------------------

Este archivo contiene una serie de variables comunes, las cuales se
montan como volumen externo al contenedor, permitiendo su gestión y
actualización sin necesidad de reconstruir la imagen Docker:

- Parámetros de base de datos (host, puerto, usuario, contraseña, nombre
  de la base de datos)

- Parámetros de logging y entorno (LOGGING_LEVEL, PROJECT_ENV, etc.)

- (Opcional) Parámetros de caché, rutas de directorios temporales, etc.

La configuración del módulo Mixers se basa en archivos YAML ubicados en
el directorio rule_config/, donde se definen de forma estructurada todas
las reglas heurísticas (rules.yaml), los detectores y agrupaciones de
reglas (detectors.yaml), así como los parámetros globales del motor
(engine.yaml). Este enfoque jerárquico y declarativo permite modificar,
añadir o deshabilitar reglas y detectores de manera sencilla y sin
necesidad de reiniciar ni recompilar el sistema, facilitando así la
adaptación continua a nuevas amenazas, la actualización de criterios de
detección y la extensión modular del motor según evolucione el contexto
operativo o regulatorio.

II. **Volúmenes y Persistencia**

El módulo ETL+IA utiliza volúmenes para persistencia de datos, modelos y
logs, facilitando el acceso y la auditoría posterior desde el host.

Las rutas típicas montadas son:

  --------------------------------------------------------------------------------------------
            **Ruta Host**              **Ruta Contenedor**            **Explicación**
  --------------------------------- ------------------------- --------------------------------
     **deploy/host-data/data/**         /app/temp/blocks         Almacena datos de bloques
                                                                  extraídos y procesados.

   **deploy/host-data/detection/**     /app/temp/detection    Resultados y reportes generados
                                                                 por el motor de detección.

     **deploy/host-data/logs/**      /app/temp/metadata/logs   Logs de ejecución y auditoría
                                                                    del sistema Mixers.

     **deploy/host-config/.env**            /app/.env              Variables de entorno y
                                                                  configuración sensible.

     **src/mixers/rule_config/**        /app/rule_config         Configuración de reglas y
                                                                     detectores (YAML).
  --------------------------------------------------------------------------------------------

  : []{#_Toc210906531 .anchor}Tabla 2 - Volúmenes de contenedor mixer

III. **Lanzamiento y uso**

El acceso principal se realiza mediante el script main.py o a través de
la interfaz CLI expuesta por el módulo.

+----------------------------------------------------------------------+
| docker compose exec mixers python -m src.main \\                     |
|                                                                      |
| \--execution-mode block \\                                           |
|                                                                      |
| \--block-range 800000 800010 \\                                      |
|                                                                      |
| \--execution-speed fast \\                                           |
|                                                                      |
| \--save-data                                                         |
+----------------------------------------------------------------------+

- Los comandos que permite este script son:\
  \--execution-mode block\|tx Determina el modo de operación del motor.

  - En modo block, el sistema analizará todas las transacciones
    incluidas en un rango de bloques de la blockchain, ideal para
    análisis masivos o procesamiento histórico.

  - En modo tx, se procesan únicamente las transacciones cuyos TXIDs se
    especifiquen explícitamente, permitiendo análisis dirigidos y
    forenses sobre casos concretos.

- \--block-range A B Define el rango de bloques a analizar (incluyendo
  el bloque inicial A y excluyendo el bloque final B).

Es obligatorio cuando se selecciona el modo block, y permite ejecutar el
motor sobre cualquier ventana temporal o de interés dentro de la
blockchain.

- \--transactions \... Permite introducir una o varias TXIDs
  (identificadores de transacción) específicas para análisis detallado.

Es obligatorio cuando se elige el modo tx, facilitando la investigación
individualizada o el re-análisis de transacciones previamente
identificadas como sospechosas.

- \--execution-speed fast\|slow Controla el nivel de profundidad y los
  recursos empleados durante la detección.

  - El modo fast prioriza la velocidad y la eficiencia, aplicando atajos
    y estrategias de corte temprano.

  - El modo slow realiza un análisis más exhaustivo, aplicando todas las
    heurísticas y detectores disponibles, ideal para auditoría o
    validación de resultados.

- \--save-data Si se activa, habilita la persistencia automática de los
  datos procesados y los resultados de detección en los directorios
  configurados (por ejemplo, volúmenes Docker).

Es recomendable mantenerlo activo en entornos de producción o auditoría
para garantizar la trazabilidad y facilitar el acceso posterior a los
resultados.

- \--data-path,\--detection-path Permiten personalizar las rutas de
  salida donde se almacenarán tanto los datos procesados (transacciones
  extraídas y preprocesadas) como los resultados de la detección
  (alertas, evidencias, informes).

Esto aporta flexibilidad para integrarse con otros sistemas, separar
entornos o adaptar la persistencia a la infraestructura del usuario.

IV. **Buenas Prácticas Operativas**

El diseño del módulo Mixers prioriza la extensibilidad para facilitar la
evolución continua frente a nuevas técnicas de anonimización o patrones
de mixing emergentes. La arquitectura permite incorporar fácilmente
nuevas reglas heurísticas o detectores: basta con implementar una clase
heredando de BaseRule o BaseDetector, registrar la nueva lógica en el
sistema de factorías, y definir su configuración y parámetros en los
archivos YAML correspondientes. Gracias a este enfoque plug-and-play, el
motor puede ser adaptado rápidamente a nuevas necesidades analíticas o
regulatorias sin modificar el núcleo del sistema ni interrumpir
operaciones existentes.

En cuanto a gestión de errores y resiliencia, el pipeline está
construido para soportar fallos parciales en la extracción,
procesamiento o evaluación de datos. El análisis se realiza de manera
aislada por bloques o transacciones individuales, de modo que si ocurre
un error puntual, este no interrumpe la ejecución global, y se documenta
para su posterior revisión. Esta robustez es especialmente valiosa en
análisis históricos de grandes volúmenes de datos o en entornos donde la
calidad de la fuente puede ser variable.

La monitorización y auditoría son aspectos integrados en el flujo de
trabajo mediante el sistema Monitor, que centraliza la recolección de
logs, métricas de rendimiento, errores y eventos clave. Esto no solo
facilita la detección temprana de incidencias y la trazabilidad de todo
el proceso, sino que también permite la generación de informes de
auditoría y la integración con sistemas de alerta y supervisión
externos, contribuyendo a la transparencia y la fiabilidad del sistema.

Por último, la seguridad y el control de la configuración son
fundamentales. Todas las variables sensibles y credenciales se gestionan
mediante volúmenes externos y archivos .env, nunca embebidos dentro de
las imágenes Docker, minimizando el riesgo de exposición accidental.
Este enfoque facilita la rotación periódica de claves, la segregación de
entornos (desarrollo, test, producción) y el cumplimiento de buenas
prácticas de seguridad en despliegues cloud o on-premise.

En conjunto, estos principios aseguran que el módulo Mixers no solo sea
potente y configurable, sino también mantenible, seguro y resiliente,
preparado para operar en escenarios exigentes y en constante cambio
dentro del análisis blockchain.

#####  

Lanzamiento Orquestado con Docker Compose

El despliegue conjunto de los módulos principales del sistema TRAC,
incluyendo ETL+IA y Mixers, se realiza de manera sencilla y eficiente
mediante Docker Compose. Esta herramienta permite definir y lanzar todos
los servicios necesarios a través de un único archivo
*docker-compose.yml*, gestionando la construcción de imágenes, la
configuración de entornos, el montaje de volúmenes y la orquestación de
redes internas.\
Cada módulo se define como un servicio independiente, especificando su
propio contexto de build, configuración de variables de entorno,
volúmenes de datos y healthchecks. Ambos servicios pueden compartir
variables y red, pero mantienen su lógica y ciclo de vida de forma
desacoplada, facilitando el mantenimiento y la escalabilidad del
sistema.![A screenshot of a computer program AI-generated content may be
incorrect.](media/image37.png){width="4.934922353455818in"
height="6.864212598425197in"}

***Ilustración 8 -- Archivo de despliegue docker-compose***

I.  **Consideraciones de Despliegue**

La arquitectura basada en Docker Compose asegura que todos los datos
críticos, logs y resultados generados por los módulos ETL+IA y Mixers se
almacenen en directorios persistentes del host. De esta manera, se
garantiza que la información esencial se conserva incluso si los
contenedores se detienen, reinician o eliminan, facilitando la
trazabilidad y la recuperación de información para auditoría o análisis
retrospectivo.

En cuanto a la comunicación entre servicios, ambos módulos comparten la
red interna btc-network, lo que permite la colaboración directa, la
transferencia eficiente de datos y la integración sencilla con otros
componentes del ecosistema TRAC. Esta red interna aísla los servicios
del exterior y proporciona un canal de comunicación seguro y controlado.

La gestión centralizada de la configuración se realiza a través de un
único archivo .env y los volúmenes compartidos de configuración. Este
enfoque simplifica la adaptación a distintos entornos (desarrollo,
pruebas, producción) y minimiza errores de configuración, permitiendo
cambios rápidos y seguros en las variables de entorno o parámetros
sensibles sin necesidad de reconstruir las imágenes.

Por último, la directiva *restart: unless-stopped* y el mecanismo de
healthcheck automático refuerzan la resiliencia del sistema en
producción. Esto permite que los servicios se reinicien automáticamente
ante caídas inesperadas y que su estado de salud sea monitorizado en
todo momento, contribuyendo a la alta disponibilidad y a la estabilidad
operativa del entorno.

II. **Ciclo de Vida Recomendado**

Para garantizar una operación eficiente y segura del sistema, se
recomienda seguir un ciclo de vida bien definido en la gestión de los
servicios Docker Compose. El primer paso consiste en configurar
adecuadamente los archivos .env y verificar la existencia de todos los
directorios necesarios para datos y logs en el host. Esta preparación
inicial es clave para evitar problemas de permisos o pérdida de
información.

Una vez preparado el entorno, los servicios se pueden lanzar de manera
orquestada utilizando el comando *docker compose up -d*, que iniciará
todos los módulos definidos en segundo plano. Es fundamental, tras el
despliegue, revisar el estado de los contenedores y consultar los logs
para asegurar que la inicialización ha sido correcta y que no existen
errores o advertencias relevantes.

A partir de ahí, se puede acceder a los servicios de ETL+IA o Mixers
según sea necesario y ejecutar las tareas o comandos específicos
documentados en sus respectivas secciones. Finalmente, se recomienda
supervisar de forma continua los logs y los outputs generados en los
volúmenes del host, tanto para asegurar la trazabilidad del análisis
como para detectar y resolver cualquier incidencia operativa de manera
temprana.

## Proceso generación modelos

En esta sección se presenta la evolución de las técnicas de inteligencia
artificial empleadas en el proyecto. El enfoque para Bitcoin se basa en
el aprendizaje supervisado, utilizando dos tipos principales de
características (features):

> **Órbitas (nivel grafo)**: Representan estructuras relacionales en el
> grafo de transacciones de Bitcoin, capturando patrones de conexión y
> flujo de fondos entre direcciones.
>
> **Variables temporales (estadísticas de direcciones)**: Incluyen
> métricas estadísticas derivadas del comportamiento temporal de las
> direcciones.

El proceso evolutivo se inició con exploraciones básicas y avanzó hacia
métodos más sofisticados, priorizando la precisión, la robustez y la
prevención de sesgos o fugas de datos (data leak). A continuación, se
detalla cada etapa de manera cronológica, destacando las decisiones
tomadas y las mejoras implementadas.

### Bitcoin Etapa Inicial: Exploración de Algoritmos Básicos

Se comenzó con una fase de experimentación preliminar para evaluar una
variedad de algoritmos de aprendizaje supervisado. Se seleccionaron
modelos comúnmente utilizados en tareas de clasificación, con el fin de
identificar aquellos con potencial para el problema específico de
detección de ransomware en Bitcoin.

- **Algoritmos probados**: Se evaluaron AdaBoost, Decision Tree, Random
  Forest (RF), XGBoost (XGB), LightGBM (LGBM) y Support Vector Machine
  (SVM).

- **Configuraciones iniciales**: Las pruebas se realizaron con
  configuraciones poco elaboradas, utilizando hiperparámetros por
  defecto. Esto permitió una evaluación rápida y sin ajustes finos,
  enfocándose en el rendimiento base de cada algoritmo.

- **Resultados**: Esta etapa reveló que RF, XGBoost y LGBM destacaban
  por su rendimiento superior en métricas como precisión, recall y
  F1-score, especialmente en el manejo de datos desbalanceados. Los
  otros modelos, como SVM y Decision Tree, mostraron limitaciones en
  escalabilidad o generalización, por lo que se descartaron para fases
  posteriores.

Esta fase inicial sirvió como base para entender las fortalezas de los
modelos ensemble (como RF, XGBoost y LGBM), que manejan bien la
complejidad de las features basadas en grafos y temporales.

### Bitcoin Etapa de Manejo del Desbalanceo de Clases: Técnicas de Sampling

Una de los desafíos iniciales identificados en el proyecto fue el severo
desbalance de clases en el conjunto de datos, donde las direcciones
\"blancas\" (no sospechosas) superaban ampliamente en número a las
direcciones sospechosas de participación en ransomware. Este desbalance
podía sesgar el entrenamiento de los modelos, priorizando la clase
mayoritaria y reduciendo la capacidad de detección de casos positivos
(sospechosos). Para abordar este problema, se exploraron técnicas de
sampling, tanto undersampling como oversampling, con el objetivo de
equilibrar las clases y mejorar el rendimiento general.

> **Técnicas probadas**: Se experimentó con undersampling (reducción de
> la clase mayoritaria) y oversampling (aumento de la clase minoritaria)
> para ajustar las proporciones de clases. Se evaluaron distintas ratios
> de desbalance, incluyendo 100:1, 50:1, 10:1, 5:1, 2:1, entre otras,
> aplicando estas técnicas de manera iterativa en los conjuntos de
> entrenamiento.
>
> **Métodos de oversampling específicos**: Entre las técnicas de
> oversampling, se probaron SMOTE (Synthetic Minority Over-sampling
> Technique), que genera muestras sintéticas interpolando entre
> instancias existentes de la clase minoritaria, y ADASYN (Adaptive
> Synthetic Sampling), que adapta la generación de muestras sintéticas
> enfocándose en áreas difíciles de clasificar.
>
> **Decisión clave**: Tras comparar los resultados, se optó por ADASYN
> debido a su superioridad en la generación de muestras más
> representativas y efectivas para el contexto de features complejas
> como órbitas y variables temporales. ADASYN demostró una mejor
> adaptación al desbalanceo extremo, evitando el sobreajuste común en
> SMOTE.
>
> **Resultados observados**: El rebalanceo de clases mediante estas
> técnicas mejoró sustancialmente el rendimiento de los modelos en
> métricas clave de evaluación, como el F1-score (que equilibra
> precisión y recall) y el ROC AUC (que mide la capacidad de
> discriminación entre clases). Esto se tradujo en una mayor
> sensibilidad para detectar direcciones sospechosas sin comprometer
> excesivamente la especificidad.

Esta etapa fue crucial para establecer una base equilibrada en los
datos, preparando el terreno para las fases subsiguientes de selección y
optimización de modelos.

### Bitcoin Etapa de Optimización: Tuning de Hiperparámetros con Optuna

Una vez identificados los modelos más prometedores (RF, XGBoost y LGBM),
se procedió a una optimización más rigurosa de sus hiperparámetros para
maximizar el rendimiento.

- **Herramienta utilizada**: Se empleó Optuna, una biblioteca de
  optimización bayesiana, para realizar un tuning eficiente. Optuna
  automatiza la búsqueda de hiperparámetros óptimos mediante pruebas
  iterativas, reduciendo el tiempo computacional en comparación con
  métodos de grid search.

- **Proceso**: Cada modelo se entrenó múltiples veces con variaciones en
  parámetros clave, como profundidad de árboles, tasa de aprendizaje,
  número de estimadores y regularización. Se utilizaron métricas de
  validación cruzada para guiar la optimización.

- **Resultados**: Esta etapa mejoró significativamente el rendimiento de
  los tres modelos, confirmando su viabilidad. Sin embargo, se observó
  que LGBM ofrecía una ventaja en términos de velocidad de entrenamiento
  y flexibilidad, lo que influyó en decisiones posteriores.

El uso de Optuna marcó un avance hacia enfoques más data-driven,
alejándose de configuraciones manuales o por defecto.

### Bitcoin Etapa Avanzada: Incorporación de Técnicas de Validación y Prevención de Data Leak

Con los modelos optimizados, se introdujeron técnicas avanzadas para
garantizar la robustez y evitar problemas comunes en machine learning,
como el sobreajuste o la fuga de datos.

- **Cross Validation avanzada**: Se implementaron variantes como
  stratified k-fold, slicing window y forward chaining, adaptadas al
  desbalanceo de clases.

- **Modificación de la función de pérdida**: Se ajustaron las funciones
  de pérdida (loss functions) para penalizar más los falsos negativos,
  dada la importancia de detectar todas las direcciones sospechosas en
  contextos de ciberseguridad.

- **Particiones de datos**: Se dividieron los datos en múltiples
  conjuntos: entrenamiento (para ajustar el modelo), validación (para
  tuning), calibración (para ajustar probabilidades de salida) y
  evaluación (para pruebas finales). Esta segmentación evitó data leak,
  asegurando que el modelo no \"vea\" datos de prueba durante el
  entrenamiento.

- **Decisión clave**: Tras evaluar el rendimiento y la flexibilidad, se
  optó por utilizar exclusivamente LGBM. Este modelo demostró ser
  suficientemente versátil en hiperparámetros y configuración,
  permitiendo emular comportamientos de RF (por ejemplo, mediante
  ensembles de árboles) y XGBoost (con boosting secuencial) cuando fuera
  necesario. Esto simplificó el pipeline sin sacrificar rendimiento.

Esta etapa enfatizó la importancia de la integridad del proceso de
entrenamiento, alineándose con mejores prácticas en IA aplicada a
seguridad.

### Bitcoin Etapa de Ensamblado: Stacking y Ponderación de Probabilidades

Para mejorar aún más la precisión, se exploraron métodos de ensamblado
que combinan predicciones de múltiples modelos.

> **Stacking inicial**: Se aplicaron técnicas de stacking para ponderar
> las probabilidades de salida de los modelos (RF, XGBoost y LGBM).
> Inicialmente, se utilizaron modelos de regresión logística como
> meta-learner para combinar las probabilidades y generar una predicción
> final.
>
> **Transición a heurísticas**: Aunque la regresión logística funcionó
> bien, se probó con enfoques heurísticos más interpretables, como
> reglas basadas en umbrales o ponderaciones manuales ajustadas
> empíricamente.
>
> **Perfeccionamiento**: Las heurísticas se refinaron iterativamente
> hasta desarrollar un módulo de consensus. Este módulo integra
> probabilidades de manera no paramétrica, considerando factores como la
> confianza del modelo y la correlación entre features (órbitas y
> temporales).

El stacking permitió capturar diversidad en las predicciones, mejorando
la generalización en datos nuevos de transacciones Bitcoin.

### Bitcoin Etapa Final: Iteraciones en la Metodología de Entrenamiento para LGBM

La evolución culminó en refinamientos iterativos enfocados en LGBM, con
énfasis en un entrenamiento unbiased y eficiente.

- **Iteraciones múltiples**: Se realizaron varias rondas de iteración en
  la metodología de entrenamiento, ajustando particiones de datos,
  funciones de pérdida y hiperparámetros basados en retroalimentación de
  evaluaciones previas.

- **Objetivos clave**:

  - **Entrenamiento unbiased**: Se incorporaron técnicas como
    undersampling/oversampling para clases desbalanceadas y
    regularización para reducir sesgos inherentes a los datos de
    ransomware.

  - **Prevención de data leak**: Se reforzaron las particiones estrictas
    y se validaron con hold-out sets independientes.

  - **Eficiencia en uso de datos**: Se optimizó el uso de los datos
    disponibles, maximizando la información de features (órbitas y
    temporales) mediante feature engineering iterativo.

Esta fase aseguró que el sistema final sea robusto, escalable y adecuado
para despliegue en entornos reales de monitoreo de criptomonedas.

### Bitcoin Resultados

En la siguiente sección se presentan los resultados obtenidos tanto a
nivel de ventana temporal como a nivel global (módulo Consensus). Cabe
señalar que, por motivos de extensión y relevancia, no se muestran la
totalidad de los experimentos realizados. Se han evaluado múltiples
algoritmos de clasificación binaria con diversas configuraciones, lo que
permitió descartar ciertas alternativas y valorar el desempeño de
distintas configuraciones. A continuación, se presentan únicamente los
14 experimentos más representativos.

+------------------------------------------+---------------------+---------------+----------------+
| **Identificación**                       | **Características** | > **Ventana** | > **Ensemble** |
+:========================================:+:===================:+:=============:+:==============:+
| **lgbm_orbits_os_window_2021**           | órbitas             | 2021          | No             |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_temp_var_os_window_2021_sd**      | variables           | 2021          | No             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_orbits_os_window_2022**           | órbitas             | 2022          | No             |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_temp_var_os_window_2022_sd**      | variables           | 2022          | No             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_orbits_os_window_2023**           | órbitas             | 2023          | No             |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_temp_var_os_window_2023_sd**      | variables           | 2023          | No             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_orbits_os_window_2023_2024**      | órbitas             | 2023 - 2024   | No             |
+------------------------------------------+---------------------+---------------+----------------+
| **lgbm_temp_var_os_window_2023_2024_sd** | variables           | 2023 - 2024   | No             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **ensemble_logReg_window_2021_sd**       | órbitas y variables | 2021          | Sí             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **ensemble_logReg_window_2022_sd**       | órbitas y variables | 2022          | Sí             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **ensemble_logReg_window_2023_sd**       | órbitas y variables | 2023          | Sí             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **ensemble_logReg_window_2023_2024_sd**  | órbitas y variables | 2023 - 2024   | Sí             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+
| **ensemble_logReg_window_2023_2024_sd**  | órbitas y variables | 2023 - 2024   | Sí             |
|                                          | temporales          |               |                |
+------------------------------------------+---------------------+---------------+----------------+

: []{#_Toc210906532 .anchor}Tabla 3 - Experimentos representativos

#### Conclusiones de experimentos de Bitcoin

Se observa una clara correlación entre el número de muestras positivas
(direcciones sospechosas) y el rendimiento en las métricas, tanto en F1
positiva como en el área bajo la curva ROC (AUC). Ambas métricas
resultan adecuadas para evaluar el grado de generalización del modelo.
En los años 2023 y 2024, donde el número de muestras positivas es
considerablemente inferior respecto a 2021 y 2022 (años en los que se
obtuvieron los mejores resultados), el rendimiento de las métricas
disminuye de manera notable. En particular, el caso de 2024 fue
inicialmente considerado como una ventana independiente, aunque
posteriormente se decidió fusionarlo con 2023 con el fin de incrementar
el número de muestras positivas, consolidando ambos años en una única
ventana.

El experimento más relevante es consensus_20_20_60_mult, ya que
representa la arquitectura final del sistema, integrando los módulos
LGBM entrenados en los experimentos:

> lgbm_temp_var_os_window_2021_sd
>
> lgbm_orbits_os_window_2021
>
> lgbm_temp_var_os_window_2022_sd
>
> lgbm_orbits_os_window_2022
>
> lgbm_temp_var_os_window_2023_2024_sd
>
> lgbm_orbits_os_window_2023_2024

Desde un inicio, se estableció priorizar la reducción de falsos
positivos. Según la matriz de confusión, el porcentaje de falsos
positivos alcanzado es del 3%, lo que se traduce en una precisión del
97% en la clase positiva. Sin embargo, la recuperación (recall) de la
clase positiva es del 48%, lo cual puede considerarse un desempeño
limitado. Para alterar este equilibrio entre precisión y recuperación
---con el consecuente impacto en la tasa de falsos positivos--- existen
varias herramientas:

1.  El umbral de decisión, que ajusta directamente la sensibilidad del
    modelo.

2.  La función objetivo, que actualmente es F1 ponderada lo que
    posibilita la reducción del porcentaje de falsos positivos aún más
    al utilizar F$b$ ponderada con $b$ \> 1 ($b$ \< 1 si se quiere
    priorizar la recuperación) . Esta opción resulta potente, aunque
    implica reentrenar los módulos LGBM.

3.  La configuración del módulo consensus, que también influye en el
    comportamiento del sistema.

Aunque las métricas actuales sugieren que el modelo está preparado para
su uso en inferencia a nivel profesional, debe tenerse en cuenta que las
estrategias de los atacantes de ransomware en la blockchain de Bitcoin
evolucionan de manera continua. Esto obliga a realizar entrenamientos
periódicos con conjuntos de datos actualizados, condición necesaria para
garantizar la efectividad del sistema de detección en entornos reales.

### Ethereum Estrategia y Metodología

Para la clasificación e identificación de actores en la blockchain de
Ethereum, una tarea fundamental para mitigar actividades ilícitas y
fortalecer la seguridad del ecosistema, se ha seguido una metodología
basada en los últimos avances en el campo. El enfoque se centra en el
uso de modelos secuenciales, específicamente inspirados en la
arquitectura BERT, para analizar el historial de transacciones de cada
cuenta.

1.  **Representación de Datos como Secuencias:** En lugar de tratar la
    blockchain como un grafo estático, el historial de transacciones de
    cada cuenta se modela como una secuencia temporal de eventos. Cada
    evento (transacción) se codifica con múltiples características: la
    dirección de la contraparte, el valor de la transferencia
    (discretizado en categorías), la dirección del flujo
    (entrada/salida) y la marca de tiempo.

2.  **Modelo Secuencial (BERT4ETH):** Se utiliza un enfoque basado en el
    modelo Transformer, similar a BERT4ETH. Este modelo se pre-entrena
    de forma auto-supervisada sobre un corpus masivo de secuencias de
    transacciones anónimas. La tarea de pre-entrenamiento, denominada
    *Masked Address Prediction* (MAP), consiste en predecir direcciones
    ocultas en una secuencia, obligando al modelo a aprender patrones
    contextuales y temporales profundos del comportamiento
    transaccional.

3.  **Extracción de *Embeddings* de Comportamiento:** El modelo
    pre-entrenado se utiliza para generar un vector de características
    (un *embedding*) para cada cuenta. Este *embedding* es una
    representación numérica densa que captura la \"huella de
    comportamiento\" de la cuenta, basándose en su historial de
    transacciones. Cuentas con comportamientos similares tendrán
    *embeddings* cercanos en el espacio vectorial.

4.  **Clasificación Supervisada:** Finalmente, estos *embeddings* se
    utilizan como entrada para un clasificador supervisado más clásico
    (como una red neuronal MLP o un Random Forest). Este clasificador se
    entrena con un conjunto de datos etiquetado (direcciones conocidas
    de ransomware, phishing, etc.) para aprender a distinguir entre
    patrones de comportamiento lícitos e ilícitos.

#### Submuestreo Inteligente del Dataset

Dado el enorme volumen de transacciones en Ethereum y el desbalance de
clases (pocas transacciones ilícitas frente a muchísimas legítimas), se
aplica una estrategia de submuestreo estratificado para crear un dataset
de entrenamiento manejable y relevante:

- **Tier 1:** Se conservan todas las transacciones donde participa una
  dirección de ransomware conocida.

- **Tier 2 (1-Hop):** Se conservan todas las transacciones de los
  \"vecinos directos\" de las direcciones de ransomware.

- **Tier 2.5 (2-Hop):** Se muestrea un porcentaje significativo (ej.
  50%) de las transacciones de los \"vecinos de los vecinos\".

- **Tier 3 (Resto):** Para el resto de transacciones, se aplica un
  submuestreo más agresivo basado en un índice de importancia (valor
  económico, conectividad de las direcciones, etc.), reteniendo solo las
  más significativas.

Este enfoque permite entrenar los modelos de manera eficiente,
centrándose en la actividad más relevante para la detección de actores
maliciosos.

### Gestión de la inteligencia artificial para Polygon

La aplicación de técnicas de inteligencia artificial para la detección
de actores ilícitos en Polygon se beneficia enormemente de su
compatibilidad con la Máquina Virtual de Ethereum (EVM). Esta
compatibilidad permite que los algoritmos y modelos diseñados para
Ethereum sean, en gran medida, directamente portables a Polygon.

#### Compatibilidad y Adaptación

La viabilidad de esta transferencia de conocimiento se basa en cuatro
pilares fundamentales:

1.  **Equivalencia de la EVM:** La lógica de ejecución de los contratos
    inteligentes es idéntica en ambas redes, lo que significa que un
    contrato malicioso se comportará de la misma manera.

2.  **Interfaces de Comunicación Comunes:** Polygon utiliza la misma API
    JSON-RPC y la misma Application Binary Interface (ABI) que Ethereum,
    permitiendo que las herramientas de extracción y análisis de datos
    funcionen sin modificaciones.

3.  **Homología de Estructuras de Datos:** Los objetos de transacción y
    los recibos (incluyendo los logs de eventos) son estructuralmente
    idénticos, lo que garantiza la compatibilidad de los pipelines de
    datos.

4.  **Modelo de Cuentas Compartido:** Ambas redes utilizan el mismo
    modelo contable, lo que resulta en grafos transaccionales que son
    isomórficos. Los algoritmos que operan sobre la estructura del grafo
    son, por tanto, compatibles.

# Gestión DE EVENTOS Y MOTOR DE REGLAS

## Introducción

Dentro de este prototipo, una de las piezas principales es el **motor de
reglas**. Este módulo es el encargado de transformar los datos y flujos
de información que se generan en el backend de la solución en alertas.
Esta **transformación** se realiza a través de la evaluación de una
serie de **reglas de negocio** en conjunción **con los flujos de
Inteligencia artificial** permitiendo la evaluación sistemática de las
carteras involucradas en las transacciones bajo monitorización. Las
alertas generadas posteriormente son enviadas al frontal web para su
visualización y gestión por parte de los usuarios de la plataforma.

![](media/image38.png){width="5.833333333333333in"
height="3.1073775153105863in"}

[]{#_Toc210906573 .anchor}Ilustración 32 -- Gestor de eventos:
estructura lógica

Esta **monitorización sustentada por la Inteligencia Artificial** ofrece
dos capacidades básicas asociadas a los casos de uso de la solución:

- Determinar si hay indicios de que la **actividad de una cartera
  monitorizada** está involucrada en **actividades ilícitas** (casos de
  ransomware)

- Determinar si una cartera está interactuando (aguas arriba o aguas
  abajo) con una cartera que, como en el caso anterior, pudiera estar
  involucrada con actividades ilícitas (casos de ransomware)

Este módulo responde a las **necesidades** prácticas planteadas por las
**entidades usuarias** de la solución, permitiendo transformar los
resultados y modelos generados dentro del módulo de inteligencia
artificial, en unos casos de uso específicos y alineados con sus
objetivos.

**Proceso basado en Inteligencia Artificial**

La definición de los tipos de reglas es una **implementación particular
de los sistemas que habitualmente permiten identificar situaciones
sospechosas o dudosas que pudieran presentar algún tipo de relación con
actividades ilícitas**. No obstante, este tipo de soluciones basados
únicamente en heurísticas, sobre la monitorización del comportamiento de
carteras en la blockchain, puede desembocar en **predicciones erróneas y
la generación de un gran número de falsos positivos**, es decir, de
casos que sin tratarse de actividades maliciosas, el sistema las
categoriza como tal, lanzando las acciones de negocio que se hayan
establecido. Este tipo de sistemas, pueden estar prejuzgando un
comportamiento completamente lícito, únicamente por la mera presencia de
unos indicadores básicos, como la ejecución de unas operativas en un
determinado orden a partir de ciertas necesidades de negocio.

El **valor de la Inteligencia Artificial** que se ha incluido en este
prototipo va en la línea de **remediar este tipo de situaciones**. De
forma que, no solo se trata de categorizar algo en base a unos
indicadores operacionales, sino también apoyándose a las **métricas de
sospecha proporcionadas por la propia inteligencia artificial**. Este
punto diferencial permite dar más fiabilidad a los resultados que
incluye la información proporcionada por los dos sistemas.

## Proceso de captura de datos

El proceso de captura de datos corresponde con los mecanismos
establecidos para recopilar la información en tiempo real de las
distintas fuentes establecidos.

![[]{#_Toc210906574 .anchor}Ilustración 33 -- Gestor de eventos:
estructura
software](media/image39.png){alt="A diagram of a diagram AI-generated content may be incorrect."
width="6.102083333333334in" height="3.1020833333333333in"}

**Fuentes de información**

El sistema recibe eventos desde múltiples blockchains (como Bitcoin,
Ethereum, Polygon), a través de procesos externos encargados de capturar
y transformar las transacciones desde los nodos hacia un formato
unificado. Estos procesos están implementados en Python y publican los
datos en tópicos Kafka.

**Flujos de transmisión**

El canal principal de transmisión de eventos es un sistema de colas
(Kafka), que permite desacoplar la generación de eventos de su
procesamiento posterior. Los eventos, una vez publicados, son consumidos
en tiempo real por un motor de procesamiento de flujos basado en Apache
Flink que enruta de forma dinámica los eventos blockchain hacia las
reglas correspondientes, en función de las direcciones monitoreadas
configuradas, optimizando así el rendimiento del proceso de evaluación.

![[]{#_Toc210906575 .anchor}Ilustración 34 -- Captura gestor de eventos:
Jobs en
ejecución](media/image40.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.134027777777778in"}

Este motor es capaz de aplicar transformaciones, evaluar condiciones y
generar eventos derivados (como alertas) en función del contexto de cada
transacción. También se permite el procesamiento programado de ciertos
patrones que requieren análisis temporal o acumulado.

La arquitectura incorpora mecanismos de persistencia (OpenSearch) que
permiten tanto consultas interactivas como soporte a evaluaciones más
complejas.

**Modelo interno de información**

A nivel interno, el sistema opera con un modelo de eventos
transaccionales unificado. Este modelo agrupa la información relevante
sobre cada transacción: direcciones implicadas, valores transferidos,
contexto temporal, y metadatos asociados.

Sobre este modelo se aplica la lógica de negocio, que interpreta cada
evento en función de las reglas definidas. Las reglas operan sobre
entidades abstractas, como "dirección", "saldo", o "entidad de destino",
lo que facilita su reutilización y la extensión del sistema a nuevas
redes o tipologías de datos.

Los eventos transformados siguen un modelo común que incluye:

- Dirección de origen y destino

- Monto y moneda

- Fecha/hora de la transacción

- Tipo de evento (IN, OUT, SELF)

- Blockchain de origen

Este modelo se almacena en OpenSearch para posterior consulta por
reglas, visualización o auditoría.

Aquí podemos ver el índice de OpenSearch en el que se almacenan los
diferentes eventos(Transacciones de las blockchain).

![A screenshot of a computer AI-generated content may be
incorrect.](media/image41.png){width="6.102083333333334in"
height="2.3847222222222224in"}

[]{#_Toc210906576 .anchor}Ilustración 35 -- Captura elementos
monitorizados

![A screenshot of a computer AI-generated content may be
incorrect.](media/image42.png){width="6.102083333333334in"
height="2.6534722222222222in"}

[]{#_Toc210906577 .anchor}Ilustración 36 -- Captura elementos
monitorizados: búsqueda (1)

![[]{#_Toc210906578 .anchor}Ilustración 37 -- Captura elementos
monitorizados: búsqueda
(2)](media/image43.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.6708333333333334in"}

## Regla de negocio

Tras capturar la información, el sistema evalúa los datos que se van
cargando para identificar correspondencias lógicas de acuerdo con las
necesidades de negocio establecidas. Estas necesidades de implementan en
la forma de reglas.

**Estructura y tipos de reglas**

Cada regla se configura con los siguientes elementos clave:

- Identificador único y nombre

- Blockchain objetivo

- Direcciones que monitorear

- Criticidad (severidad)

- Canal de notificación

- Metadatos dinámicos

El sistema soporta los siguientes tipos de regla:

  -----------------------------------------------------------------------------
  Tipo de regla       Descripción
  ------------------- ---------------------------------------------------------
  Off-Ramp            Detecta transferencias hacia direcciones sospechosas de
                      acuerdo con los criterios establecidos por las técnicas
                      de inteligencia artificial.

  Balance             Evalúa la perdida significativa de balance en una
                      dirección

  Dormant-to-Active   Detecta actividad reciente tras un largo periodo de
                      inactividad

  Peeling Chain       Identifica envíos pequeños y consecuetivos a múltiples
                      destinos distintos
  -----------------------------------------------------------------------------

  : []{#_Toc210906533 .anchor}Tabla 5 -- Reglas de detección de
  actividades fraudulentas

Cada tipo está asociado a un evaluador específico que implementa la
lógica necesaria para determinar si se cumplen las condiciones
configuradas.

![[]{#_Toc210906579 .anchor}Ilustración 38 -- Captura creación de regla
de monitorización en tiempo
real](media/image44.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.1305555555555555in"}

**Proceso evaluador**

El motor de evaluación asocia cada regla a un módulo evaluador. Existen
dos modos de evaluación:

- **Tiempo real:** Se ejecuta al recibir un evento nuevo (por ejemplo,
  una transacción en Kafka).

Aquí podemos ver uno de los Jobs en apache Flink, que procesan en
streaming las transacciones que los procesos de ingesta de blockchain
dejan en topics de KAFKA. Se recogen los eventos desde el source de
Kafka y en este caso se evalúan reglas OffRamp sobre estos eventos en
tiempo real.

![[]{#_Toc210906580 .anchor}Ilustración 39 -- Captura gestor de eventos:
flujo de
ejecución](media/image45.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.4694444444444446in"}

- **Evaluación periódica:** Se realiza de forma programada sobre datos
  históricos, consultando OpenSearch con plantillas predefinidas.

Dependiendo del tipo de regla, se accede a información histórica (como
fechas de transacción o balances), se aplican condiciones umbral, y se
valida si la dirección analizada presenta un patrón anómalo.

La evaluación es modular y extensible: nuevas reglas pueden
implementarse simplemente creando una subclase de Rule y su evaluador
correspondiente.

Aquí vemos el job en Apache Flink, que lanza evaluaciones periódicas, de
las diferentes reglas (Balance, Peeling Chain ..,) sobre los datos
almacenados en OpenSearch.

Previamente, los datos de las transacciones son almacenas en OpenSearch
en Jobs de Apache Flink que procesan en streaming los eventos
almacenados en Kafka, los tranforman y los cargan en Opensearch.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image46.png){width="6.102083333333334in"
height="2.667361111111111in"}

[]{#_Toc210906581 .anchor}Ilustración 40 -- Captura Gestor de eventos,
dependencia de procesos

## Gestión enriquecida con técnicas de Inteligencia Artificial

El **uso de la inteligencia artificial en conjunción con el sistema de
reglas anterior para el análisis de los flujos es uno de los valores
diferenciales de esta solución**. Esta combinación permite evitar los
problemas descritos con anterioridad a los que están expuestos los
sistemas tradicionales. Las opciones para combinar ambos sistemas con el
objetivo de proporcionar **resultados más precisos** son diversas,
dentro de este prototipo, y acorde a las necesidades por la entidad
usuaria, actualmente nos centramos en las capacidades de evaluar las
transacciones y las carteras involucradas en las transacciones
relacionadas con los elementos bajo monitorización (tanto aguas arriba
como aguas abajo). Esta evaluación es doble, por un lado, la propia
evaluación relativa a las propias sospechas de una determinada cartera
por su actividad pasada; en la otra mano la evaluación de que las
transacciones del elemento monitorizado forman parte de un patrón de
pago de *mixers*.

- **Nivel de sospecha de carteras**

El **módulo de Inteligencia Artificial** aplica modelos de detección de
actividad ilícita asociada a **ransomware** sobre datos on-chain. Para
cada **dirección** (address) calcula una **puntuación de riesgo** entre
**0 y 1**, donde 0 indica *baja probabilidad* y 1 *alta probabilidad* de
implicación en flujos vinculados a ransomware, considerando su
**comportamiento histórico y reciente**.\
Esta puntuación enriquece el **motor de reglas**: cuando el sistema
detecta que una de nuestras **direcciones monitorizadas** ha
interactuado con una **dirección catalogada como maliciosa**, además de
la coincidencia por listas/etiquetas contrastamos el evento con la
**predicción de IA** de esa contraparte. Si la puntuación de IA es
**mayor o igual que un umbral** definido por el analista, **reforzamos
la alerta** y elevamos su prioridad, al aportar evidencia probabilística
adicional.

Por lo tanto, en la definición de las reglas se añaden umbrales
configurables o THRESHOLD de predicción, por ejemplo 0.7. La alerta
final combinará la **evidencia determinista** detectada por la regla por
contacto con una address marcada como sospechosa, con una **evidencia
probabilística** dada por la puntuación de la IA. En función de esto
podremos ajustar la severidad de la Alerta final.

- **Gestión de mixers**

El **Módulo IA de Detección de Mixers** complementa la puntuación por
dirección incorporando una señal específica a nivel de transacción. A
partir de **heurísticas avanzadas** (p. ej., patrones de CoinJoin,
múltiples entradas / salidas, salidas de valor igual, peel chains,
comportamiento de change, temporalidad y estructuración de montos) y
modelos de clasificación, el módulo asigna a cada transacción una
puntuación de mezcla mixer_score (0,1), donde 0 indica baja probabilidad
y 1 alta probabilidad de uso de servicios de mezcla u otras técnicas de
ofuscación.

En la evaluación de reglas en las que se monitorizan transacciones de
nuestras addreses monitorizadas, ahora podemos dar un valor añadido con
la información aportada por este modulo de detección de mixers. Podemos
ver si nuestras addreses pueden estar involucradas en transacciones con
un valor a partir del cual el analista identifique dichas transacciones
como posibles Mixers.

Vincular una **transacción de una dirección monitorizada** con un
**mixer** aporta una **señal de riesgo adicional** que refuerza (o
matiza) lo que ya sabemos por listas de direcciones maliciosas. Podemos
subir la severidad de nuestras alertas si el riesgo de mixer es alto.

## Alertas

Tras identificar estas correspondientes, existe una lógica de negocio
para generar las correspondientes alertas de notificación a los usuarios
del sistema.

**Concepto de prealerta**

El sistema incorpora un mecanismo de **prealertas** que actúa como una
primera fase de detección temprana. Cada evaluador de regla, una vez
procesado un evento blockchain, genera una prealerta si se detecta un
patrón potencialmente sospechoso.

Estas prealertas:

- Se representan como objetos livianos que encapsulan la información
  esencial del evento y la regla evaluada.

- Son enviadas a un **tópico específico de Kafka**, lo que permite su
  desacoplamiento del flujo de generación de alertas finales.

- Permiten introducir una **capa adicional de análisis o
  enriquecimiento** mediante stream processing.

**Gestión de una alerta**

Las prealertas publicadas en Kafka son procesadas por un pipeline de
**Apache Flink**, que implementa lógica de evaluación adicional,
correlación y filtrado. Este proceso puede:

- Validar si la prealerta cumple criterios adicionales para convertirse
  en una alerta definitiva.

- Enriquecer el contenido con información contextual.

- Aplicar reglas cruzadas o restricciones por ventana temporal.

Una vez cumplidas las condiciones, se genera una **alerta final**, la
cual contiene:

- Identificador de la regla origen.

- Dirección objetivo afectada.

- Severidad.

- Blockchain involucrada.

- Información adicional para análisis (trazas, resumen cuantitativo,
  etc.).

![[]{#_Toc210906582 .anchor}Ilustración 41 -- Captura alerta generada
por sistema de
monitorización](media/image47.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.745833333333333in"}

Estas alertas son luego distribuidas a través de distintos canales según
configuración. Ahora mismo el canal de distribución es una API de
nuestro sistema encargada de la gestión de Alertas que luego se
visualizarán y gestionarán desde el portal web de la aplicación.

# ARQUITECTURA FíSICA DEL PROTOTIPO 

## Introducción

En los puntos anteriores se ha descrito cuales son las necesidades
funcionales y de gestión de información. Del mismo modo se han
proporcionado diseños lógicos, con el fin de proporcionar contexto sobre
las soluciones propuestas para cada módulo. Estos diagramas corresponden
con una visión abstracta del proyecto, ofreciendo una visión
simplificada y genérica de la solución a implementar.

Ahora en este punto, se **baja a la capa física**, proporcionando una
**visión más específica y concreta del hardware empleado en la solución
de arquitectura propuesta para este proyecto**. En este sentido,
pasaremos a definir la solución para cada módulo, así como los elementos
requeridos para los distintos flujos de comunicación.

### Requisitos de arquitectura y no funcionales

De acuerdo con los requisitos establecidos en la documentación del
proyecto, **la capa de arquitectura e infraestructura de este prototipo
debe de cumplir los puntos incluidos** en la siguiente tabla:

  ---------------------------------------------------------------------------
  Cód        Título             Descripción
  ---------- ------------------ ---------------------------------------------
  ENS-0001   Escalabilidad      El sistema debe de ser capaz de escalar para
                                manejar un creciente volumen de transacciones
                                procedentes de diversas blockchains, sin que
                                exista una degradación en el servicio.

  ENS-0002   Tiempo Real        Debe ser capaz de procesar diversas fuentes
                                de datos de entrada en tiempo real.

  ENS-0003   Eficiencia         Hacer uso eficiente de los recursos
                                computacionales disponibles y de
                                almacenamiento para mantener costos
                                operativos bajos

  ENS-0004   Auditoria y        Capacidades de auditoría y trazabilidad de
             trazabilidad de    operaciones solicitadas por los usuarios
             operaciones        

  ENS-0005   Monitorización del Capacidad de monitorizar y controlar el
             sistema            estado de salud general de la aplicación y
                                todos sus componentes, permitiendo
                                identificar cuellos de botella u otro tipo de
                                problemas.

  ENS-0006   Gestión de grandes Capacidad de ingestar, almacenar y explotar
             volúmenes de datos grandes volúmenes de datos.

  ENS-0007   Alta               Asegurar que el sistema es redundante y
             disponibilidad     cuente con backup para conectarse
                                automáticamente al sistema de backup o
                                replica en caso de fallos. Asegurar el
                                rendimiento del sistema mediante balanceo de
                                carga.

  ENS-0008   Conexiones Seguras Sistemas de intercambio de información por
                                métodos seguros(TLS, encriptación)

  ENS-0009   Datos protegidos   Sistema de encriptación de información
             en reposo          almacenada (protección datos en reposo)

  ENS-0010   Procedimientos     Documentos procedimentales de actualizaciones
             operativos         de infraestructura y planes de recuperación
             Infraestructura    

  ENS-0011   Autenticación      La arquitectura de la aplicación controla que
             segura             el acceso a todos los componentes se realiza
                                de forma segura.

  ENS-0012   Autorización por   Definición de roles y funcionalidades y
             asignación de      cumplir con el principio Need to know/Need to
             roles              use

  ENS-0013   Compatibilidad     Los navegadores standard: Edge, Chrome,
             Navegadores        Firefox

  ENS-0014   Medidas contra     Se instalarán los agentes de seguridad
             malware y test de  necesarios para monitorizar y bastionar los
             vulnerabilidades   sistemas que lo requieran

  ENS-0015   Versiones de       Versiones de componentes validadas por el
             componentes        fabricante y con parches de seguridad
             validados          periódicos

  ENS-0016   Actualizaciones    Se dispone de la capacidad de realizar
                                actualizaciones e implementar correcciones de
                                error sin caída prolongada del sistema.

  ENS-0017   Orquestación de    El sistema incluirá un mecanismo para la
             ingestadores       gestión de los sistemas que permitan la
             externos de datos  ingesta de datos de fuentes externas. 
  ---------------------------------------------------------------------------

  : []{#_Toc210906534 .anchor}Tabla 6 -- Especificaciones no funcionales
  del prototipo

Las necesidades establecidas para este proyecto condicionan el tipo de
solución que se ofrece, y por tanto la propia infraestructura física
empleada. En este sentido, el diseño planteado ofrece una solución
ajustada a los requisitos, buscando compatibilizar una buena performance
junto con un control en el coste. Del mismo modo, se hará uso de
soluciones que permitan el escalado tanto horizontal como en vertical,
así como soluciones estándares que permitan tanto la migración a otro
proveedor cloud, como el uso de sus servicios si así lo demanda las
necesidades de comercialización de esta solución.

A lo largo de este epígrafe, veremos los aspectos particulares de la
arquitectura física de la solución, así como aquellos aspectos
singulares para dar cabida a los requisitos no funcionales y de
arquitectura establecidos en la tabla anterior.

## Diagrama General de Arquitectura

La implantación de este prototipo se ha realizado en AWS. Los
principales motivos por los que se ha utilizado infraestructura cloud, y
en particular AWS, son los siguientes: **escalabilidad, disponibilidad
global**, **servicios gestionados de alto nivel**, y una integración
nativa con herramientas clave para el procesamiento de datos,
**almacenamiento masivo y despliegue de modelos de inteligencia
artificial**. AWS proporciona un ecosistema maduro y robusto que permite
acelerar el desarrollo de soluciones complejas, reducir el coste
operativo de la infraestructura y garantizar niveles altos de seguridad
y cumplimiento normativo.

Además, AWS ofrece una amplia gama de **servicios especializados** que
han sido fundamentales para cubrir los distintos módulos funcionales de
la solución. En el siguiente diagrama se detalla la infraestructura y la
relación entre los distintos componentes que forman parte de esta
solución en la nube.

![[]{#_Toc210906583 .anchor}Ilustración 42 -- Diagrama general
infraestructura física](media/image48.png){width="5.7027777777777775in"
height="2.0764687226596674in"}

![[]{#_Toc210906584 .anchor}Ilustración 43 -- Captura listado de
servidores
EC2](media/image49.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.0965277777777778in"}

En las siguientes secciones se hace un análisis más detallado de cada
elemento. De todas formas, y de manera general se pasa a detallar los
**elementos principales de esta solución**:

- Cuenta **VPC** de la aplicación. De manera general contar con una VPC
  específica para la solución permite garantizar el **aislamiento y
  establecer controles de seguridad** para limitar el acceso a aquellos
  perfiles que corresponda desde el punto de vista de la
  infraestructura. ^(ENS-0011\ y\ ESN-0012)^

- Instancias **EC2**. Por su versatilidad y rápida configuración, se ha
  hecho uso este tipo de servidores virtuales. Si bien, en cada caso
  tiene una configuración particular y ajustada a las necesidades de
  cada capa, en todo caso se ha hecho uso de máquinas Ubuntu 22.04.
  Posteriormente en las siguientes secciones se bajará a más detalle en
  los procesos que corren en cada una de ellas.

  - Estas instancias virtuales garantizan la escalabilidad tanto
    horizontal como vertical, dependiendo de las necesidades
    particulares de cada caso y el uso eficiente de la infraestructura.
    ^(ESN-0001\ y\ ESN-0003)^

- Volúmenes de almacenamiento **EBS**. Sobre todo, para aquellos casos
  donde se requiere de unas altas necesidades de almacenamiento, como
  pueden ser los servidores donde corren los nodos de las distintas
  blockchains. ^(ESN-0006)^

  - Las posibilidades de establecer el algoritmo de cifrado de la
    información en reposo, permite garantizar la protección de los
    datos. ^(ESN-0009)^

- **Cloudwatch**, como solución genérica para la gestión segura de los
  logs de todos los servicios que corren en las distintas componentes de
  la solución. ^(ESN-0004)^

  - Cloudwatch se acompaña de los elementos de gestión y generación de
    alertas para aquellos casos en los que sea necesario. ^(ESN-0005)^

- Buckets **S3**, es la solución de almacenamiento centralizada de
  ficheros y datos de larga retención. ^(ESN-0006)^

- **AWS Backups**, para la centralización de los backups y los
  procedimientos operativos asociados a la ejecución programada de los
  backups y de restauración de la infraestructura si así es necesario.
  ^(ESN-0010)^

- **AWS System Manager** para la ejecución centralizada de operaciones
  de mantenimiento y soporte de los servidores empleados para la
  solución. ^(ESN-0016)^

- **AWS IAM,** para la configuración de los permisos y roles de acceso a
  la infraestructura. ^(ESN-0012)^

En las siguientes subsecciones pasaremos a mostrar los detalles de las
infraestructuras empleadas para cada módulo. La información sobre la
motivación y requisitos a cubrir han quedado previamente expuestos en
las distintas secciones de este mismo documento.

## Módulo de Ingesta 

El módulo de ingesta de información constituye uno de los componentes
fundamentales del sistema, ya que se encarga de recolectar y procesar
los datos provenientes de las blockchains establecidas para este
proyecto ^(REQ-0001)^. Se ha desarrollado un pipeline de ingesta para
las tres redes blockchain: **Bitcoin**, **Ethereum** y **Polygon**, cada
una con particularidades técnicas, estructurales y operativas que han
influido en la implementación de este módulo.

### Integración de Bitcoin

Vista general de la solución de arquitectura bajo estudio para la
ingesta de la *blockchain* de *bitcoin* y ETL. Para la implementación de
la solución, se va a hacer uso de infraestructura en AWS.

En este sentido el siguiente diagrama general visualiza los elementos
empleados:

![[]{#_Toc210906585 .anchor}Ilustración 44 -- Diagrama físico Ingesta
Bitcoin](media/image50.emf)

### Detalle Nodo Ingestión

![[]{#_Toc210906586 .anchor}Ilustración 45 -- Diagrama físico Ingesta
Bitcoin (2)](media/image51.emf)

### Integración de Ethereum

Vista general de la solución de arquitectura bajo estudio para la
ingesta de la *blockchain* de *ETHEREUM* y su ETL. Para la
implementación de la solución, se va a hacer uso de infraestructura en
AWS.

![[]{#_Toc210906587 .anchor}Ilustración 46 -- Diagrama físico Ingesta
Ethereum](media/image52.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.432638888888889in"}

### Integración de Polygon

Vista general de la solución de arquitectura bajo estudio para la
ingesta de la *blockchain* de *POLYGON* y su ETL. Para la implementación
de la solución, se va a hacer uso de infraestructura en AWS.

![[]{#_Toc210906588 .anchor}Ilustración 47 -- Diagrama físico ingesta
Polygon](media/image53.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.432638888888889in"}

## Módulo de Enriquecimiento

![[]{#_Toc210906589 .anchor}Ilustración 48 -- Diagrama físico
Pipeline](media/image54.emf)

## Datalake

La solución de **datalake** actúa como una capa de persistencia
unificada que integra información procedente de múltiples orígenes
heterogéneos.

A través de procesos ETL, los datos son transformados y almacenados en
diferentes sistemas según su naturaleza: **PostgreSQL** para estructuras
relacionales y **Neo4j** para datos con relaciones dinámicas y
jerárquicas.

Todo ello expuesto mediante una **API interna unificada (FastAPI)** que
facilita el acceso y la gestión de la información. ENS-0006

![[]{#_Toc210906590 .anchor}Ilustración 49 -- Diagrama físico API
datalake](media/image55.png){width="6.1in" height="3.575in"}

### Detalles técnicos

  -----------------------------------------------------------------------
      Instancia     Type           IP Privada          IP Publica
  ----------------- -------------- ------------------- ------------------
      EC2 Neo4J     m6a.xlarge     172.31.6.135        3.69.54.153

   EC2 IA & Motor   m6a.4xlarge    172.31.3.207        3.65.28.93
       eventos                                         

       EC2 BTC      c6a.xlarge     172.31.6.80         18.192.20.3

       EC2 ETH      m7a.xlarge     172.31.13.252       3.69.51.139

       EC2 POL      m7a.xlarge     172.31.1.243        35.159.72.130

    EC2 WebFront    c6a.large      172.31.40.227       63.177.213.117

    EC2 Datalake    m6a.xlarge     172.31.6.135        3.69.54.153
  -----------------------------------------------------------------------

  : []{#_Toc210906535 .anchor}Tabla 7 -- Detalle de red Servidores
  Infraestructura

## Módulo de Inteligencia Artificial

![[]{#_Toc210906591 .anchor}Ilustración 50 -- Diagrama físico Módulo de
IA](media/image56.png){width="6.09375in" height="4.34375in"}

### Detalles técnicos

  -----------------------------------------------------------------------
      Instancia     Type           IP Privada          IP Publica
  ----------------- -------------- ------------------- ------------------
    EC2 Airflow &   m6a.xlarge     172.31.6.135        3.69.54.153
      Datalake                                         

  EC2 Motor Eventos m6a.4xlarge    172.31.3.207        3.65.28.93
    & IA Process                                       
  -----------------------------------------------------------------------

  : []{#_Toc210906536 .anchor}Tabla 8 -- Detalle de red Módulo de IA

## Módulo Gestor de Eventos

Este módulo es el encargado de transformar los datos y flujos de
información que se generan en el backend de la solución en alertas. Esta
**transformación** se realiza a través de la evaluación de una serie de
**reglas de negocio** en conjunción **con los flujos de Inteligencia
artificial** permitiendo la evaluación sistemática de las carteras
involucradas en las transacciones bajo monitorización. Las alertas
generadas posteriormente son enviadas al frontal web para su
visualización y gestión por parte de los usuarios de la plataforma.

Este apartado describe la arquitectura de un entorno **streaming
batch/near-real-time** basado en **Apache Flink 2.0 (Java 17)**,
**Apache Kafka 4.0**, **Kafka Connect (Debezium 3.0)**, **OpenSearch
3.0** (con **Dashboards**) y **Redis 7**, orquestado mediante **Docker
Compose**. El diagrama adjunto representa los componentes, relaciones de
red y puntos de acceso principales expuestos por el despliegue.

![[]{#_Toc210906592 .anchor}Ilustración 51 -- Diagrama físico Gestor de
Eventos](media/image57.png){alt="A diagram of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.432638888888889in"}

### Detalles técnicos

  -----------------------------------------------------------------------
      Instancia     Type           IP Privada          IP Publica
  ----------------- -------------- ------------------- ------------------
      EC2 Neo4J     m6a.xlarge     172.31.6.135        3.69.54.153

   EC2 IA & Motor   m6a.4xlarge    172.31.3.207        3.65.28.93
       eventos                                         

       EC2 BTC      c6a.xlarge     172.31.6.80         18.192.20.3

       EC2 ETH      m7a.xlarge     172.31.13.252       3.69.51.139

       EC2 POL      m7a.xlarge     172.31.1.243        35.159.72.130

    EC2 WebFront    c6a.large      172.31.40.227       63.177.213.117

    EC2 Datalake    m6a.xlarge     172.31.6.135        3.69.54.153
  -----------------------------------------------------------------------

  : []{#_Toc210906537 .anchor}Tabla 9 -- Detalle de red Gestor Eventos

## Frontal Web y Custodia

Dentro de los aspectos fundamentales para este prototipo se encuentra el
proporcionar una solución web en la que los distintos tipos de usuarios
puedan gestionar y proceder con la ejecución de los casos de uso
establecidos para este prototipo. ^(REQ-0008\ y\ REQ-0006)^

Esta solución web proporcionará un interfaz, accesible a través del
navegador web, por el que cada usuario, dependiendo de su rol y
configuraciones, pueda consumir y gestionar los datos correspondientes.

Este apartado describe la arquitectura de un entorno **web** y de
**procesamiento en segundo plano** basado en **Nginx**, una aplicación
PHP con un **worker de colas**, **Redis 7** como servicio auxiliar de
baja latencia, **Fluentd** para recolección de logs. Todos los
componentes se orquestan mediante **Docker Compose** y comparten
volúmenes persistentes (incluido **EFS** para certificados y ficheros de
aplicación).

Se accede a servicios externos de Custodia y Autenticación.

El diagrama adjunto representa los **componentes**, sus **relaciones de
red**, los **puntos de acceso** expuestos, así como los volúmenes y
dependencias más relevantes.

![[]{#_Toc210906593 .anchor}Ilustración 52 -- Diagrama físico Frontal
Web](media/image58.png){alt="A screenshot of a computer screen AI-generated content may be incorrect."
width="6.102083333333334in" height="3.432638888888889in"}

### Detalles técnicos

  -----------------------------------------------------------------------
      Instancia     Type           IP Privada          IP Publica
  ----------------- -------------- ------------------- ------------------
    EC2 WebFront    c6a.large      172.31.40.227       63.177.213.117

  -----------------------------------------------------------------------

  : []{#_Toc210906538 .anchor}Tabla 10 -- Detalle de red Frontal Web

## Gestión Backups

Esta sección describe la arquitectura de **copias de seguridad
centralizadas** del sistema mediante **AWS Backup**, cuyo objetivo es
**proteger y restaurar** recursos críticos con políticas homogéneas,
trazabilidad y controles de retención. El diagrama adjunto muestra el
flujo lógico: **recursos protegidos** → **plan de backup** → **vault
cifrado con Vault Lock** → **operaciones de restauración**.

La protección se aplica mediante **asignaciones por ARN y etiqueta**,
cubriendo:

- **Instancias EC2**: arn:aws:ec2:\*:\*:instance/\* filtradas por la
  etiqueta\
  aws:ResourceTag/company = Deloitte.

- **Clusters Aurora (RDS)**: arn:aws:rds:\*:\*:cluster:\* filtrados por
  la etiqueta\
  aws:ResourceTag/company = Deloitte.

El plan de backup se ejecuta con una frecuencia diaría. Los backups se
guardan con una retención de 35 días.

![[]{#_Toc210906594 .anchor}Ilustración 53 -- Diagrama físico
Backup](media/image59.png){width="6.1in" height="3.558333333333333in"}

## Conexiones equipo desarrollo

Para la gestión de acceso externo al ecosistema AWS, se hace uso de los
Security Groups (FW de AWS), dando acceso acotado por IP de cada
usuario/agente al puerto 22 "SSH".

En caso de necesitar acceder a otro puerto, el usuario deberá establecer
un túnel SSH para acceder a los puertos internos.

Un ejemplo de la configuración:

- Inbound rules:

![[]{#_Toc210906595 .anchor}Ilustración 54 -- Captura reglas de acceso
equipo de desarrollo](media/image60.png){width="6.102083333333334in"
height="0.47291666666666665in"}

- Outbound rules:

![[]{#_Toc210906596 .anchor}Ilustración 55 -- Captura reglas de salida
equipo de desarrollo](media/image61.png){width="6.102083333333334in"
height="0.5222222222222223in"}

> A continuación, el diagrama de arquitectura:

![[]{#_Toc210906597 .anchor}Ilustración 56 -- Diagrama de arquitectura
acceso equipo de
desarrollo](media/image62.png){width="6.097222222222222in"
height="3.089583333333333in"}

## Solución basada en contenedores

Dentro de los puntos anteriores se ha expuesto la solución de
arquitectura desplegada para cubrir los aspectos funcionales y técnicos
establecidos para este proyecto.

En ese sentido, desde una visión puramente técnica, la implementación
realizada basada en contenedores dockers, así como la segregación de
responsabilidades en componentes más unitarios, permiten el escalado de
la solución en aquellos puntos que así lo requieran.

Una arquitectura basada en Docker permite establecer **contenedores
independientes para cada una de las soluciones de integración**
establecidas en este proyecto. Esta aproximación facilita la mejora
continua de cada componente de forma aislada, optimizando su
rendimiento, mantenimiento, despliegue y eficacia de manera general.
Además, el uso de contenedores garantiza un entorno de ejecución
coherente entre desarrollo, pruebas y producción, reduciendo problemas
de compatibilidad y facilitando la escalabilidad, monitorización y
control individualizado de cada servicio dentro de la solución global.

Entre las principales ventajas de utilizar Docker se encuentran **la
portabilidad, la eficiencia y la consistencia del entorno de
ejecución**. Al empaquetar aplicaciones junto con todas sus
dependencias, Docker permite que los contenedores se ejecuten de manera
idéntica en diferentes entornos, ya sea en entornos locales o en la
nube. Además, **los contenedores son livianos y arrancan rápidamente**,
lo que mejora significativamente los tiempos de despliegue y reduce el
consumo de recursos en comparación con las máquinas virtuales
tradicionales. Como ya veremos en la sección de desarrollo y despliegue
de este documento, esta tecnología también favorece la integración con
prácticas DevOps, como la integración y entrega continuas (CI/CD), al
permitir la automatización y estandarización de los entornos de
desarrollo y producción.

La solución propuesta soporta la opción de incluir contenedores
personalizados. Esta capacidad permite la integración dentro del sistema
de otras fuentes de información de otra índole o naturaleza. En este
sentido, la solución de arquitectura propuesta permite que, en el futuro
y fuera del ámbito de este proyecto, se realice la integración de otras
soluciones de inteligencia artificial para mejorar la precisión y
calidad de los resultados.

# APLICACION WEB Prototipo 

## Introducción

Dentro de los aspectos fundamentales para este prototipo se encuentra el
proporcionar una solución web en la que los distintos tipos de usuarios
puedan gestionar y proceder con la ejecución de los casos de uso
establecidos para este prototipo. ^(REQ-0008\ y\ REQ-0006)^

Esta solución web proporcionará un interfaz, accesible a través del
navegador web, por el que cada usuario, dependiendo de su rol y
configuraciones, pueda consumir y gestionar los datos correspondientes.

## Características principales

La aplicación sigue los principios y la guía de estilos establecida para
las soluciones que van a formar parte del portfolio de soluciones de
Deloitte. En ese sentido, la firma pone en manos de los equipos técnicos
una documentación donde se describen aquellos aspectos principales que
se debe cumplir. Aspectos como el uso del negro, y el verde Deloitte,
así como la referencia al logo y nombre de Deloitte son elementos
fundamentales que cubrir. Otros aspectos como la sobriedad visual y la
claridad son también otros elementos sugeridos dentro de esta guía.

En este sentido, el prototipo planteado implementa los aspectos
fundamentales establecidos en dicha guía, ofreciendo a los usuarios un
interfaz claro y directo, pero siempre sin desmerecer las necesidades
funcionales establecidas tanto por la entidad usuaria, como por el
equipo técnico.

**Interfaz y usabilidad**

- Diseño intuitivo, modular y adaptable, orientado a facilitar la
  visualización de grandes volúmenes de datos.

- Navegación basada en paneles y vistas contextuales, que permiten
  analizar relaciones entre direcciones, transacciones, tokens o casos.

- Interfaz responsiva, adaptada a distintos tamaños de pantalla y
  dispositivos (desktop, portátil o tablet).

- Incorporación de filtros dinámicos, menús de acción rápida.

**Arquitectura y tecnología**

- Basada en una **arquitectura web modular**, que permite su ampliación
  con nuevas funcionalidades o módulos de integración.

- Implementación de **autenticación federada (SAML / OAuth2)** y
  **control de acceso RBAC**, garantizando seguridad y cumplimiento
  normativo.

**Rendimiento y seguridad**

- Carga eficiente de datos mediante consultas asincrónicas y paginación.

- Implementación de mecanismos de cacheo y optimización de peticiones a
  fuentes externas.

- Comunicación segura mediante HTTPS/TLS y gestión cifrada de tokens
  JWT.

- Registro continuo de eventos y auditoría completa de acciones
  (creación, acceso, modificación, borrado).

**Concepto de pivoting**

Dentro de las características principales de la tecnología de
blockchain, que se ha intentado reflejar en esta solución, es la
interrelación entre los distintos elementos. Las addresses,
transacciones, bloques, etc. suelen ser elementos que se encuentran
entrelazados a través de la propia naturaleza de la tecnología
blockchain. Para cubrir ese aspecto, la solución planteada implementa el
concepto de pivoting: a través de enlaces directos, el usuario de la
plataforma puede ir navegando a través de las mismas interrelaciones
establecidas dentro de la blockchain, además de otras relaciones
funcionales proporcionadas por el prototipo. Este mecanismo facilita la
tarea de análisis y por tanto de toma de decisiones.

## Casos de uso

### Interfaz de usuario ^(ESF-0001)^

**Actores implicados**: Analistas, gestor

El sistema debe proporcionar una interfaz de usuario ágil que permita la
navegación rápida, fluida e intuitiva entre los diferentes objetos de
información y facilitar una sistemática de trabajo.

Se han definido interfaces de usuario para los distintos activos de
información de las blockchains: direcciones (addresses), bloques,
transacciones, tokens (si procede), completamente navegable: al mostrar
una address, se puede acceder a la información del bloque y desde esta
información acceder a otra address relacionado con ese bloque, tokens
relacionados con ese address, etc...

**Listado address**

![[]{#_Toc210906598 .anchor}Ilustración 57 - Listado de
addresses](media/image63.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.359722222222222in"}

**Información del address**

![[]{#_Toc210906599 .anchor}Ilustración 58 - Detalles de una
address](media/image64.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.654166666666667in"}

Detalles de las transacciones

![[]{#_Toc210906600 .anchor}Ilustración 59 - Detalle de una
transacción](media/image65.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.9430555555555555in"}

También se han definido interfaces para facilitar una sistemática de
trabajo, que se encuentran detalladas en las descripciones de los casos
de uso de alertas hallazgos, casos, informes, monitorización y actores.

### Capacidades de búsqueda ^(ESF-0002)^

**Actores implicados**: Analistas, gestor

En las distintas interfaces de la aplicación web, se pueden realizar
búsquedas en función de la vista en que se encuentre el usuario
(addresses, alertas, casos), así como también aplicar filtros.

![[]{#_Toc210906601 .anchor}Ilustración 60 - Buscador y
filtros](media/image66.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.0659722222222223in"}

### Libreta de hallazgos ^(ESF-0003)^

**Actores implicados**: Analistas

El usuario analista, dispondrá de una sección donde hacer anotaciones
para cada objeto de información en el contexto de cada caso: address,
transacción, incidente, etc.

![[]{#_Toc210906602 .anchor}Ilustración 61 - Libreta de
hallazgos](media/image67.png){alt="A white background with black text AI-generated content may be incorrect."
width="6.102083333333334in" height="0.8729166666666667in"}

### Gestor de casos ^(ESF-0004)^

**Actores implicados**: Analistas

A través de la gestión de casos, los analistas tienen la capacidad de
creación, gestión y cierre de casos. Cada caso agrupa toda la
información relevante obtenida como pueden ser addresses involucradas,
sus respectivas transacciones, documentos relevantes, anotaciones.

Cada caso, únicamente lo pueden editar, cambiar de estado y añadir
información aquellos analistas asociados al caso.

![[]{#_Toc210906603 .anchor}Ilustración 62 - Listado de
casos](media/image68.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.6472222222222221in"}

![[]{#_Toc210906604 .anchor}Ilustración 63 - Información de
casos](media/image69.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.9361111111111111in"}

![[]{#_Toc210906605 .anchor}Ilustración 64 - Árbol de
trazabilidad](media/image70.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.0930555555555554in"}

![[]{#_Toc210906606 .anchor}Ilustración 65 - Grafo de
trazabilidad](media/image71.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.8409722222222222in"}

![[]{#_Toc210906607 .anchor}Ilustración 66 - Adresses incluidas en un
caso](media/image72.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.363888888888889in"}

![[]{#_Toc210906608 .anchor}Ilustración 67 - Documentación del
caso](media/image73.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.257638888888889in"}

### Generación de informes ^(ESF-0005)\ y\ (ESF-0006)^

**Actores implicados**: Analistas

Los usuarios con rol analista, podrán realizar la generación automática
de informes a partir de la información recogida con un caso. Este
informe parte de una plantilla y se genera en formato Word, para que los
analistas puedan editarlo y añadir información de otras fuentes de
datos.

Los informes estarán accesibles desde cada caso para tenerlos
clasificados y solo tengan acceso los analistas asociados a él.

Se podrá publicar y autorizar a terceros para su acceso. Para cada
informe creado se realizará un snapshot con el objetivo de preservar la
información en un momento de tiempo concreto.

![[]{#_Toc210906609 .anchor}Ilustración 68 -- Generación de
informe](media/image74.png){alt="A screen shot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="1.2916666666666667in"}

### Detallado de tokens ERC-20 y ERC-721 ^(ESF-0018),\ (ESF-0019),\ (ESF-0020)^

**Actores implicados**: Analistas, Gestores

A través de la posibilidad del pivotado de la aplicación y la ingesta de
las blockchains de Ethereum y Polygon, los analistas y gestores, pueden
ver toda la información y metadatos de los distintos tipos de tokens ERC
-- 20 y ERC -- 721 (NFTs) con el propósito de ofrecer un mayor
conocimiento al usuario sobre las operaciones y transacciones que se
realizan.

Para la obtención de los archivos multimedia, se proporciona la url y
datos necesarios para la visualización de estos.

![[]{#_Toc210906610 .anchor}Ilustración 69 - Detalles de una address de
Ethereum](media/image75.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.463888888888889in"}

### Generación de monitorización ^(ESF-0028)^

**Actores implicados**: Analistas, Gestores

Desde la aplicación se puede crear la monitorización de una o varias
addresses, donde se puede definir unos valores para que salte una alerta
en función de los movimientos de dicha address.

La alerta generada se notificará vía e-mail a los usuarios asignados al
caso o al gestor de la address de la cual ha saltado dicha alerta.

![[]{#_Toc210906611 .anchor}Ilustración 70 -
Monitorización](media/image76.png){alt="A white and black text AI-generated content may be incorrect."
width="6.102083333333334in" height="0.9229166666666667in"}

![[]{#_Toc210906612 .anchor}Ilustración 71 - Alerta
generada](media/image77.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.488888888888889in"}

### Recomendación de acciones ^(ESF-0022)^

**Actores implicados**: Analistas, Gestores

El sistema recomienda que acciones realizar en función de la alerta
recogida sobre una address para tener un protocolo de actuación.

![[]{#_Toc210906613 .anchor}Ilustración 72 - Acciones
recomendadas](media/image77.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.488888888888889in"}

### Investigación de actores y comportamiento ^(ESF-0029)^

**Actores implicados**: Analistas, Gestores

La aplicación dispone de un módulo de análisis de actores, donde se
agrupan las direcciones que pertenecen a una misma enditad o individuo.
La asociación de direcciones manualmente o sugerencias automáticas
generadas por algoritmos de inteligencia artificial.

![[]{#_Toc210906614 .anchor}Ilustración 73 - Información de
entidades](media/image78.png){alt="A white background with black and white text AI-generated content may be incorrect."
width="6.102083333333334in" height="2.7118055555555554in"}

![[]{#_Toc210906615 .anchor}Ilustración 74 - Información de adresses de
entidades](media/image79.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.7041666666666666in"}

### Custodia de evidencias y sellado ^(ESF-0031)\ y\ (ESF-0033)^

**Actores implicados**: Analistas

A través de la aplicación, los analistas pueden generar custodia,
preservación y sellado electrónico de evidencias de los informes de los
incidentes y casos para garantizar su autenticidad, trazabilidad e
integridad durante el proceso de análisis e investigación.

Cada evidencia registrada queda asociada a un identificador único.

El sistema almacena las evidencias en un entorno seguro y controlado,
manteniendo un registro de auditoría completo.

Adicionalmente, el sistema conserva las evidencias por un periodo mínimo
de cinco años, conforme a los requisitos de custodia definidos.

Durante este periodo, las evidencias pueden ser recuperadas y
verificadas por los gestores o analistas autorizados, manteniendo
siempre la trazabilidad de su ciclo de vida.

![A logo for a company AI-generated content may be
incorrect.](media/image80.jpg){width="1.375in"
height="1.3020833333333333in"}

## Gestión de Autenticación y Autorización ^(ESF-0034)\ y\ (ESF-0037)^

### Autenticación 

Para el acceso a la aplicación se seguirán los procedimientos estándares
basados en integración mediante protocolos estándares como SAML. SAML es
un estándar de acceso seguro donde la aplicación (en el rol de service
provider) delega la responsabilidad de ejecutar la autenticación a un
tercero (identity provider). Esta segunda pieza, gestiona la identidad
de los usuarios facilitando la integración transversal de diversas
aplicaciones y permitiendo implementar lógicas de acceso o segundos
factores de validación.

![[]{#_Toc210906616 .anchor}Ilustración 75 - Diagrama funcionamiento de
autenticación](media/image81.png){alt="A diagram of a authencication for web application"
width="6.102083333333334in" height="3.4472222222222224in"}

Con esta integración la aplicación NO gestiona información sensible de
los usuarios, quedando la misma aislada del lado del gestor de
identidades. SAML es un protocolo de autenticación segura, siendo uno de
los estándares corporativos más habituales. Este sistema permite que,
dentro de la aplicación, solo sea necesario almacenar la información
mínimo de la cuenta (que en nuestro caso es el email).

### Autorización y control de accesos

Tras el proceso de autenticación en la plataforma, el sistema establece
los permisos en base al rol del usuario. El tipo de control de permisos
basado en roles (RBAC) permite establecer la visibilidad de módulos, y
acciones posibles en base al rol establecido a la cuenta. Este role se
establece desde el panel de gestión de usuarios donde, de manera
integral con el propio sistema de gestión de cuentas.

De acuerdo con las necesidades y casos de uso planteados, se han
definido los siguientes roles:

- **Administrador de la plataforma**: Con capacidades orientadas al
  soporte dentro de la propia herramienta, así como otras tareas
  administrativas como la gestión de accesos y permisos del resto de
  cuentas.

- **Administrador de entidades (Manager)**: Encargado de la gestión de
  recursos pertenecientes a su propia organización.

  - Gestión de sus clientes

  - Gestión de carteras y addresses de sus clientes.

  - Información de las addresses, si están en incidentes, están marcadas
    como sospechosas si han saltado alertas sobre ellas.

  - Pivotear entre elementos para acceder a información de las
    blockchains

  - Generación de reglas para la monitorización de addresses
    pertenecientes a sus clientes.

  - Capacidad de búsqueda.

- **Analista de seguridad:**

  - Pivotear entre elementos para acceder a cualquier información de las
    blockchains

  - Crear casos, informes y evidencias.

  - Gestión de los casos.

  - Generación de reglas para la monitorización de addresses
    relacionadas con los casos.

  - Añadir información adicional a los casos.

  - Capacidad de búsqueda.

![[]{#_Toc210906617 .anchor}Ilustración 76 -- Interfaz de usuario:
Gestión de usuarios](media/image82.png){width="6.102083333333334in"
height="2.9131944444444446in"}

Si bien, este prototipo se ha implementado de acuerdo con los casos de
uso y permisos establecidos en la sección anterior (*Casos de Uso*);
esta configuración se ha realizando a través de las facilidades
establecidas dentro de las capacidades el framework de desarrollo
empleado permite la configuración ágil de nuevos permisos y roles,
acorde a nuevas necesidades que vayan surgiendo en el futuro. Este
sistema hace uso de cadenas json para definir los nuevos elementos, así
como los roles con acceso y los permisos establecidos.

![[]{#_Toc210906618 .anchor}Ilustración 77 -- Interfaz de usuario:
Gestión de permisos](media/image83.png){width="6.102083333333334in"
height="2.9in"}

En la siguiente tabla se muestra a modo de resumen, una relación entre
las distintas funcionalidades incluidas en la aplicación, con su
correspondiente relación con las especificaciones funcionales
establecidas, y los distintos roles que pueden ejecutarlo..

+----------+----------------+---------------+---------------------------------+
| Cód.     | Título         | Roles         | Descripción                     |
|          |                | implicados    |                                 |
+==========+:===============+:==============+:================================+
| ESF-0001 | Interfaz de    | Analista de   | \- Visualizar, filtrar y        |
|          | usuario        | seguridad,    | pivotar entre datos             |
|          |                | Gestor        | relacionados (wallets, tokens,  |
|          |                |               | transacciones).                 |
|          |                |               |                                 |
|          |                |               | \- Navegar entre entidades      |
|          |                |               | conectadas dentro del modelo de |
|          |                |               | datos.                          |
|          |                |               |                                 |
|          |                |               | \- Acceder a vistas detalladas  |
|          |                |               | de cada elemento.               |
+----------+----------------+---------------+---------------------------------+
| ESF-0002 | Capacidades de | Analista de   | \- Ejecutar búsquedas avanzadas |
|          | búsqueda       | seguridad,    | por direcciones, metadatos o    |
|          |                | Gestor        | atributos.                      |
|          |                |               |                                 |
|          |                |               | \- Aplicar filtros              |
|          |                |               | personalizados y ordenación de  |
|          |                |               | resultados.                     |
|          |                |               |                                 |
|          |                |               | \- Consultar resultados en modo |
|          |                |               | síncrono o bajo demanda.        |
+----------+----------------+---------------+---------------------------------+
| ESF-0003 | Libreta de     | Analista de   | \- Registrar anotaciones y      |
|          | hallazgos      | seguridad     | observaciones asociadas a       |
|          |                |               | objetos de información          |
|          |                |               | (address, transacción,          |
|          |                |               | incidente)                      |
+----------+----------------+---------------+---------------------------------+
| ESF-0004 | Gestor de      | Analista de   | \- Crear, editar y cerrar casos |
|          | casos          | seguridad     | de investigación.               |
|          |                |               |                                 |
|          |                |               | \- Controlar el estado y        |
|          |                |               | trazabilidad del caso.          |
+----------+----------------+---------------+---------------------------------+
| ESF-0005 | Generación de  | Analista de   | \- Crear informes automáticos   |
|          | informes       | seguridad     | basados en la información de    |
|          |                |               | los casos.                      |
|          |                |               |                                 |
|          |                |               | \- Generar snapshots y          |
|          |                |               | compartir informes con          |
|          |                |               | terceros.                       |
|          |                |               |                                 |
|          |                |               | \- Editar informes de manera    |
|          |                |               | colaborativa.                   |
+----------+----------------+---------------+---------------------------------+
| ESF-0006 | Listado y      | Analista de   | \- Consultar informe generados  |
|          | visualización  | seguridad     | por casos.                      |
|          | de informes    |               |                                 |
|          |                |               | \- Filtrar, ordenar y acceder a |
|          |                |               | informes autorizados.           |
|          |                |               |                                 |
|          |                |               | \- Visualizar contenido y       |
|          |                |               | versiones históricas.           |
+----------+----------------+---------------+---------------------------------+
| ESF-0018 | Detallado de   | Analista de   | \- Mostrar información de       |
|          | tokens ERC-20  | seguridad,    | tokens fungibles vinculados a   |
|          |                | Gestor        | una dirección.                  |
|          |                |               |                                 |
|          |                |               | \- Analizar interacciones y     |
|          |                |               | balances.                       |
+----------+----------------+---------------+---------------------------------+
| ESF-0019 | Detallado de   | Analista de   | \- Mostrar metadatos y          |
|          | colecciones    | seguridad,    | atributos de tokens ERC-721 y   |
|          | NFT            | Gestor        | ERC-1155.                       |
|          |                |               |                                 |
|          |                |               | \- Relacionar NFTs con          |
|          |                |               | direcciones y transacciones.    |
+----------+----------------+---------------+---------------------------------+
| ESF-0020 | Extracción     | Analista de   | \- Recuperar urls subyacentes   |
|          | multimedia NFT | seguridad     | multimedia (imágenes, vídeos,   |
|          |                |               | metadatos).                     |
|          |                |               |                                 |
|          |                |               | \- Verificar integridad y       |
|          |                |               | fuente del contenido.           |
+----------+----------------+---------------+---------------------------------+
| ESF-0028 | Motor de       | Analista de   | \- Generar monitorización de    |
|          | reglas,        | seguridad,    | addresses sospechosas.          |
|          | monitorización | Gestor        |                                 |
|          | y alertas      |               | \- Envío y recepción de alertas |
|          |                |               | automáticas.                    |
+----------+----------------+---------------+---------------------------------+
| ESF-0029 | Investigación  | Analista de   | \- Asociar identidad a las      |
|          | de actores y   | seguridad,    | addresses                       |
|          | comportamiento | Gestor        |                                 |
+----------+----------------+---------------+---------------------------------+
| ESF-0031 | Custodia de    | Analista de   | \- Registrar y almacenar        |
|          | evidencias     | seguridad     | evidencias digitales con        |
|          |                |               | identificador único.            |
|          |                |               |                                 |
|          |                |               | \- Garantizar integridad        |
|          |                |               | mediante un id único.           |
|          |                |               |                                 |
|          |                |               | \- Mantener trazabilidad y      |
|          |                |               | acceso controlado.              |
+----------+----------------+---------------+---------------------------------+
| ESF-0033 | Módulo de      | Analista de   | \- Sellar electrónicamente      |
|          | sellado        | seguridad     | evidencias y documentos.        |
|          |                |               |                                 |
|          |                |               | \- Obtener sellos de tiempo y   |
|          |                |               | comprobantes de integridad.     |
|          |                |               |                                 |
|          |                |               | \- Validar existencia e         |
|          |                |               | inmutabilidad de la             |
|          |                |               | información.                    |
+----------+----------------+---------------+---------------------------------+
| ESF-0034 | Autenticación  | Todos los     | \- Autenticación segura         |
|          | y gestión de   | roles         | mediante SAML / OAuth.          |
|          | sesión         |               |                                 |
|          |                |               | \- Aplicación de MFA y cierre   |
|          |                |               | automático por inactividad.     |
|          |                |               |                                 |
|          |                |               | \- Generación de tokens JWT     |
|          |                |               | para acceso API.                |
+----------+----------------+---------------+---------------------------------+
| ESF-0036 | API de acceso  | Analista de   | \- Consultar y crear alertas    |
|          |                | seguridad     | mediante endpoints REST.        |
|          |                |               |                                 |
|          |                |               | \- Autenticación por token JWT  |
|          |                |               | y validación de permisos.       |
|          |                |               |                                 |
|          |                |               | \- Centralizar reglas de        |
|          |                |               | monitorización.                 |
+----------+----------------+---------------+---------------------------------+
| ESF-0037 | Gestión de     | Administrador | \- Crear y asignar roles dentro |
|          | roles y        | de la         | del modelo RBAC.                |
|          | accesos        | plataforma    |                                 |
|          |                |               | \- Revisar y auditar permisos   |
|          |                |               | activos.                        |
|          |                |               |                                 |
|          |                |               | \- Asegurar la segregación de   |
|          |                |               | funciones y el mínimo           |
|          |                |               | privilegio.                     |
+----------+----------------+---------------+---------------------------------+

: []{#_Toc210906539 .anchor}Tabla 11 - Relación funcionalidades con
roles

## API de Acceso ^(ESF-0036)^

La API de Monitorización y Alertas tiene como objetivo centralizar la
gestión de alertas generadas por el sistema y facilitar la consulta de
las reglas de monitorización configuradas.

Permite crear nuevos registros de alerta a partir de eventos detectados,
así como consultar las reglas activas que determinan cuándo y cómo deben
generarse dichos avisos.

El acceso a la API está restringido exclusivamente a un usuario
autorizado dentro del sistema.\
Para poder realizar cualquier solicitud a los servicios disponibles, el
usuario debe autenticarse previamente a través del mecanismo
establecido, obteniendo un **token JWT** (JSON Web Token) válido.

Este token actúa como credencial temporal de acceso y debe incluirse en
las cabeceras de cada petición. De esta forma, se garantiza que
únicamente las aplicaciones o usuario identificado y validado puedan
interactuar con los endpoints de la API, manteniendo la
**confidencialidad, integridad y trazabilidad** de las operaciones.

Cualquier intento de acceso sin un token válido, expirado o manipulado
será rechazado automáticamente por el sistema.

### Endpoint /getRules

Este servicio permite **consultar las reglas de monitorización activas**
en el sistema.\
Cada regla define un conjunto de condiciones o parámetros que determinan
cuándo debe generarse una alerta.

![[]{#_Toc210906619 .anchor}Ilustración 78 - Ejemplo endPoint
getRules](media/image84.png){alt="A screenshot of a computer program AI-generated content may be incorrect."
width="6.102083333333334in" height="4.591666666666667in"}

### Endpoint /create-alert

Este servicio permite la creación de una nueva alerta sobre una address,
la cual se está monitorizando ^(ESF-0028)^. Esto ocurre en el momento
que cumple los criterios establecidos por la regla de monitorización.

![[]{#_Toc210906620 .anchor}Ilustración 79 - Ejemplo endPoint creación
de
alertas](media/image85.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="4.102083333333334in"}

# MONITORIZACIÓN

## Propósito y alcance

Este apartado describe el **módulo de monitorización transversal** de la
aplicación. Dentro de las necesidades establecidas para este proyecto, y
asociado al requisito *REQ-0009 -- Gobierno de la solución,* es de vital
importancia contar con un control del estado de salud de los servidores
y los servicios que corren, así como contar con información sobre las
volumetrías ^(ENS-0005\ y\ ENS-0006)^ y PKIs relativos a los flujos
transversales de información. Estas métricas posteriormente se
utilizarán para verificar los objetivos planteados en la etapa 3 y
garantizar la cobertura de las especificaciones no funcionales del
proyecto. Este módulo compatibiliza esta tarea junto con la gestión y
almacenamiento seguro de los logs, este control permite garantizar la
trazabilidad de las acciones de manera transversal y la gestión de
trazas de auditoria ^(ENS-0004)^. El objetivo es centralizar **logs,
métricas, alarmas y paneles** usando **Amazon CloudWatch** como servicio
de observabilidad nativo de AWS, permitiendo la gestión en tiempo real
^(ENS-0002)^, asegurar la alta disponibilidad del servicio ^(ENS-0007)^
y el control de la eficiencia del sistema en su conjunto ^(ENS-0003)^.

**Amazon CloudWatch** es el servicio de monitorización de AWS que
recopila y visualiza métricas, logs y eventos en tiempo real
^(ESF-0035)^. Permite supervisar recursos de AWS, aplicaciones y
servicios personalizados para detectar problemas y optimizar el
rendimiento. Además, ofrece alarmas, tableros y automatización de
respuestas ante cambios en la infraestructura.

![[]{#_Toc210906621 .anchor}Ilustración 80 -- Alcance
Monitorización](media/image86.png){width="4.729166666666667in"
height="2.433416447944007in"}

El alcance del trabajo desarrollado en este módulo cubre los siguientes
puntos:

- **Instancias EC2** que alojan los componentes de la solución.

- **Contenedores** desplegados con **docker-compose**.

- Servicios gestionados de AWS, con foco en **Amazon Aurora
  (MySQL/PostgreSQL compatible)**.

- Ingesta de **logs** y **métricas** de aplicación, infraestructura y
  base de datos hacia **CloudWatch**.

- **Alarmas** automatizadas y **paneles** de control para operación y
  negocio

![[]{#_Toc210906622 .anchor}Ilustración 81 -- Captura Visualización de
Métricas](media/image87.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.703472222222222in"}

Los siguientes puntos de esta sección recorren los aspectos técnicos
relativos a las distintas áreas incluidas en este módulo.

## Visión general de la arquitectura

La arquitectura de monitorización se apoya en Amazon CloudWatch como
**plataforma única** para consolidar **logs, métricas, alarmas y
paneles**. Los componentes de negocio se ejecutan en **instancias EC2**
mediante **docker-compose** y consumen servicios gestionados (p. ej.,
**Aurora**). Desde el punto de vista operativo, el diseño separa
claramente el **plano de datos de observabilidad** (lo que enviamos:
logs y métricas) del **plano de control** (cómo reaccionamos: alarmas,
notificaciones y visualización). Esta separación facilita el gobierno
^(REQ-0009)^, la auditoría ^(ENS-0004)^ y el cumplimiento de los
requisitos de disponibilidad y eficiencia
^(ENS-0002,\ ENS-0003\ y\ ENS-0007)^.

**Componentes de la solución:**

**Instancias EC2 y capa de contenedores.** Las cargas de trabajo se
ejecutan en EC2 mediante **docker-compose**. Cada servicio escribe
**logs estándar** (stdout/stderr). Esta capa es el **origen** de la
mayoría de las señales operativas.

**Agentes de ingesta (CloudWatch Agent / Fluentd\|Fluent Bit).** En cada
EC2 se despliega un **CloudWatch Agent** para recopilar **métricas de
sistema** (CPU, memoria, disco, red).

Para **logs**, se utilizan tres patrones:

- **Driver awslogs** de Docker (simple y directo) para enviar los logs
  de contenedor a **CloudWatch Logs** por **Log Group**.

- **Fluentd/Fluent Bit** (opcional) cuando se necesita **parseo,
  enriquecimiento, filtrado, envío** (CloudWatch).

- **CloudWatch Agent** para recopilar ficheros de logs y enviarlos al
  CloudWatch.

**Plano de métricas (CloudWatch Metrics).** CloudWatch recibe: (1)
**métricas nativas de AWS**, como **AWS/EC2** y **AWS/RDS (Aurora)**; y
(2) **métricas personalizadas** publicadas por el **CloudWatch Agent**.
Las métricas están **etiquetadas por dimensiones** (p. ej., InstanceId,
Environment, Service), lo que permite **filtrar, agregar y alarmar** por
instancia, servicio o entorno.

**Plano de logs (CloudWatch Logs).** Los logs de aplicación e
infraestructura se organizan en **Log Groups** por **servicio/entorno**,
con **retención** y **cifrado KMS** definidos por IaC. Se consultan con
**Logs Insights** para diagnosticar incidencias, derivar **KPIs** y
alimentar **Metric Filters** cuando se requieren contadores simples (p.
ej., errores por minuto).

**Plano de control (Alarmas y notificaciones).** Sobre las métricas se
definen **alarmas** de umbral, **compuestas** (reglas lógicas entre
alarmas base) y con **Anomaly Detection** para señales estacionales. Las
acciones de alarma se orquestan mediante **Amazon SNS** (correo),
cumpliendo ENS-0002/7.

**Visualización y gobierno (Dashboards).** Los **CloudWatch Dashboards**
consolidan vistas por **infraestructura** (CPU/Mem/Disk por EC2),
**aplicación** (errores/latencias por servicio) y **negocio**
(bloques/transacciones en blockchain, correlaciones). Estas vistas
soportan el **gobierno y la auditoría** (ENS-0004) al proporcionar
trazabilidad y evidencias.

## Flujo de datos de observabilidad

**Flujos de observabilidad**: **logs**, **métricas** y **eventos/estados
de alarma** que se generan, transportan, almacenan y consumen para
operar y auditar la plataforma. Estos flujos describen **qué señal se
produce**, **dónde se origina**, **cómo viaja** (agentes/outputs),
**dónde se almacena** (sinks) y **para qué se usa** (diagnóstico, KPIs,

alarmas, paneles).

+------------+------------------+--------------+-------------+----------------+----------+---------------+
| Flujo      | Payload          | Origen       | Transporte  | Destino        | Uso      |               |
+============+==================+==============+=============+================+==========+===============+
| Logs app   | Mensajes JSON /  | Aplicaciones | awslogs     | CloudWatch     | Troubleshooting, KPIs    |
|            | texto (INFO /    |              | Fluentd     | **Logs**       | (Insights), auditoría    |
|            | ERROR, IDs de    |              |             |                |                          |
|            | correlación)     |              | CloudWatch  |                |                          |
|            |                  |              | Agente      |                |                          |
+------------+------------------+--------------+-------------+----------------+--------------------------+
| Métricas   | CPU/Mem/Disk/Net | Instancias   | CloudWatch  | CloudWatch     | Capacidad, salud,        |
| host       |                  | EC2          | **Agent**   | **Metrics**    | alarmas                  |
+------------+------------------+--------------+-------------+----------------+--------------------------+
| Aurora     | Conexiones, CPU, | Servicio AWS | Publicación | CloudWatch     | DB paneles / alertas     |
|            | lag, deadlocks   |              | nativa      | **Metrics**    |                          |
+------------+------------------+--------------+-------------+----------------+--------------------------+
| Alarmas    | Estados OK /     | Alarms       | \_          | SNS +          | Operaciones /            |
|            | ALARM /          |              |             | Dashboards     | Trazabilidad             |
|            | INSUF.\_DATA     |              |             |                |                          |
+------------+------------------+--------------+-------------+----------------+--------------------------+
| Dashboards | Widgets y        | Metrics +    | \_          | CloudWatch     | Gobierno / operación     |
|            | resultados de    | Logs         |             | **Dashboards** |                          |
|            | consultas        |              |             |                |                          |
+------------+------------------+--------------+-------------+----------------+--------------------------+

: []{#_Toc210906540 .anchor}Tabla 12 -- Matrix de cobertura
Monitorización

**Componentes del flujo**

- **Productores (origen)**: contenedores y procesos de aplicación
  (stdout/stderr), sistema operativo (CPU/Mem/Disk/Net), y servicios
  gestionados (Aurora).

- **Transporte/Agentes**: driver Docker **awslogs**, **Fluentd/Fluent
  Bit** (enriquecimiento/roteo), **CloudWatch Agent** (métricas de host,
  procstat, StatsD/collectd opcional) y la **API de CloudWatch** (para
  métricas personalizadas cuando aplique).

- **Sinks (destino)**: **CloudWatch Logs** (logs), **CloudWatch
  Metrics** (métricas), **CloudWatch Alarms** (estado), **SNS**
  (notificaciones), **CloudWatch Dashboards** (consumo/visualización).

- **Consumo**: operación, troubleshooting, cumplimiento (ENS-0004),
  gobierno (REQ-0009), y análisis (Logs Insights, métricas y paneles).

**Flujos y su contenido**

- **Logs de Aplicación**

**Qué son**: mensajes estructurados o texto libre que describen eventos
de ejecución (INFO/ERROR, trazas, IDs de correlación).\
**Origen**: cada contenedor (stdout/stderr) y ficheros específicos
(nginx, app).\
**Transporte**: **awslogs** o **Fluentd/Fluent Bit** (con parseo,
filtros, enriquecimiento).\
**Destino**: **CloudWatch Logs** (Log Groups por servicio/entorno,
retención/KMS).\
**Uso**: diagnóstico, auditoría, KPIs vía **Logs Insights** y **Metric
Filters** (p. ej., conteo de errores/minuto).

- **Métricas instancias EC2**

**Qué son**: series numéricas periódicas (CPU, memoria, disco, red).\
**Origen**: sistema operativo del host.\
**Transporte**: **CloudWatch Agent** (plugins cpu, mem, disk, net).\
**Destino**: **CloudWatch Metrics** (namespace Cripto/Infra con
dimensiones como InstanceId, Environment).

- **Métricas de servicios gestionados (Aurora)**

**Qué son**: métricas nativas publicadas por AWS (conexiones, CPU, lag,
deadlocks).\
**Origen**: **Amazon Aurora (MySQL)**.\
**Transporte**: publicación nativa de AWS (sin agente)\
**Destino**: **CloudWatch Metrics** (namespace AWS/RDS, dimensión
DBClusterIdentifier/DBInstanceIdentifier).\
**Uso**: paneles y alarmas de base de datos; soporte a ENS-0002/7 por
disponibilidad y rendimiento.

- **Estados de alarmas y notificaciones**

**Qué son**: evaluaciones de condiciones sobre métricas (umbral,
**compuestas**, **Anomaly Detection**).\
**Origen**: **CloudWatch Alarms**.\
**Transporte**: cambio de estado → **SNS** (email/Slack/PagerDuty) y
registro de eventos en CloudWatch.\
**Destino/Consumo**: equipos de operación, paneles con widgets de
estado, y trazabilidad para auditoría.

- **Paneles(Dashboards) y consultas**

**Qué son**: vistas consolidadas de métricas y resultados de **Logs
Insights** (infraestructura, aplicación, negocio).\
**Origen**: CloudWatch Metrics + queries de CloudWatch Logs Insights.\
**Destino/Consumo**: **CloudWatch Dashboards**.\
**Uso**: gobierno, operación diaria, reporting y evidencias
(ENS-0004/REQ-0009).

## Diseño lógico

El **diseño lógico** de la monitorización define **cómo se organizan y
clasifican** las señales de observabilidad (métricas, logs y alarmas)
**a nivel conceptual**, independientemente de hosts concretos o del
despliegue físico. Establece **nombres, convenciones y reglas** para que
toda la plataforma reporte y consuma señales de manera **coherente y
auditable**.

Aplica al desarrollo (como reportar logs), a operaciones (como
localizar, agrupar y reportar alertas) y a la seguridad y cumplimiento
^(ENS‑0004)(REQ‑0009)^ y a la auditoria (evidencias consistentes y
fácilmente localizables).

Con este deseño lógico se resuelve la consistencia entre
servicios/entornos aportando nombres y claves homogéneas, la
trazabilidad y el gobierno.

Las piezas clave son:

- **Namespaces (Métricas)**: agrupan **series de métricas** por
  **dominio lógico** (Infra/App/Negocio). Representan el "**contexto**"
  al que pertenecen las métricas (no existen en Logs). Ej.:
  EC2/ContainerHost, AWS/RDS, Company/App/Business.

- **Grupos de logs (CloudWatch Logs)**: agrupan **mensajes de log** por
  **servicio/entorno** y definen **retención**, **cifrado (KMS)** y
  **etiquetas**. Son el "**cajón**" de almacenamiento y búsqueda. Ej.:
  /deloitte/oba, /deloitte/flink-alert-engine.

- **Dimensiones estándar (Métricas)**: pares **clave=valor** que
  etiquetan cada punto de métrica para **segmentar y filtrar** (p.ej.,
  InstanceId, Environment, Service). Son el "**quién/dónde**" que
  permite crear **alarmas por ámbito** y **dashboards reutilizables**.

- A partir de estas piezas se especifican las **convenciones**
  (nomenclatura), **valores por defecto**, y **reglas de uso**
  (dimensiones mínimas) que se detallan en las subsecciones siguientes.

### Namespaces, grupos de logs y dimensiones

- **Namespace (Métricas)**: *contenedor lógico* en CloudWatch
  **Metrics** que agrupa series relacionadas. Aporta **orden**,
  **gobierno** y facilita **segregación** por dominio
  (Infra/App/Negocio). No existe en Logs.

- **Log Group (Logs)**: *contenedor lógico* en CloudWatch **Logs**. Cada
  grupo tiene **retención**, **cifrado** y **etiquetas** propias. Aporta
  **trazabilidad**, control de **ciclo de vida** y separación por
  **servicio/entorno**.

- **Dimensión (Métricas)**: par **clave=valor** que etiqueta cada punto
  de métrica (p. ej., InstanceId=i-\..., Environment=prd). Aporta
  **segmentación** (filtrar y agregar), reutilización de **widgets** y
  **alarmas específicas** por instancia/servicio.

**Resumen**: *Namespaces* ordenan **métricas** por dominio; *Log Groups*
ordenan **logs** por servicio/entorno; *Dimensiones* permiten
**filtrar/alertar** con precisión.

## Cloud Logs

Se utilizan diferentes métodos para enviar los logs de los diferentes
componentes a Cloud Watch.

### Driver awslogs

services:

jobmanager:

image: flink:2.0.0-java17

container_name: jobmanager

.........

logging:

driver: awslogs

options:

awslogs-region: eu-central-1

awslogs-group: /deloitte/flink-alert-engine/jobmanager

#awslogs-stream: \"{{.Name}}\"

awslogs-create-group: \"true\"

tag: \"{{.Name}}/{{.ID}}

### Sidecar Fluent Bit

**Fluente Bit Docker container**

fluentd:

image: fluentd

env_file: .env

volumes:

\- /var/log/nginx/:/var/log/nginx/

\- /var/log/vhosts/:/var/log/vhosts/

\- /mnt/efs/logs/:/mnt/efs/logs/

restart: unless-stopped

logging: \*id001

**fluent-bit.conf**

\<source\>

\@type tail

\@label \@APP

\<parse\>

\@type multiline

format_firstline /\^\\d{4}-\\d{2}-\\d{2} \\d{2}:\\d{2}:\\d{2}/

format1 /\^(?\<message\>.\*)/

\</parse\>

path /var/log/vhosts/\*\*/\*.log

pos_file /var/fluentd/APP/pos

tag \*

\</source\>

\<label \@APP\>

\<filter\>

\@type record_transformer

enable_ruby

\<record\>

hostname #{Socket.gethostname}

service \${tag_parts\[-4\]}

application \${tag_parts\[-3\]}

\</record\>

\</filter\>

\<match\>

\@type cloudwatch_logs

log_group_name /deloitte/oba

log_stream_name \${service}\_\${application}\_\${hostname}

auto_create_stream true

region eu-central-1

\<buffer hostname,service,application\>

\@include buffer.conf

path /var/fluentd/APP/buffer

\</buffer\>

\<format\>

\@type single_value

\</format\>

\</match\>

\</label\>

## Métricas

### CloudWatch Agent en instancias EC2

Archivo de configuración para capturar métricas en el Agente.

\"metrics\": {

\"namespace\": \"Cripto/Infra\",

\"append_dimensions\": {

\"InstanceId\": \"\${aws:InstanceId}\",

\"Environment\": \"prd\"

},

\"aggregation_dimensions\": \[

\[\"InstanceId\"\],

\[\"Environment\"\],

\[\]

\],

\"metrics_collected\": {

\"cpu\": {

\"measurement\": \[

\"cpu_usage_idle\",

\"cpu_usage_user\",

\"cpu_usage_system\"

\],

\"metrics_collection_interval\": 60,

\"totalcpu\": true

},

\"mem\": {

\"measurement\": \[

\"mem_used_percent\",

\"mem_available\",

\"mem_used\"

\],

\"metrics_collection_interval\": 60

},

\"disk\": {

\"resources\": \[

\"/\"

\],

\"measurement\": \[

\"used_percent\",

\"inodes_free\"

\],

\"metrics_collection_interval\": 60

},

\"net\": {

\"resources\": \[

\"eth0\"

\],

\"measurement\": \[

\"bytes_sent\",

\"bytes_recv\"

\],

\"metrics_collection_interval\": 60

}

}

### Publicación nativa en servicios AWS

El servicio **Amazon Aurora (incluido el motor MySQL)** **publica
métricas por defecto** en **CloudWatch** sin necesidad de agente. Estas
métricas se encuentran en el *namespace* **AWS/RDS**, normalmente con
dimensión **DBClusterIdentifier** (y/o DBInstanceIdentifier), y son
visibles en *CloudWatch → Metrics → AWS/RDS*. A partir de ellas se
pueden construir **dashboards** y **alarmas** directamente.

Métricas recomendadas (namespace AWS/RDS, DBClusterIdentifier como
dimensión):

- CPUUtilization, FreeableMemory, DatabaseConnections

- Deadlocks, DiskQueueDepth, FreeLocalStorage

- ReplicaLag, AuroraBinlogReplicaLag (si aplica)

- Queries, DMLThroughput, SelectThroughput (según engine)

## Alarmas

- **Umbrales** (ejemplos):

  - HTTP5xxRate \> 2% (5 min) por servicio → **ALERTA**.

  - p95LatencyMs \> SLO sostenido 10 min.

  - CPUUtilization (EC2) \> 80% durante 15 min.

  - DatabaseConnections \> 85% capacidad (Aurora).

  - Deadlocks \> 0 (2 ventanas consecutivas).

- **Anomaly Detection**: para métricas con estacionalidad (tráfico
  diario).

- **Acciones**: tópico **SNS** con integraciones (Email).

## Dashboards y observabilidad

### Dashboards de infraestructura por EC2

**Gráficas por instancia** (un widget por EC2) mostrando **CPU**,
**memoria** y **espacio en disco** capturados por CloudWatch (AWS/EC2 +
Agent):

- CPU (Average 1m) por InstanceId.

- mem_used_percent (Agent) por InstanceId.

- disk_used_percent (Agent) para el path / (y otros volúmenes si aplica)

![[]{#_Toc210906623 .anchor}Ilustración 82 -- Captura métricas
performance](media/image88.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="4.790277777777778in"}

### Dashboards de negocio (tracking de blockchains)

- Gráficas de **bloques** y **transacciones** **ingestados** por red
  (ETH, BTC, POL).

- **Reglas de correlación** aplicadas sobre transacciones (detección de
  patrones/fraude) y **alarmas generadas** (widgets de estado de alarmas
  y contadores por severidad).

- Ejemplos de KPIs:

  - Bloques/minuto y transacciones/minuto por blockchain.

  - Rules evaluadas en cada ejecución

  - Alarmas generadas en un rango de tiempo.

![[]{#_Toc210906624 .anchor}Ilustración 83 -- Captura dashboard
rendimiento](media/image89.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="2.3958333333333335in"}

# GESTION DEL SOFTWARE desarrollado 

## Introducción

El modelo DevOps se adopta en este proyecto como eje estratégico para
garantizar una gestión eficiente del ciclo de vida del software, desde
la ingesta de datos hasta la exposición de resultados en el frontal. La
solución, orientada al análisis automatizado de las blockchains de
Bitcoin, Ethereum y Polygon en busca de patrones asociados a ransomware,
requiere un enfoque técnico sólido, ágil y escalable. Dado que el
sistema se estructura en módulos especializados (ingesta, procesamiento,
machine learning, gestión de reglas y frontal), DevOps permite orquestar
y mantener una coherencia operativa entre componentes altamente
desacoplados, pero interdependientes.

![[]{#_Toc210906625 .anchor}Ilustración 84 -- Procedimiento
SSDLC](media/image90.png){width="2.9444444444444446in"
height="1.8728313648293964in"}

Azure DevOps actúa como la plataforma central de integración y
orquestación del proyecto, permitiendo una trazabilidad completa del
código fuente (principalmente en Python), la automatización de pruebas,
la construcción de artefactos y los flujos de despliegue. Como se ha
comentado con anterioridad, estos despliegues se realizan sobre
contenedores Docker, lo que facilita la portabilidad, el aislamiento y
la reproducibilidad del entorno en todas las etapas, desde el desarrollo
hasta la producción.

![[]{#_Toc210906626 .anchor}Ilustración 85 -- Captura Portal Azure
DevOps](media/image91.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="4.524305555555555in"}

La incorporación de prácticas como la Integración y Entrega Continua
(CI/CD), así como la monitorización automatizada y la infraestructura
como código, permite reducir significativamente los tiempos de entrega,
detectar errores de forma temprana y escalar de forma controlada
conforme evolucionan las necesidades del sistema. Además, el enfoque
DevOps favorece una cultura de colaboración entre desarrollo,
operaciones y ciencia de datos, alineando objetivos técnicos con los de
ciberseguridad y resiliencia del negocio.

En los siguientes epígrafes se revisarán los aspectos más generales de
la gestión de código, en relación con los repositorios existentes y la
metodología de trabajo. Luego visitaremos los procedimientos de
despliegue haciendo uso de Azure DevOps, así como los artefactos
principales del prototipo.

## Gestión del software

Este prototipo necesita del desarrollo de una serie de módulos y
utilidades propios para cubrir las necesidades expuestas en este
proyecto. En este sentido, se hace necesario disponer de una
infraestructura de repositorios de código, además de otras soluciones
estándares para la automatización de los procesos de creación del
paquete software, y posterior despliegue dentro de la infraestructura
establecida para este proyecto.

![[]{#_Toc210906627 .anchor}Ilustración 86 -- Repositorios de
código](media/image92.png){width="4.85241469816273in"
height="2.4246839457567804in"}

El equipo de desarrollo trabaja contra repositorios alojado en Azure
DevOps. Estos repositorios siguen el protocolo GIT siendo un estándar
dentro de la industria del desarrollo de soluciones de software.

Azure DevOps incluye mecanismos de gestión de identidades y control de
roles, de forma que es posible controlar los permisos y acciones
disponibles para cada usuario, así como las ramas y flujos de trabajo.
Este tipo de repositorio implementa el protocolo GIT, de forma que es
posible paralelizar el trabajo, y permite el seguimiento y control de
los cambios realizados.

Dentro del ecosistema *git*, *gitflow* es una de las metodologías de
trabajo más empleadas. Con ella se puede asegurar el correcta
coordinación y gestión del código, así como la trazabilidad y
seguimiento de los cambios introducidos por los distintos miembros del
equipo. Gitflow establece una estructura y ramas de trabajo
predefinidas, así como unos mecanismos para ir incluyendo los cambios de
código para posibilitar el trabajo coordinado del equipo, y mejorar la
productividad. Esta metodología es un estándar de facto, existiendo
bastante literatura sobre el mismo, haciendo que cualquier equipo de
desarrollo y devops pueda estar bastante familiarizado y pueda adquirir
experiencia fácilmente.

Los distintos repositorios con los que cuenta el proyecto son:

- Ingestion: Con los scripts y procedimientos requeridos para la carga
  de información de las distintas blockchains.

- IA: Incluye la información de los pipelines y procedimientos para
  lanzar la ejecución de los modelos de inteligencia artificial.

- datalake_API: Información sobre el modelo empleado dentro de la
  Datalake, así como implementación de los endpoints necesarios para
  operar sobre el mismo.

- rules_engine: Implementación del motor de reglas y generador de
  alertas.

- Enrichment: Repositorio con la lógica requerida para realizar la carga
  de información.

![[]{#_Toc210906628 .anchor}Ilustración 87 -- Captura Listado de
Repositorios Azure
DevOps](media/image93.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="3.8541666666666665in"}

## Procedimientos de despliegue

Las capacidades proporcionadas por Azure DevOps para la **gestión de
flujos de trabajo** (pipelines) entran en juego a la hora de definir los
**procedimientos de despliegue de las soluciones software** incluidos en
este prototipo. En ese sentido, se ha implementación una automatización
de procesos para realizar el empaquetado y despliegue de los distintos
componentes que componen la solución dentro de la infraestructura
establecida para el proyecto.

![[]{#_Toc210906629 .anchor}Ilustración 88 -- Procedimiento de
despliegue](media/image94.emf){width="4.84375in" height="2.40625in"}

El flujo completo se inicia cuando un desarrollador sube sus cambios de
código dentro de la rama de integración en el repositorio centralizado.
En este punto, se ha definido un pipeline que ejecuta las pruebas
unitarias, empaqueta el software, y lo despliega dentro de la
infraestructura establecida.

Con este mecanismo, además de la industrialización del flujo de trabajo,
evitando el error humano a la hora de desplegar el proyecto,
garantizamos la trazabilidad completa del flujo de verificación y
despliegue, y la identificación temprana de cualquier tipo de problema o
error.

![[]{#_Toc210906630 .anchor}Ilustración 89 -- Captura Procesos de
despliegue](media/image95.png){alt="A screenshot of a computer AI-generated content may be incorrect."
width="6.102083333333334in" height="4.094444444444444in"}

# PRÓXIMOS PASOS 

En este documento se ha expuesto la **arquitectura general y detalle
técnico implementados para cubrir el objetivo principal de este
proyecto**: crear un prototipo que tenga la capacidad de detectar
patrones asociados a casos de ransomware dentro de las blockchains en
estudio, a través del análisis de información in-chain y off-chain.

Tras la ejecución satisfactoria de los casos de prueba de la etapa 2, se
ha creado el documento ENT*-0009* - R*esultados de pruebas de etapa 2*.

En este punto, se puede confirmar que se dispone de un prototipo que
cubre las necesidades y requisitos planteados dentro del documento del
proyecto de ingeniería y que, por tanto**, satisface el propósito
establecido para este proyecto**.

Ahora, este prototipo está disponible para pasar a la **etapa 3** en la
que la correspondiente entidad usuaria podrá realizar las **pruebas
funcionales establecidas**. Los usuarios tendrán acceso a un entorno
como el descrito en este documento, en el que podrán ejecutar los flujos
de negocio y validaciones de acuerdo con el **plan de validación
establecido para la etapa 3**. Los casos de uso ahí descritos recogen,
por un lado, aspectos funcionales de la solución, verificando que cubre
las necesidades establecidas para los usuarios de la plataforma; así
como otros técnicos y relacionados con las necesidades de gestión y
procesamiento de grandes volúmenes de datos.

Esta etapa 3 servirá para verificar las capacidades del prototipo, así
como para detectar posibles aspectos de mejora que tengan que ser
corregidos o mejorados.

De manera general, aunque este prototipo se diseñó para dar respuesta a
unas necesidades muy concretas, se ha puesto de manifiesto su
**potencial** para habilitar nuevas capacidades en el análisis de
actividades maliciosas dentro de las blockchains. Entre los posibles
casos de uso destacan la **evaluación continua de la blockchain para
generar indicadores de actividad ilícita**, así como la **extracción de
métricas económicas asociadas a dichos comportamientos**, aspectos que,
si bien no forman parte del alcance inicial del proyecto, podrían ser
explorados en una evolución futura del mismo.

Adicionalmente, este trabajo abre la puerta a líneas de investigación
complementarias, como la integración de **técnicas de machine learning y
detección de anomalías** para identificar patrones emergentes, la
**correlación entre cadenas públicas y privadas** para una visión más
amplia, o el desarrollo de **dashboards dinámicos** que faciliten la
explotación de los datos por parte de analistas de ciberseguridad e
investigadores financieros. Estas posibilidades no solo ampliarían el
alcance del sistema, sino que también lo posicionarían como una
herramienta estratégica para organismos reguladores, equipos de
respuesta a incidentes y entidades interesadas en comprender y mitigar
el impacto de la actividad ilícita en el ecosistema blockchain.

# REFERENCIAS 

- <https://www.blockchain.com>

Información actualiza del estado de la blockchains, en concreto de
Bitcoin.

- <https://www.mintur.gob.es/Publicaciones/Publicacionesperiodicas/EconomiaIndustrial/RevistaEconomiaIndustrial/405/DOLADER,%20BEL%20Y%20MU%C3%91OZ.pdf>

Información general sobre el funcionamiento y características de las
blockchain

- <https://airflow.apache.org/>

*Airflow* como una de las alternativas valoradas en esta solución.

- <https://learnmeabitcoin.com/>

Información genérica sobre el funcionamiento interno, y la estructura y
metadatos relacionados con la blockchain de bitcoin.

- <https://studio.glassnode.com/metrics>

Información relativa a métricas y contadores de las distintas
blockchains.

- <https://docs.polygon.technology/pos/how-to/snapshots>

Métricas y datos técnicos de polygon

- <https://espaciomarca.es.deloitte.com/>

Guía de estilos de Deloitte (Espacio de Marca Deloitte)

## ANEXO I. HISTÓRICO DE MODIFICACIONES {#anexo-i.-histórico-de-modificaciones .Subanexo}

  -----------------------------------------------------------------------
   Versión       Fecha         Autor     Modificaciones
  ---------- ------------- ------------- --------------------------------
     1.0      08/10/2025     Deloitte    Versión inicial del documento.

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         
  -----------------------------------------------------------------------

  : []{#_Toc133437760 .anchor}Tabla 13 - Histórico de modificaciones

## ANEXO II. ENDPOINTS API DATALAKE {#anexo-ii.-endpoints-api-datalake .Subanexo}

El siguiente fichero adjunto incluye la declaración de la API (formato
openapi y pdf) de acceso al módulo de Datalake de este prototipo.

![](media/image96.emf)

El diseño y la implementación pueden ir evolucionando a medida que se
vayan implementando más casos de uso.

## ANEXO III. ENDPOINTS API FRONTEND {#anexo-iii.-endpoints-api-frontend .Subanexo}

Los siguientes ficheros adjuntos incluyen la declaración de la API
(formato openapi) que actualmente proporcionamos para integraciones de
terceros. En la sección relativa al frontal web, se ha incluido
documentación adicional sobre su usabilidad y casos de uso.

![](media/image97.emf)![](media/image98.emf)

El diseño y la implementación pueden ir evolucionando a medida que se
vayan implementando más casos de uso o requisitos de cliente.

## ANEXO IV. RESULTADOS PRUEBAS DE VALIDACION {#anexo-iv.-resultados-pruebas-de-validacion .Subanexo}

En el siguiente documento quedan reflejados los resultados de las
pruebas de evaluación de los modelos ejecutados en la fase de
entrenamiento. Esta información se encuentra dentro de la sección 3.7.3
de este documento, donde se incluyen los resultados finales y las
conclusiones y se hace referencia a este documento.

![](media/image99.emf)
