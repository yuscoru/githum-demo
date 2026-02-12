PKIs, Monitorización y Rendimiento

R004_TRAC

# **ÍNDICE** {#índice .TOC-Heading}

[ÍNDICE DE TABLAS [2](#_Toc408386635)](#_Toc408386635)

[1 INTRODUCCIÓN [3](#introducción)](#introducción)

[1.1 Propósito [3](#propósito)](#propósito)

[1.2 Audiencia [3](#audiencia)](#audiencia)

[1.3 Ámbito [3](#ámbito)](#ámbito)

[1.4 Descripción de la Solución
[4](#descripción-de-la-solución)](#descripción-de-la-solución)

[1.5 Procedimiento de trabajo
[5](#procedimiento-de-trabajo)](#procedimiento-de-trabajo)

[2 ESPECIFICACIONES TRATADAS
[6](#especificaciones-tratadas)](#especificaciones-tratadas)

[[3]{.mark} [DESCRIPCION SECCIONES DEL DOCUMENTO (SECCION A
ELIMINAR)]{.mark}
[7](#descripcion-secciones-del-documento-seccion-a-eliminar)](#descripcion-secciones-del-documento-seccion-a-eliminar)

[4 INGESTA DE INFORMACIÓN [CITRA]{.mark}
[9](#modulo-ingesta-de-información-citra)](#modulo-ingesta-de-información-citra)

[4.1 Ingesta blockchain de Bitcoin
[9](#ingesta-blockchain-de-bitcoin)](#ingesta-blockchain-de-bitcoin)

[4.2 Ingesta blockchain de Ethereum [CITRA]{.mark}
[11](#ingesta-blockchain-de-ethereum-citra)](#ingesta-blockchain-de-ethereum-citra)

[4.3 Ingesta blockchain de Polygon [CITRA]{.mark}
[11](#ingesta-blockchain-de-polygon-citra)](#ingesta-blockchain-de-polygon-citra)

[5 DATALAKE [12](#_Toc207872757)](#_Toc207872757)

[5.1 PostgreeSQL [CITRA]{.mark}
[12](#postgresql-citra)](#postgresql-citra)

[5.2 Neo4j [ECC]{.mark} [12](#neo4j-ecc)](#neo4j-ecc)

[5.3 API [CITRA]{.mark} [12](#api-citra)](#api-citra)

[6 ENRIQUECIMIENTO DE INFORMACIÓN [ECC]{.mark}
[13](#enriquecimiento-de-información-ecc)](#enriquecimiento-de-información-ecc)

[7 MODULO DE INTELIGENCIA ARTIFICIAL [ECC]{.mark}
[15](#modulo-de-inteligencia-artificial-ecc)](#modulo-de-inteligencia-artificial-ecc)

[7.1 Subproceso de queries
[15](#subproceso-de-queries)](#subproceso-de-queries)

[7.2 Subproceso de ejecución de predicciones
[16](#subproceso-de-ejecución-de-predicciones)](#subproceso-de-ejecución-de-predicciones)

[8 Gestor de Eventos Y MOTOR DE REGLAS [ECC]{.mark}
[19](#modulo-gestor-de-eventos-ecc)](#modulo-gestor-de-eventos-ecc)

[8.1 Flujos de entrada de información
[19](#flujos-de-entrada-de-información)](#flujos-de-entrada-de-información)

[8.1.1 Gestión de eventos de transacciones
[22](#gestión-de-eventos-de-transacciones)](#gestión-de-eventos-de-transacciones)

[8.1.2 Gestión de eventos de predicciones
[22](#gestión-de-eventos-de-predicciones)](#gestión-de-eventos-de-predicciones)

[9 FRONTAL WEB [CITRA]{.mark}
[24](#modulo-frontal-web-citra)](#modulo-frontal-web-citra)

[10 Próximos Pasos [25](#próximos-pasos)](#próximos-pasos)

[11 REFERENCIAS [26](#referencias)](#referencias)

[ANEXO I: HISTÓRICO DE MODIFICACIONES
[27](#anexo-i-histórico-de-modificaciones)](#anexo-i-histórico-de-modificaciones)

[ANEXO II: PKIs [TODOS]{.mark}
[28](#anexo-ii-pkis-todos)](#anexo-ii-pkis-todos)

[]{#_Toc408386635 .anchor}ÍNDICE DE TABLAS

[Tabla 1 -- Audiencia [3](#_Toc204167270)](#_Toc204167270)

[Tabla 1 - Histórico de modificaciones
[27](#_Toc133437760)](#_Toc133437760)

ÍNDICE DE ILUSTRACIONES

[Ilustración 1 -- Diagrama conceptual del prototipo
[5](#_Toc207873321)](#_Toc207873321)

[Ilustración 1 -- Diagrama funcional ingesta desde blockchains
[10](#_Toc207873322)](#_Toc207873322)

[Ilustración 1 -- Métrica rendimiento CPU
[11](#_Toc207873323)](#_Toc207873323)

[Ilustración 1 -- Métrica rendimiento Red de entrada
[11](#_Toc207873324)](#_Toc207873324)

[Ilustración 1 -- Métrica rendimiento Red de salida
[12](#_Toc207873325)](#_Toc207873325)

[Ilustración 1 -- Diagrama funcional Datalake
[13](#_Toc207873326)](#_Toc207873326)

[Ilustración 1 -- Diagrama funcional enriquecimiento
[14](#_Toc207873327)](#_Toc207873327)

[Ilustración 1 -- Métrica rendimiento CPU (1)
[15](#_Toc207873328)](#_Toc207873328)

[Ilustración 1 -- Métrica rendimiento CPU (2)
[15](#_Toc207873329)](#_Toc207873329)

[Ilustración 1 -- Métrica rendimiento CPU
[17](#_Toc207873330)](#_Toc207873330)

[Ilustración 1 -- Métrica rendimiento tiempo de ejecución
[17](#_Toc207873331)](#_Toc207873331)

[Ilustración 1 -- Métrica rendimiento Red entrada
[18](#_Toc207873332)](#_Toc207873332)

[Ilustración 1 -- Métrica rendimiento Red salida
[18](#_Toc207873333)](#_Toc207873333)

[Ilustración 1 -- Diagrama funcional gestion de eventos
[20](#_Toc207873334)](#_Toc207873334)

[Ilustración 1 -- Diagrama flujo interno gestor de reglas
[21](#_Toc207873335)](#_Toc207873335)

[Ilustración 1 -- Métrica rendimiento CPU (1)
[22](#_Toc207873336)](#_Toc207873336)

[Ilustración 1 -- Métrica rendimiento CPU (2)
[22](#_Toc207873337)](#_Toc207873337)

[Ilustración 1 -- PKIs rendimiento gestor de eventos (1)
[23](#_Toc207873338)](#_Toc207873338)

[Ilustración 1 -- PKIs rendimiento gestor de eventos (2)
[24](#_Toc207873339)](#_Toc207873339)

# INTRODUCCIÓN

## Propósito

El propósito de este documento es el de recoger el detalle técnico de
los distintos análisis de rendimiento efectuados sobre los módulos y
componentes del prototipo de acuerdo con el diseño establecido dentro
del documento de Diseño Técnico.

El fin de este documento es doble: por un lado, el de garantizar y
confirmar el cumplimiento de los requisitos funcionales establecidos
dentro de la documentación de arquitectura del proyecto, sobre todo
aquellos asociados a las necesidades de tiempo real ^(REQ-0005)^; por el
otro, la de evaluar las capacidades volumétricas del prototipo, de forma
que se disponga de una visión precisa de la capacidad real del sistema,
en la medida que puede dar información fiable para evaluar la eficiencia
^(ESN-0003)^ y rendimiento del sistema ^(ESN-0002)^, escalabilidad
^(ESN-0001)^ y monitorización ^(ESN-0005)^, así como ayudar en la
evolución futura del sistema, ya sea incrementando sus capacidades.

## Audiencia

La table siguiente proporciona información detallada sobre las
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

  : []{#_Toc204167270 .anchor}Tabla 1 -- Audiencia

## Ámbito

El proyecto responde al reto "Seguimiento de transacciones vinculadas
con ransomware y otras campañas" perteneciente a la tercera convocatoria
de la Iniciativa estratégica de Compra Pública de Innovación convocada
por el Instituto Nacional de Ciberseguridad (INCIBE), con el objetivo de
impulsar la I+D+i y la creación de productos y soluciones en el ámbito
de la ciberseguridad.

Ciberdelitos como el ransomware mueven anualmente casi 600 millones de
dólares en pagos, lo que hace que organizaciones de seguridad como el
FBI, NSA, FinCEN o Europol generen acciones para el análisis,
seguimiento, detección y atribución de las transacciones vinculadas a
este tipo de ataques. Las formas en las que los actores malintencionados
o cibercriminales atacan a los sistemas están siendo cada vez más
sofisticadas y con ello los flujos en los que tratan de esconder los
pagos recibidos por estas acciones. Es por ello por lo que este reto
busca dar solución a los problemas actuales y futuros de trazabilidad,
detección y atribución de transacciones debidas a campañas originadas
por el cibercrimen.

## Descripción de la Solución

El objeto del proyecto es el **desarrollo de soluciones que permitan el
seguimiento y detección de transacciones con criptoactivos vinculados
con actividades ilícitas** o incidentes de seguridad **a partir de
técnicas y algoritmos de inteligencia artificial**. De manera resumida,
para alcanzar este objetivo, este prototipo realiza la carga de
información tangible a partir de datos procedentes de las blockchains
incluidas en este proyecto, y datos off-chain procedentes de diversas
fuentes. Esta información, pasa por una serie de componentes para su
procesado y gestión, de forma que luego pueda ser usado por los módulos
de inteligencia artificial y gestión de eventos para, finalmente, crear
las correspondientes alertas asociados a los indicios identificados. El
detalle funcional y la información sobre los distintos flujos de datos
se encuentra dentro del documento de Arquitectura del prototipo.

![[]{#_Toc207873321 .anchor}Ilustración 1 -- Diagrama conceptual del
prototipo](media/image5.png){width="6.102083333333334in"
height="3.1835181539807524in"}

Dentro de este documento se recogen los resultados obtenidos tras
realizar algunos análisis relativos al rendimiento de los puntos más
tensionados y de mayor criticidad dentro de la solución propuesta. Como
se ha comentado en el Documento de Arquitectura, uno de los puntos más
críticos es la alta volumetría de información que tiene que ser
procesada. Dentro de los propios requisitos y necesidades planteadas en
el documento de proyecto de ingeniería, ya se había recogido en varias
ocasiones la necesidad de evaluar las capacidades, garantizando en un
futuro entorno productivo, la aplicación pueda cumplir con las
necesidades planteadas.

El objetivo establecido para este proyecto es el de procesar 3 de las
blockchains más relevantes dentro del ecosistema cripto. Estas
blockchain presentan una gran volumetría de información que tiene que
ser procesada por el resto de los componentes de la solución. Este
estrés, tiene que ser medido y analizado, de forma que podamos
garantizar la correcta sincronía y comunicación de los distintos
elementos, de la manera más eficiente.

## Procedimiento de trabajo

Dentro del documento de arquitectura se han descrito los distintos
componentes, así como los flujos de datos existentes en la solución.
Este documento utiliza esta misma definición, facilitando al lector el
seguimiento de los aspectos y flujos funcionales expuestos al análisis.
Para cada uno de estos flujos, se establecerán los puntos críticos de
análisis, estableciendo en cada caso los procedimientos y elementos a
monitorizar. Posteriormente se establecerán los distintos escenarios y
condiciones, así como los rangos en modo tabla de valores dependiendo de
lo esperado.

Finalmente se recogen las recomendaciones de arquitectura y
configuración de acuerdo con los aspectos de comportamiento observados
durante las pruebas ejecutadas durante la etapa 2 del proyecto. Estas
recomendaciones permitirán configurar el entorno sobre el que se tendrán
que ejecutar las pruebas de verificación del prototipo durante de etapa
3.

Durante la etapa 3 del proyecto, se seguirá monitorizando el entorno, de
forma que podamos obtener una comparativa con los números expuestos en
este documento, y así poder perfilar las necesidades técnicas y de
configuración de un posible entorno productivo.

# ESPECIFICACIONES TRATADAS

En este documento se tratarán aspectos relacionados con los siguientes
puntos recogidos dentro del documento del proyecto de ingeniería
presentado en la etapa 1.

  -----------------------------------------------------------------------
  **Código**     **Título**
  -------------- --------------------------------------------------------
  REQ-0005       Monitorización Continua

  ESN-0001       Escalabilidad

  ESN-0002       Tiempo Real

  ESN-0003       Eficiencia

  ESN-0005       Monitorización del sistema
  -----------------------------------------------------------------------

  : Tabla 2 -- Aspectos funcionales relacionados

# [DESCRIPCION SECCIONES DEL DOCUMENTO (SECCION A ELIMINAR)]{.mark}

[Aspectos a tener en cuenta para cualquier apartado de este
informe:]{.mark}

**[1. Resumen Ejecutivo]{.mark}**

- **[Objetivo del análisis]{.mark}**

- [Breve descripción del elemento bajo análisis (tipo, plataforma,
  usuarios)]{.mark}

- [Principales hallazgos]{.mark}

- [Conclusiones clave y recomendaciones generales]{.mark}

**[2. Contexto y Alcance]{.mark}**

- [Justificación del análisis (por qué se realiza)]{.mark}

- [Alcance del estudio (módulos o funcionalidades analizadas)]{.mark}

- [Limitaciones (ej. entorno de pruebas, datos simulados, etc.)]{.mark}

**[3. Entorno de Pruebas]{.mark}**

- [Descripción de la infraestructura:]{.mark}

  - [Hardware (CPU, RAM, etc.)]{.mark}

  - [Software (SO, versión de la app, DB, etc.)]{.mark}

  - [Red (latencia, ancho de banda)]{.mark}

- [Herramientas utilizadas:]{.mark}

  - [Ej: JMeter, New Relic, Lighthouse, etc.]{.mark}

- [Configuraciones relevantes (caches, concurrencia, etc.)]{.mark}

**[4. Metodología]{.mark}**

- [Tipo de pruebas realizadas:]{.mark}

  - [**Carga**: Evaluar respuesta bajo número creciente de
    usuarios]{.mark}

  - [**Estrés**: Probar límites del sistema]{.mark}

  - [**Duración (soak)**: Estabilidad a largo plazo]{.mark}

  - [**Rendimiento puntual (profiling)**: Análisis detallado de
    funciones/código]{.mark}

- [Casos de prueba usados]{.mark}

- [Métricas recolectadas: tiempo de respuesta, throughput, uso de CPU,
  memoria, etc.]{.mark}

**[5. Resultados]{.mark}**

- [Presentación clara de los datos:]{.mark}

  - [Tablas y gráficos por cada métrica relevante]{.mark}

- [Comparativas (antes vs. después de cambios, vs. umbrales
  deseados)]{.mark}

- [Comportamientos anómalos identificados]{.mark}

- [Cuellos de botella detectados]{.mark}

**[6. Análisis]{.mark}**

- [Interpretación técnica de los resultados]{.mark}

- [Posibles causas de problemas de rendimiento]{.mark}

- [Impacto de cada problema en la experiencia de usuario o
  negocio]{.mark}

**[7. Recomendaciones]{.mark}**

- [Soluciones sugeridas por cada problema identificado]{.mark}

  - [Ej: optimizar consultas SQL, uso de CDN, refactorización de código,
    escalado horizontal]{.mark}

- [Priorización de acciones (urgente/importante)]{.mark}

- [Posibles riesgos o impacto de las soluciones]{.mark}

**[8. Conclusiones]{.mark}**

- [Resumen de la situación general del rendimiento]{.mark}

- [Valoración del cumplimiento de objetivos de rendimiento]{.mark}

- [Próximos pasos propuestos]{.mark}

**[9. Anexos]{.mark}**

- [Logs detallados]{.mark}

- [Scripts de prueba]{.mark}

- [Configuración de herramientas]{.mark}

- [Código relevante (si aplica)]{.mark}

# MODULO INGESTA DE INFORMACIÓN [CITRA]{.mark}

La ingesta corresponde con la carga de información procedente de las
distintas blockchains establecidas en este proyecto.

![[]{#_Toc207873322 .anchor}Ilustración 2 -- Diagrama funcional ingesta
desde blockchains](media/image6.png){width="5.416666666666667in"
height="3.0585804899387576in"}

- **Contexto y Alcance**

El módulo de ingesta es el encargado de cargar los datos procedentes de
las blockchains dentro del sistema. Su monitorización y control de
rendimiento es muy importante para garantizar la sincronía y el perfecto
funcionamiento del resto de componentes que conforman el sistema.

**Este estudio se centrará en evaluar las capacidades de ingesta y
procesamiento, verificando que no existen cuellos de botella o problemas
de coordinación con el resto de los módulos y componentes de la
solución**.

El estudio se ha realizado a partir de la configuración y estado actual
de las blockchains. Cambios en los algoritmos o la propia naturaleza de
estas blockchains, pueden alterar los volúmenes de carga. Esto puede
provocar que los resultados aquí mostrados tengan que se reconsiderados.

## Ingesta blockchain de Bitcoin

**Características técnicas:**

- Servidor AWS EC2 c6a.xlarge (4 vCPUs, 8GB)

- Sistema Operation Ubuntu 22.04

- Cliente Bitcoin: Bitcoin Core

**Procedimiento de Análisis**

En unas condiciones regulares de carga de la blockchain, se considera un
uso de red y CPUs de acuerdo con la siguiente tabla.

  ---------------------------------------------------
           Métrica           Valor
  -------------------------- ------------------------
          Network In         250KB -- 4MB (por hora)

         Network Out         512KB -- 8MB (por hora)

    Bloques procesados por   4 - 10 (por hora)
             hora            

    Transacciones por hora   6,000 -- 24,000 (por
                             hora)

           Uso CPU           5 - 30% (4 CPUs)
  ---------------------------------------------------

  : Tabla 2 -- Métricas y PKIs de rendimiento espeardo

**Resultado obtenido**

CPU:

![[]{#_Toc207873323 .anchor}Ilustración 3 -- Métrica rendimiento
CPU](media/image7.png){width="6.102083333333334in"
height="2.3722222222222222in"}

Network In:

![[]{#_Toc207873324 .anchor}Ilustración 4 -- Métrica rendimiento Red de
entrada](media/image8.png){width="6.102083333333334in"
height="2.2756944444444445in"}

Network Out:

![[]{#_Toc207873325 .anchor}Ilustración 5 -- Métrica rendimiento Red de
salida](media/image9.png){width="6.102083333333334in"
height="2.3097222222222222in"}

Bloques por unidad de tiempo:

![Ilustración 6 - Bloques por unidad de
tiempo](media/image10.png){width="6.102083333333334in"
height="2.678472222222222in"}

**Análisis de los resultados**

Los parámetros de comportamiento del ingestador de Bitcoin se encuentran
dentro de los valores normales establecidos dentro del procedimiento de
análisis. En este sentido, y bajo las condiciones de los experimentos
realizados, no se observa un riesgo o problema latente de rendimiento en
este submódulo que pueda afectar al comportamiento global del sistema.

**Recomendaciones**

Las recomendaciones planteadas son generales:

- Monitorizar las principales características del servicio (CPU y carga
  de red) para verificar que las gráficas siguen mostrando el mismo
  comportamiento que el observado durante este experimento.

- Establecer en un entorno productivo de alertas de infraestructura
  cuando los valores caigan o superen los valores mínimo y máximo
  identificados.

## Ingesta blockchain de Ethereum [CITRA]{.mark}

**Características técnicas:**

- Servidor AWS EC2 c6a.xlarge (4 vCPUs, 8GB)

- Sistema Operation Ubuntu 22.04

- Nodo Ethereum: Reth (Cliente Ejecución) y Nimbus (Cliente Consenso)

**Procedimiento de Análisis**

## Ingesta blockchain de Polygon [CITRA]{.mark}

[]{#_Toc207872757 .anchor}**Características técnicas:**

- Servidor AWS EC2 c6a.xlarge (4 vCPUs, 8GB)

- Sistema Operation Ubuntu 22.04

- Proveedor Polygon: API Alchemy

**Procedimiento de Análisis**

El método de análisis será la monitorización de logs para hacer un
seguimiento del correcto devenir del proceso de ingesta en Polygon. Para
ello se utilizan distintos métodos:

- Análisis de media de bloques procesados al día

![](media/image11.png){width="6.102083333333334in"
height="0.2659722222222222in"}

- Revisión de errores mediante expresiones regulares: mediante comandos
  de expresiones regulares como "grep" se comprueba para el fichero
  actual de logs si hay errores. En caso positivo, se realizará un
  análisis de los propios logs y del código para su arreglo.

![](media/image12.png){width="6.102083333333334in" height="0.30625in"}

# CAPACIDADES DE DATALAKE

El datalake es el componente encargado de almacenar y proveer los datos
almacenados en esta solución.

![[]{#_Toc207873326 .anchor}Ilustración 7 -- Diagrama funcional
Datalake](media/image13.png){width="3.095833333333333in"
height="1.9020570866141733in"}

El datalake se compone principalmente de dos tecnologías: bases de datos
PostgreSQL y Neo4j. Como se ha explicado en el documento de
arquitectura, cada tipo de almacenamiento es usado en condiciones
diferentes. [(Véase el punto XXX del documento de Diseño para más
detalle).]{.mark}

- **Contexto y Alcance**

Es primordial contar con evaluaciones técnicas de las capacidades y el
rendimiento de las dos tecnologías de almacenamiento que se van a
emplear para este proyecto.

Este estudio se centrará en evaluar tres aspectos diferentes de este
módulo:

- Capacidad y límites relativos a la carga de información

- Capacidades físicas de almacenamiento

- Límites de la API en relación con las capacidades de recuperación de
  información almacenada dentro de este datalake.

## PostgreSQL [CITRA]{.mark}

La base de datos es la pieza principal para el almacenamiento y la
gestión de los datos de las distintas blockchains. Se ha elegido este
gestor a diferencia de otras tecnologías como MySQL o MariaDB por estos
dos motivos principales:

- Código abierto

- Gran rendimiento con grandes volúmenes de datos

El principal reto que se afronta al indexar tres blockchains distintas
es el de gestionar de forma eficiente y rápida grandes volúmenes de
datos. Es por ello que un gestor de base de datos que premie el acceso
rápido a la información y también la obtención veloz será una prioridad.

Con este objetivo en mente, el principal gestor para bases de datos
centralizadas es Postgres por los siguientes motivos:

- Índices: permite gran personalización del sistema de indexado de
  tablas de forma que la obtención de los datos sea de la forma más
  rápida posible.

- Volcado masivo: la existencia de directivas como COPY, únicas en este
  gestor y especializadas en inserción de archivos grandes a base de
  datos hace de Postgres un gran aliado a la hora de realizar
  operaciones de escritura masiva de forma recurrente.

- Multiconcurrencia: Postgres permite una mejor concurrencia en la que
  varios procesos acceden a los datos sin que ello suponga violaciones a
  la integridad de los datos o problemas de bloqueos.

Por estos motivos, se ha elegido a Postgres como gestor de base de datos
principal. Cada blockchain tendrá su base de datos dedicada para
almacenamiento de lo que se considere necesario, desde datos de la
blockchain en sí a datos relacionados con tokens fungibles, NFTs y Smart
Contracts.

## Neo4j [ECC]{.mark}

## API [CITRA]{.mark}

# ENRIQUECIMIENTO DE INFORMACIÓN [ECC]{.mark}

Este sistema permite el enriquecimiento de información desde fuentes
externas asociada a ransomware dentro de la blockchain.

La orquestación y automatización de flujos de trabajo y ETL se hace a
través de Apache Airflow. Se trata de una plataforma open source para
programar, monitorizar y gestionar flujos de trabajo a través de una
interfaz declarativa basada en Python.

Dentro de las necesidades establecidas para este módulo está la de
establecer mecanismos para la ingesta de información de fuentes de
diversa naturaleza, así como su procesamiento y alojamiento dentro del
Datalake a través de los mecanismos que se han establecido.

Por otro lado, en la capa de persistencia reside Neo4J, la cual es una
base de datos basada en grafos que permite el seguimiento y relación de
los distintos nodos utilizados (Addresses, Transacciones, Tools, Agents,
etc).

![[]{#_Toc207873327 .anchor}Ilustración 8 -- Diagrama funcional
enriquecimiento](media/image14.png){width="5.576080489938757in"
height="2.947826990376203in"}

**Características técnicas:**

- Servidor AWS EC2 m6a.xlarge (4 vCPUs, 16GB)

- Sistema Operation Ubuntu 22.04

- Apache Airflow 2.9.1

- Neo4J latest

- Docker

**Procedimiento de Análisis**

Es importante llevar un control y monitorización de las métricas de uso
de la propia instancia y resultados obtenidos por los procesos de
Airflow y Neo4J. Ya que se trata de una fase fundamental para el flujo
de trabajo del resto del servicio.

A partir de un análisis realizado con una carga de trabajo habitual,
usando una instancia del tipo c6a.2xlarge, se ha visto que el uso de
recursos estaba por debajo del 30%.

Lo cual parece indicar que se tiene una instancia sobredimensionada y se
está pagando un coste mayor al necesario.

Se ha decidido optar por una instancia de tipo general m6a.xlarge, lo
que supone un ahorro de un 40% aproximadamente y mantiene todos los
servicios desplegados en funcionamiento correcto.

Aquí se expone la monitorización sobre la instancia sobredimensionada
c6a.2xlarge:

![[]{#_Toc207873328 .anchor}Ilustración 9 -- Métrica rendimiento CPU
(1)](media/image15.jpeg){width="6.102083333333334in"
height="0.8284722222222223in"}

Y aquí la instancia actual más ajustada a su uso habitual:

![[]{#_Toc207873329 .anchor}Ilustración 10 -- Métrica rendimiento CPU
(2)](media/image16.png){width="6.102083333333334in"
height="1.2881944444444444in"}

Como se puede apreciar, con esta nueva instancia los recursos oscilan
entre un 30-60%, pasando de un coste por hora de 0,35€/h a 0,20€/hora
aprox.

**Recomendaciones**

Las recomendaciones planteadas son las siguientes:

- Monitorizar las principales características del servicio (CPU y RAM)
  para verificar que las gráficas siguen mostrando el mismo
  comportamiento que el observado.

- Establecer alarmas si el uso de CPU, RAM o espacio en disco supera los
  máximos establecidos, que deberían ser el 85% aproximadamente.

- Monitorizar las métricas de Airflow y Neo4J

- Migración hacia servicios nativos de AWS, lo cual aportará un mayor
  control, backups automáticos, escalado, alta disponibilidad y mayor
  seguridad.

# MODULO DE INTELIGENCIA ARTIFICIAL [ECC]{.mark}

Proceso de ejecución continua de predicción de peligrosidad de carteras:

**Contexto y Alcance**

Dentro de los procesos principales en este prototipo se encuentra el
*Proceso de ejecución continua de predicción de peligrosidad de
carteras*. Este sistema se encarga de procesar la información que se va
publicando en el datalake, y realizar una evaluación del riesgo asociado
a los distintos elementos, de acuerdo con los procesos de entrenamiento
ejecutados en fases anteriores de este proyecto. Este proceso se
encuentra referenciado en el documento de arquitectura como el
**[Pipeline ETL de predicciones]{.mark}**

Durante estas pruebas se evaluará el comportamiento real de este
sistema, de acuerdo con las métricas habituales de consumo de recursos
de los sistemas en los que se va a ejecutar.

La ejecución se ha realizado en base a la infraestructura establecida
para este proceso, proporcionándonos una visión lo más realista posible
de su rendimiento y eficiencia. Dependiendo de los resultados obtenidos
podrá haber recomendaciones sobre la propia infraestructura o elementos
relacionados.

La ejecución de estas pruebas, y sus métricas las dividiremos en dos
secciones: Por un lado, tenemos el proceso encargado de extra la
información de la base de datos (el cual provoca un gran estrés sobre la
propia base de datos sobre la que se está cargando la información); por
el otro tenemos el proceso encargado de generar las estructuras
intermedias y los datasets requeridos por el sistema de predicciones.

## Subproceso de queries 

**Rango de bloques descargados\**
 Desde el bloque 769 700 (2022‑12‑31 11:21:17 GMT+1)\
 Hasta el bloque 819 700 (2023‑12‑04 07:54:28 GMT+1)\
 → 50 000 bloques en total\
**Volumen de datos\**
 84 GB en CSVs (batches de descarga)\
 11 GB en Parquet (resultados de proceso)\
**Tiempos** (se hizo en 2 descargas)\
Descarga  1: (769 700→779 700): 08:02→13:14 = 5 h 12 min\
Descarga 2: (779 800→819 700): 20:50→17:46 (+1 día) = 20 h 56 min\
Total descarga: 26 h 08 min (1 día, 2 h 08 min)\
**Procesado**\
De la descarga 1: 14:28→14:36 = 0 h 08 min\
De la descarga 2: 19:10→21:35 = 2 h 25 min\
Total procesado: 2 h 33 min

## Subproceso de ejecución de predicciones

**Características técnicas:**

- Servidor AWS EC2 t3a.xlarge (2 vCPUs, 4GB)

- Sistema Operation Ubuntu 22.04

- Este sistema se encuentra "dockerizado". Su ejecución se ha realizado
  dentro de un contenedor. En esa misma infraestructura se están
  ejecutando otros procesos de acuerdo con la propia documentación de
  arquitectura de la solución.

**Resultado obtenido**

- Consumo de CPU

  - Máximo: 25% (1 vCPU al 100%)

![[]{#_Toc207873330 .anchor}Ilustración 11 -- Métrica rendimiento
CPU](media/image17.png){width="6.102083333333334in"
height="1.7881944444444444in"}

- Duración del proceso:

  - Mínimo: 23 minutos

  - Máximo: 40 minutos

  - Media: 25 minutos

![[]{#_Toc207873331 .anchor}Ilustración 12 -- Métrica rendimiento tiempo
de ejecución](media/image18.png){width="6.102083333333334in"
height="2.448611111111111in"}

- Network In:

  - Max: 35 Mb

![[]{#_Toc207873332 .anchor}Ilustración 13 -- Métrica rendimiento Red
entrada](media/image19.png){width="6.102083333333334in"
height="1.7784722222222222in"}

- Network Out:

  - Max: 10Mb

![[]{#_Toc207873333 .anchor}Ilustración 14 -- Métrica rendimiento Red
salida](media/image20.png){width="6.102083333333334in"
height="1.773611111111111in"}

- Consumo de Disco

  - 500 Mb por ejecución

**Análisis de los resultados**

Los valores observados relacionados con el comportamiento del proceso de
cómputo de la predicción están dentro de lo esperado.

Quedaría pendiente evaluar el consumo de memoria, de acuerdo con las
necesidades del proceso. En todo caso este cálculo no es directo ya que
este sistema se encuentra desplegado en infraestructura junto con otros
procesos.

**Observamos que, desde que una transacción es cargada en el datalake
por el sistema de ingesta, en unos 30 minutos de media es posible contar
con una estimación automática de su riesgo.** Esta evaluación del riesgo
luego se transmite al sistema de gestor de eventos que, dependiendo de
la propia lógica de negocio establecida, genera las pertinentes reglas
para proceder a su gestión en el frontal web.

Los tiempos requeridos por el pipeline (recolección de información,
procesado y ejecución) permiten una programación horaria de este flujo.
Ofreciendo una respuesta temprana una vez identificada la actividad
sospechosa de acuerdo con los patrones establecidos.

**Recomendaciones**

Debido a la propia evolución de la blockchain, es necesario repetir
estas métricas con cierta regularidad de forma que nos permita revisar
la evolución del sistema.

Dentro del roadmap futuro de este proyecto, se debería de hacer una
refactorización de la lógica para optimizar los recursos. Actualmente
este sistema consume el 100% de una única CPU. Si bien esto permite su
despliegue en un sistema donde estén corriendo otros procesos, se
podrían buscar alternativas para paralelizar actividades internas y
reducir el tiempo de cómputo.

# MODULO Gestor de Eventos [ECC]{.mark}

Este subsistema es el encargado de transformar los datos y flujos de
información que se generan en el backoffice de la solución en alertas.
Esta transformación se realiza a través de la evaluación de una serie de
reglas de negocio.

Las alertas generadas posteriormente son enviadas al frontal web para su
visualización y gestión por parte de los usuarios de la plataforma.

![[]{#_Toc207873334 .anchor}Ilustración 15 -- Diagrama funcional gestion
de eventos](media/image21.png){width="5.285416666666666in"
height="2.5620089676290463in"}

## Flujos de entrada de información

La entrada de información podrá ser de diferentes tipos: transacciones y
predicciones de IA. Dependiendo del evento entrante, se procesarán las
reglas y se tratarán de distinta manera.\
Una vez hecho el procesamiento del evento, se generarán una serie de
alertas si se cumplen los requisitos de alguna de ellas.

Estas alertas se enviarán al topic de Kafka "prealerts" para una
verificación y gestión posterior. Enviándose al frontal de la aplicación
finalmente para la gestión por parte del usuario correspondiente.

Este componente esta formado por varias tecnologías que se comunican
entre ellas:

- **Apache Kafka:** gestiona los eventos entrantes y facilita el
  procesamiento de éstos en stream. Dependiendo del tipo de evento, se
  almacenará en un topic de Kafka diferente.

- **Apache Flink:** es la tecnología principal donde se ejecuta la
  lógica de negocio atribuida a las reglas definidas. Aporta el
  procesamiento batch en streaming de cada evento entrante.

- **Redis:** se trata de una base de datos key-value en memoria, permite
  almacenar datos que están en caché necesarios para las operaciones de
  trazabilidad.

- **OpenSearch:** es una base de datos NoSQL usada como la persistencia
  principal del componente. Se almacenarán datos de trazabilidad,
  auditoria de logs, transacciones, etc.

![[]{#_Toc207873335 .anchor}Ilustración 16 -- Diagrama flujo interno
gestor de reglas](media/image22.png){width="6.102083333333334in"
height="3.1020833333333333in"}

**Características técnicas:**

- Servidor AWS EC2 m6a.2xlarge (8 vCPUs, 32GB)

- Sistema Operation Ubuntu 22.04

- Apache Kafka 4.0.0

- Apache Flink 2.0.0

- Redis 7

- OpenSearch 3.0.0

- Docker

**Procedimiento de Análisis**

Es importante llevar un control y monitorización de las métricas de uso
del motor de reglas.

A partir de un análisis realizado con una carga de eventos habitual en
Bitcoin y Ethereum, y desplegando el motor de reglas con paralelismo 4,
se ha visto necesario el escalado de tipo de instancia EC2 de m6a.xlarge
a m6a.2xlarge

**Escalado EC2**

Como se puede ver en la siguiente imagen, los recursos de CPU y RAM
están rozando el 100%, interrumpiendo los procesos y ralentizando el
funcionamiento habitual.

A parte de esto, hay que puntualizar que la misma instancia comparte
recursos con el módulo de Inteligencia Artificial descrito
anteriormente. El cual usa 1 CPU al 100% durante aproximadamente 30
minutos y se ejecuta cada hora.

![[]{#_Toc207873336 .anchor}Ilustración 17 -- Métrica rendimiento CPU
(1)](media/image23.jpeg){width="6.102083333333334in"
height="1.8743055555555554in"}

Una vez migrada la instancia a m6a.2xlarge, como se puede observar en la
siguiente captura, el uso de recursos ha bajado entorno al 40-50%, lo
cual permite que todos los procesos se puedan ejecutar correctamente:

![](media/image24.png){width="6.102083333333334in"
height="2.0819444444444444in"}

[]{#_Toc207873337 .anchor}Ilustración 18 -- Métrica rendimiento CPU (2)

**Análisis de los resultados**

Los parámetros de comportamiento del motor de reglas se encuentran
dentro de lo normal.

En este sentido, y bajo las condiciones de los experimentos realizados,
no se observa un riesgo o problema latente de rendimiento en este
submódulo que pueda afectar al rendimiento de la aplicación.

**Recomendaciones**

Las recomendaciones planteadas son generales:

- Monitorizar las principales características del servicio (CPU y RAM)
  para verificar que las gráficas siguen mostrando el mismo
  comportamiento que el observado

- Monitorizar las métricas de procesamiento de reglas

- Establecer alertas cuando los valores superen los valores máximos
  identificados.

- Establecer alertas cuando se supere cierto umbral de lag de los
  tópicos de Kafka utilizados

- Migración hacia servicios nativos de AWS, lo cual aportará un mayor
  control, backups automáticos, escalado, alta disponibilidad y mayor
  seguridad.

### Gestión de eventos de transacciones

Uno de los eventos entrantes son las transacciones (BTC, ETH y POL). Los
procesos de ingesta están integrados con el bróker de Kafka del motor de
reglas para poder recibir todos los eventos generados.

![](media/image25.png){width="6.102083333333334in"
height="2.0944444444444446in"}

![[]{#_Toc207873338 .anchor}Ilustración 19 -- PKIs rendimiento gestor de
eventos (1)](media/image26.png){width="6.102083333333334in"
height="2.04375in"}

### Gestión de eventos de predicciones

![[]{#_Toc207873339 .anchor}Ilustración 20 -- PKIs rendimiento gestor de
eventos (2)](media/image27.png){width="6.102083333333334in"
height="2.2284722222222224in"}

# MODULO FRONTAL WEB [CITRA]{.mark}

[DEFINIR METRICAS DE RENDIMIENTO DEL FRONTEND]{.mark}

# Próximos Pasos

En este documento se han expuesto los PKIs técnicos y de rendimiento
establecidos con el prototipo de la solución durante las pruebas
ejecutadas en la etapa 2. Estos valores van acompañados de las métricas
obtenidas a través de los sistemas de monitorización establecidos dentro
de la infraestructura de la solución.

Esta información, además de proporcionar información para medir las
capacidades actuales, también son de vital importancia para establecer
la configuración del entorno necesario para la ejecución de las pruebas
de etapa 3 del proyecto y garantizar su correcto funcionamiento en un
entorno funcional.

También, a lo largo de este documento se han recogido otros aspectos a
tener en consideración a la hora de considerar un entorno productivo.
Estos aspectos, tienen que ser de consideración en los futuros procesos
de despliegues de la solución, de forma que se pueda garantizar su
correcto funcionamiento y operatividad. En este sentido, si bien la
solución es agnóstica del proveedor cloud (aunque actualmente corre en
infraestructura AWS), sería importante considerar las opciones y
servicios (IaaS y SaaS) del proveedor en el que se pretende desplegar la
solución para seleccionar aquellos que mejor se ajustes a las
necesidades de arquitectura (establecidas en el documento de
Arquitectura del prototipo) y de rendimiento (identificadas en este
documento) de la solución.

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

# ANEXO I: HISTÓRICO DE MODIFICACIONES

  ---------------------------------------------------------------------------
   Versión     Fecha          Autor      Modificaciones
  --------- ------------ --------------- ------------------------------------
     0.1     10/2/2025         ECC       Creación del documento y
                                         cumplimiento de puntos básicos

     0.2     20/05/2025        ECC       Actualización con las métricas
                                         observadas

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         

                                         
  ---------------------------------------------------------------------------

  : []{#_Toc133437760 .anchor}Tabla 2 -- Histórico de modificaciones

# ANEXO II: PKIs [TODOS]{.mark}

Dentro de esta sección se recogerán aquellos PKIs y métricas
establecidas a lo largo de este documento. Estas métricas podrán
emplearse para evaluar el rendimiento del proyecto en futuras fases
productivas y tomar decisiones sobre cambios o mejoras funcionales o de
arquitectura.

  -------------------------------------------------------------------------------
  Código     Nombre              Métrica         Rango            Observaciones
  ---------- ------------------- --------------- ---------------- ---------------
  PKI-0001   Ingesta BTC Red     Network In por  250 KB--4 MB/h   
             Entrada             hora                             

  PKI-0002   Ingesta BTC Red     Network Out por 512 KB--8 MB/h   
             Salida              hora                             

  PKI-0003   Ingesta BTC Bloques Bloques por     4--10 bloques/h  
                                 hora                             

  PKI-0004   Ingesta BTC         Transacciones   6000--24000 tx/h 
             Transacciones       por hora                         

  PKI-0005   Ingesta BTC CPU (4  Consumo CPU     5%--30%          
             vCPU)                                                

  PKI-0006   IA Predicciones     Duración        23--40 minutos   
                                                 (media \~25)     

  PKI-0007   IA Predicciones CPU Consumo CPU     ≤25% (1 vCPU al  
                                                 100%)            

  PKI-0008   IA Predicciones Red Network In por  ≤35 MB           
             In                  hora                             

  PKI-0009   IA Predicciones Red Network Out por ≤10 MB           
             Out                 hora                             

  PKI-0010   IA Predicciones     Consumo Disco   \~500 MB         
             Disco                                                

  PKI-0011   Enriquecimiento     CPU/RAM         30%--60% nominal 
             Airflow/Neo4J       (m6a.xlarge)    alerta \>85%     

  PKI-0012   Motor de Reglas     CPU/RAM         40%--50% nominal 
                                 (m6a.2xlarge)   alerta \>85%     

  PKI-0013   Motor de Reglas Lag Lag Kafka       Alerta si lag    
             Kafka                               supera umbral    
                                                 operativo (ej.   
                                                 menos de un      
                                                 minuto)          
  -------------------------------------------------------------------------------

  : Tabla 3 -- PKIs Propuestos
