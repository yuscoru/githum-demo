# CPP3-R4 — TRAC

## Documento de Datos de Éxito (Casos de Éxito Operativos)

**Proyecto:** CPP3 — Reto 4 — TRAC  
**Versión:** 1.6 (FINAL)  
**Fecha:** 2025  
**Clasificación:** Uso interno / Demostración operativa  

---

## ÍNDICE

1. [Introducción](#1-introducción)  
2. [Alcance y Objetivos](#2-alcance-y-objetivos)  
3. [Proceso Global del Sistema TRAC](#3-proceso-global-del-sistema-trac)  
4. [Caso de Éxito Operativo 1 — Detección de Dirección Sospechosa y Monitorización de Red](#4-caso-de-éxito-operativo-1--detección-de-dirección-sospechosa-y-monitorización-de-red)  
5. [Caso de Éxito Operativo 2 — Detección del Actor Lazarus mediante Histórico de Bloques](#5-caso-de-éxito-operativo-2--detección-del-actor-lazarus-mediante-histórico-de-bloques)  
6. [Tabla Resumen de Datos de Éxito](#6-tabla-resumen-de-datos-de-éxito)  
7. [Conclusiones](#7-conclusiones)  
8. [Referencias y Fuentes](#8-referencias-y-fuentes)  

---

## 1. Introducción

El presente documento recoge los **Datos de Éxito** del sistema TRAC (Trazabilidad, Registro y Análisis de Criptomonedas), correspondientes a los **Casos de Éxito Operativos** ejecutados durante la fase de validación del prototipo en el marco del proyecto CPP3-R4.

El sistema TRAC tiene como misión la detección, trazabilidad y análisis de transacciones sospechosas en redes blockchain (Bitcoin, Ethereum, Polygon), integrando módulos de ingestión de datos en tiempo real, enriquecimiento mediante inteligencia artificial (IA), motor de reglas, y alertas operativas.

Los casos de éxito aquí documentados demuestran la capacidad real del sistema para:

- Identificar y monitorizar direcciones de criptomonedas marcadas como sospechosas.
- Ejecutar análisis histórico de bloques para detectar interacciones con actores maliciosos conocidos.
- Generar alertas automáticas con información contextual (dirección, predicción IA, bloque, transacción).

---

## 2. Alcance y Objetivos

### 2.1 Alcance

Este documento cubre los casos de éxito operativos ejecutados sobre la blockchain de **Bitcoin (BTC)** mediante el modo de ejecución **histórico** y el modo de **monitorización en tiempo real** del sistema TRAC.

### 2.2 Objetivos

- Demostrar el funcionamiento end-to-end del sistema TRAC en un entorno real con datos reales de la blockchain de Bitcoin.
- Validar la capacidad del motor de IA para identificar direcciones sospechosas con alta precisión (predicción ≥ 0.6).
- Verificar la generación correcta de alertas operativas ante la detección de interacciones entre direcciones monitorizadas y direcciones catalogadas como sospechosas.
- Documentar evidencias reproducibles y trazables de cada caso de éxito.

---

## 3. Proceso Global del Sistema TRAC

El siguiente diagrama representa el proceso global de operación del sistema TRAC, desde la ingestión de datos blockchain hasta la generación de alertas:

> **[Figura 0 — Diagrama del Proceso Global del Sistema TRAC]**  
> *(Pendiente de insertar: diagrama de flujo global del sistema TRAC — ingestión → enriquecimiento → IA → motor de reglas → alertas)*

El flujo de proceso se estructura en las siguientes etapas principales:

1. **Ingestión**: El nodo blockchain captura bloques y transacciones en tiempo real o en modo histórico.
2. **Almacenamiento (Datalake)**: Los datos se almacenan en PostgreSQL (relacional) y Neo4j (grafos de relaciones).
3. **Enriquecimiento**: El módulo de enriquecimiento (Airflow + Neo4j) añade contexto a las transacciones (direcciones sospechosas, categorías, fuentes OSINT).
4. **Predicción IA**: El modelo de inteligencia artificial calcula un índice de sospecha (0–1) para cada dirección analizada.
5. **Motor de Reglas**: Evalúa las reglas de negocio configuradas y genera alertas cuando se detectan condiciones de riesgo.
6. **Alertas Operativas**: Las alertas son presentadas al operador con todos los datos contextuales relevantes.

---

## 4. Caso de Éxito Operativo 1 — Detección de Dirección Sospechosa y Monitorización de Red

### 4.1 Descripción del Caso

En este caso operativo se parte de una dirección BTC ya catalogada en el sistema como **maliciosa** con una **predicción IA del 100%**. El objetivo es utilizar el sistema TRAC para identificar y monitorizar otras direcciones que hayan interactuado con ella en la blockchain.

### 4.2 Datos de la Dirección Objetivo (Sospechosa Conocida)

| Campo | Valor |
|---|---|
| **Dirección objetivo** | `3Kj7XWBSzcGfrd4YzzFtrTc4xLrybB1KuK` |
| **Dirección IA** | `3Kj7XWBSzcGfrd4YzzFtrTc4xLrybB1KuK` |
| **Última actualización** | 2024-08-02T04:57:40.240000000+00:00 |
| **Nivel de sospecha** | 1 (máximo) |
| **Fuente** | DFIR |
| **Bloque** | 919573 |
| **Predicción IA** | 1.0 (100%) |

La dirección `3Kj7XWBSzcGfrd4YzzFtrTc4xLrybB1KuK` se encuentra registrada en el sistema (Neo4j) y catalogada con predicción IA del 100%, confirmando su naturaleza maliciosa.

### 4.3 Dirección Monitorizada (Relacionada)

A partir de la dirección objetivo, se identifica una dirección que **interaccionó** con ella en un momento dado en la blockchain:

| Campo | Valor |
|---|---|
| **Dirección monitorizada** | `bc1q5hjnc52wwk4wnvmy99ysxcnqa8en3mw85p99paq50lt5827dj5lq0wl4e4` |
| **Tipo de monitorización** | Ramp-off |
| **Objetivo** | Detectar posibles interacciones con otras direcciones sospechosas |

Se activa una **monitorización de tipo ramp-off** para esta dirección, orientada a detectar posibles interacciones con otras direcciones involucradas o marcadas como sospechosas.

### 4.4 Transacciones Relevantes Detectadas

| # | Transacción | Bloque | Descripción |
|---|---|---|---|
| 1 | `55dacd2d0b69398a14d5d5153d41b1d7241af7da291f034fcaefa94e8a18d681` | 916757 | La dirección monitorizada envía fondos a la dirección maliciosa |
| 2 | `a5cc52c3ea44daac0e2fe6fa5162c0b01a0fc87f67d06097adc687e4e99094d5` | 915346 | La dirección monitorizada recibe BTC |

### 4.5 Evidencias Visuales

> **[Figura 1 — Alta de la dirección monitorizada en el sistema TRAC]**  
> *(Pendiente de insertar: captura de pantalla del formulario/interfaz de alta de la dirección en el módulo de monitorización)*

> **[Figura 2 — Alerta generada por el sistema al detectar la interacción con la dirección maliciosa]**  
> *(Pendiente de insertar: captura de pantalla de la alerta operativa con datos de dirección, predicción, bloque y transacción)*

### 4.6 Resultado

El sistema TRAC **detectó correctamente** la interacción entre la dirección monitorizada y la dirección maliciosa conocida, generando la correspondiente alerta operativa con:

- Identificación de ambas direcciones involucradas.
- Índice de predicción IA de la dirección maliciosa: **1.0 (100%)**.
- Bloque y transacción exactos de la interacción.

**Veredicto: ✅ CASO DE ÉXITO OPERATIVO CONFIRMADO**

---

## 5. Caso de Éxito Operativo 2 — Detección del Actor Lazarus mediante Histórico de Bloques

### 5.1 Descripción del Caso

En este caso operativo se trabaja con una dirección BTC atribuida al grupo de amenaza avanzada **Lazarus** (actor de Estado), previamente catalogada en el sistema TRAC como involucrada en actividades ilícitas. Se ejecuta un **análisis histórico de bloques** para detectar interacciones con una dirección monitorizada.

### 5.2 Datos de la Dirección del Actor Lazarus

| Campo | Valor |
|---|---|
| **Dirección Lazarus (sospechosa)** | `18Uxo7GNYKSU6Ab5EXjV8ziJDjjJCXEhRq` |
| **Actor** | Lazarus (APT — amenaza persistente avanzada de Estado) |
| **Estado en sistema** | Catalogada como involucrada en actividades ilícitas — blockchain BTC |

### 5.3 Dirección Monitorizada

| Campo | Valor |
|---|---|
| **Dirección monitorizada** | `1DzNJZK2H5E1GtyHBgUcabfsdB2q9z3qtg` |
| **Predicción IA (propia)** | 0.6 (60%) — también catalogada como maliciosa |
| **Tipo de análisis** | Histórico de bloques |
| **Rango de bloques analizado** | 913340 → 913380 (80 bloques) |

> **Nota importante:** La dirección monitorizada `1DzNJZK2H5E1GtyHBgUcabfsdB2q9z3qtg` se encuentra a su vez catalogada en el sistema como **maliciosa**, con un índice de predicción IA de **0.6**. Esto añade relevancia operativa al caso, ya que ambas partes de la interacción son direcciones sospechosas.

### 5.4 Ejecución del Histórico y Resultados

Se ejecuta el histórico de la blockchain de Bitcoin entre los bloques **913340** y **913380**, detectando **múltiples interacciones** entre la dirección monitorizada y la dirección Lazarus.

Entre los patrones detectados destacan:

- **Transferencias parciales**: La dirección monitorizada envía una parte de los fondos a la dirección Lazarus y retiene el resto en la misma dirección, generando múltiples alertas.
- **Múltiples interacciones en el rango**: A lo largo de los 80 bloques analizados se producen varias transacciones entre ambas direcciones.

### 5.5 Alertas Generadas

Cada interacción detectada genera una alerta operativa que incluye:

| Campo de la Alerta | Descripción |
|---|---|
| **Dirección monitorizada** | `1DzNJZK2H5E1GtyHBgUcabfsdB2q9z3qtg` |
| **Predicción IA (monitorizada)** | 0.6 |
| **Dirección sospechosa contraparte** | `18Uxo7GNYKSU6Ab5EXjV8ziJDjjJCXEhRq` (Lazarus) |
| **Predicción IA (contraparte)** | Catalogada — actividad ilícita confirmada |
| **Bloque** | Dentro del rango 913340–913380 |
| **Transacción** | Hash de transacción exacto (registrado en el sistema) |

### 5.6 Evidencias Visuales

> **[Figura 3 — Ejecución del histórico de bloques en el sistema TRAC (rango 913340–913380)]**  
> *(Pendiente de insertar: captura de pantalla de la configuración y lanzamiento del histórico)*

> **[Figura 4 — Alertas operativas generadas por múltiples interacciones con la dirección Lazarus]**  
> *(Pendiente de insertar: captura de pantalla del listado de alertas generadas, mostrando dirección, predicción, bloque y transacción)*

### 5.7 Resultado

El sistema TRAC **detectó correctamente** múltiples interacciones entre la dirección monitorizada y la dirección del actor Lazarus, generando alertas para cada una de ellas. El análisis histórico de 80 bloques fue completado con éxito.

**Veredicto: ✅ CASO DE ÉXITO OPERATIVO CONFIRMADO**

---

## 6. Tabla Resumen de Datos de Éxito

| # | Caso | Blockchain | Modo | Dirección Monitorizada | Dirección Sospechosa | Predicción IA | Bloques Analizados | Alertas Generadas | Resultado |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Monitorización ramp-off — dirección maliciosa conocida | BTC | Tiempo real / Histórico | `bc1q5hjnc52...0wl4e4` | `3Kj7XWBSzc...1KuK` | 1.0 (100%) | 915346 – 916757 | ✅ Alerta generada | **ÉXITO** |
| 2 | Actor Lazarus — histórico de bloques | BTC | Histórico | `1DzNJZK2H5...qtg` (pred. 0.6) | `18Uxo7GNYK...hRq` (Lazarus) | 0.6 + catalogada | 913340 – 913380 (80 bloques) | ✅ Múltiples alertas | **ÉXITO** |

---

## 7. Conclusiones

Los dos casos de éxito operativos documentados demuestran que el sistema TRAC:

1. **Es capaz de detectar en tiempo real y en modo histórico** las interacciones entre direcciones monitorizadas y direcciones catalogadas como sospechosas o maliciosas.
2. **El motor de IA produce predicciones precisas** (1.0 para la dirección DFIR; 0.6 para la dirección con actividad conocida), que son coherentes con las fuentes de inteligencia externas.
3. **Las alertas operativas generadas son completas y trazables**, incluyendo identificador de dirección, predicción IA, número de bloque y hash de transacción.
4. **El sistema es efectivo frente a actores de amenaza avanzada** (APT como Lazarus), validando su utilidad en escenarios de inteligencia financiera y ciberseguridad.
5. **El modo histórico permite el análisis retrospectivo** de rangos de bloques acotados, facilitando la investigación forense digital de transacciones en la blockchain.

---

## 8. Referencias y Fuentes

- Documentación interna del proyecto CPP3-R4 TRAC (Deloitte / Equipo de desarrollo).
- Base de datos de direcciones sospechosas integrada en el sistema TRAC (fuente: DFIR interno).
- Inteligencia sobre el actor Lazarus: reportes públicos de atribución de actividad maliciosa en blockchain BTC.
- Blockchain de Bitcoin (mainnet) — datos consultados en tiempo real e histórico mediante nodo propio.
- Fuente oficial pública (OSINT): referencia exacta pendiente de adjuntar/citar.
