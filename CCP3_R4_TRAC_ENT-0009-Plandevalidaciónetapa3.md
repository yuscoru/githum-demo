Informe validación Etapa 3

R004_TRAC

# **ÍNDICE** {#índice .TOC-Heading}

[ÍNDICE DE TABLAS [2](#_Toc408386635)](#_Toc408386635)

[1 INTRODUCCIÓN [4](#introducción)](#introducción)

[1.1 Propósito [4](#propósito)](#propósito)

[1.2 Audiencia [4](#audiencia)](#audiencia)

[1.3 Ámbito [4](#ámbito)](#ámbito)

[1.4 Metodología de trabajo
[5](#metodología-de-trabajo)](#metodología-de-trabajo)

[2 Resultados VALIDACIÓN Etapa 3 [6](#_Toc145599529)](#_Toc145599529)

[2.1 PE3-0001 - Prueba global de integración de componentes.
[6](#pe3-0001---prueba-global-de-integración-de-componentes.)](#pe3-0001---prueba-global-de-integración-de-componentes.)

[2.2 PE3-0002 - Seguridad global de la herramienta.
[8](#pe3-0002---seguridad-global-de-la-herramienta.)](#pe3-0002---seguridad-global-de-la-herramienta.)

[2.3 PE3-0003 - Carga y Volumetría
[9](#pe3-0003---carga-y-volumetría)](#pe3-0003---carga-y-volumetría)

[2.4 PE3-0003.01 - Pruebas de rendimiento de usuario
[11](#pe3-0003.01---pruebas-de-rendimiento-de-usuario)](#pe3-0003.01---pruebas-de-rendimiento-de-usuario)

[2.5 PE3-0003.02 - Rendimiento ingesta datos
[14](#pe3-0003.02---rendimiento-ingesta-datos)](#pe3-0003.02---rendimiento-ingesta-datos)

[2.6 PE3-0004 - Opciones de menú disponibles
[21](#_Toc222675254)](#_Toc222675254)

[2.7 PE3-0004 - Testing menú disponibles
[22](#pe3-0004---testing-menú-disponibles)](#pe3-0004---testing-menú-disponibles)

[2.8 PE3-0005 - Capacidades de la landing
[24](#pe3-0005---capacidades-de-la-landing)](#pe3-0005---capacidades-de-la-landing)

[2.9 PE3-0006 - Capacidad de búsqueda
[25](#pe3-0006---capacidad-de-búsqueda)](#pe3-0006---capacidad-de-búsqueda)

[2.10 PE3-0006-03 - Búsquedas por IP
[28](#pe3-0006.03---búsquedas-por-ip)](#pe3-0006.03---búsquedas-por-ip)

[2.11 PE3-0006.02 - Búsquedas por Wallet
[31](#pe3-0006.02---búsquedas-por-wallet)](#pe3-0006.02---búsquedas-por-wallet)

[2.12 PE3-0007 - Monitoreo wallets
[35](#pe3-0007---monitoreo-wallets)](#pe3-0007---monitoreo-wallets)

[2.13 PE3-0007.01 - Monitorización de operación de entrada
[39](#pe3-0007.01---monitorización-de-operación-de-entrada)](#pe3-0007.01---monitorización-de-operación-de-entrada)

[2.14 PE3-0007.02 - Monitorización de operación de salida
[46](#pe3-0007.02---monitorización-de-operación-de-salida)](#pe3-0007.02---monitorización-de-operación-de-salida)

[2.15 PE3-0008 - Gestión de alertas
[52](#pe3-0008---gestión-de-alertas)](#pe3-0008---gestión-de-alertas)

[2.16 PE3-0009 - Monitorización
[59](#pe3-0009---monitorización)](#pe3-0009---monitorización)

[2.17 PE3-0009.01 - Generación de alerta
[60](#pe3-0009.01---generación-de-alerta)](#pe3-0009.01---generación-de-alerta)

[2.18 PE3-0009.02 - Simulación de alerta
[73](#pe3-0009.02---simulación-de-alerta)](#pe3-0009.02---simulación-de-alerta)

[2.19 PE3-0009.03 - Descarte de alertas
[77](#pe3-0009.03---descarte-de-alertas)](#pe3-0009.03---descarte-de-alertas)

[2.20 PE3-0009.04 - Histórico de una alerta
[81](#pe3-0009.04---histórico-de-una-alerta)](#pe3-0009.04---histórico-de-una-alerta)

[2.21 PE3-0010 - Gestión de Wallets
[84](#pe3-0010---gestión-de-wallets)](#pe3-0010---gestión-de-wallets)

[2.22 PE3-0010.01 - Elementos Wallet
[90](#pe3-0010.01---elementos-wallet)](#pe3-0010.01---elementos-wallet)

[2.23 PE3-0010.02 - Wallets sospechosos
[93](#pe3-0010.02---wallets-sospechosos)](#pe3-0010.02---wallets-sospechosos)

[2.24 PE3-0011 - Gestión de incidentes
[97](#pe3-0011---gestión-de-incidentes)](#pe3-0011---gestión-de-incidentes)

[2.25 PE3-0011.01 - Gestión de incidentes: Desde listado de incidentes
[101](#pe3-0011.01---gestión-de-incidentes-desde-listado-de-incidentes)](#pe3-0011.01---gestión-de-incidentes-desde-listado-de-incidentes)

[2.26 PE3-0011.02 - Gestión de incidentes: Escalado de alerta
[103](#pe3-0011.02---gestión-de-incidentes-escalado-de-alerta)](#pe3-0011.02---gestión-de-incidentes-escalado-de-alerta)

[2.27 PE3-0012 - Gestión de activos
[104](#pe3-0012---gestión-de-activos)](#pe3-0012---gestión-de-activos)

[2.28 PE3-0013 - Testing custodia de evidencias
[106](#pe3-0013---testing-custodia-de-evidencias)](#pe3-0013---testing-custodia-de-evidencias)

[2.29 PE3-0014 - Backups
[109](#pe3-0014---backups)](#pe3-0014---backups)

[3 Conclusiones [112](#conclusiones)](#conclusiones)

[4 REFERENCIAS [113](#referencias)](#referencias)

[ANEXO I. ÍNDICE de Requisitos [114](#_Toc222675280)](#_Toc222675280)

[ANEXO II. HISTÓRICO DE MODIFICACIONES
[116](#_Toc222675281)](#_Toc222675281)

[]{#_Toc408386635 .anchor}ÍNDICE DE TABLAS

[Tabla 1 -- Audiencia [7](#_Toc222680870)](#_Toc222680870)

[Tabla 1 -- PE3-0001 Elementos relacionados
[10](#_Toc222680871)](#_Toc222680871)

[Tabla 1 -- PE3-0002 Elementos relacionados
[12](#_Toc222680872)](#_Toc222680872)

[Tabla 1 -- PE3-0003 Elementos relacionados
[13](#_Toc222680873)](#_Toc222680873)

[Tabla 1 -- PE3-0003.01 Elementos relacionados
[16](#_Toc222680874)](#_Toc222680874)

[Tabla 1 -- PE3-0003.02 Elementos relacionados
[18](#_Toc222680875)](#_Toc222680875)

[Tabla 1 -- PE3-0004 Elementos relacionados
[25](#_Toc222680876)](#_Toc222680876)

[Tabla 1 -- PE3-0005 Elementos relacionados
[28](#_Toc222680877)](#_Toc222680877)

[Tabla 1 -- PE3-0006 Elementos relacionados
[29](#_Toc222680878)](#_Toc222680878)

[Tabla 1 -- PE3-0006.02 Elementos relacionados
[32](#_Toc222680879)](#_Toc222680879)

[Tabla 1 -- PE3-0006-03 Elementos relacionados
[36](#_Toc222680880)](#_Toc222680880)

[Tabla 1 -- PE3-0007 Elementos relacionados
[38](#_Toc222680881)](#_Toc222680881)

[Tabla 1 -- PE3-0007.01 Elementos relacionados
[44](#_Toc222680882)](#_Toc222680882)

[Tabla 1 -- PE3-0007.02 Elementos relacionados
[50](#_Toc222680883)](#_Toc222680883)

[Tabla 1 -- PE3-0008 Elementos relacionados
[56](#_Toc222680884)](#_Toc222680884)

[Tabla 1 -- PE3-0009 Elementos relacionados
[63](#_Toc222680885)](#_Toc222680885)

[Tabla 1 -- PE3-0009.01 Elementos relacionados
[64](#_Toc222680886)](#_Toc222680886)

[Tabla 1 -- PE3-0009.02 Elementos relacionados
[78](#_Toc222680887)](#_Toc222680887)

[Tabla 1 -- PE3-0009.03 Elementos relacionados
[82](#_Toc222680888)](#_Toc222680888)

[Tabla 1 -- PE3-0009.04 Elementos relacionados
[85](#_Toc222680889)](#_Toc222680889)

[Tabla 1 -- PE3-0010 Elementos relacionados
[88](#_Toc222680890)](#_Toc222680890)

[Tabla 1 -- PE3-0010.01 Elementos relacionados
[94](#_Toc222680891)](#_Toc222680891)

[Tabla 1 -- PE3-0010.02 Elementos relacionados
[97](#_Toc222680892)](#_Toc222680892)

[Tabla 1 -- PE3-0011 Elementos relacionados
[101](#_Toc222680893)](#_Toc222680893)

[Tabla 1 -- PE3-0011.01 Elementos relacionados
[105](#_Toc222680894)](#_Toc222680894)

[Tabla 1 -- PE3-0011.02 Elementos relacionados
[107](#_Toc222680895)](#_Toc222680895)

[Tabla 1 -- PE3-0012 Elementos relacionados
[109](#_Toc222680896)](#_Toc222680896)

[Tabla 1 -- PE3-0013 Elementos relacionados
[111](#_Toc222680897)](#_Toc222680897)

[Tabla 1 -- PE3-0014 Elementos relacionados
[114](#_Toc222680898)](#_Toc222680898)

[Tabla 1 -- Relación de casos de prueba por requisito
[120](#_Toc222680899)](#_Toc222680899)

[Tabla 1 -- Histórico de modificaciones
[121](#_Toc133437760)](#_Toc133437760)

ÍNDICE DE ILUSTRACIONES

[Ilustración 1 - PE3-0001 Evidencia Paso 1
[10](#_Toc222680721)](#_Toc222680721)

[Ilustración 1 - PE3-0001 Evidencia Paso 2
[10](#_Toc222680722)](#_Toc222680722)

[Ilustración 1 - PE3-0001 Evidencia Paso 3
[11](#_Toc222680723)](#_Toc222680723)

[Ilustración 1 - PE3-0003 Evidencia Paso 1
[13](#_Toc222680724)](#_Toc222680724)

[Ilustración 1 - PE3-0003 Evidencia Paso 3
[13](#_Toc222680725)](#_Toc222680725)

[Ilustración 1 - PE3-0003 Evidencia Paso 4
[14](#_Toc222680726)](#_Toc222680726)

[Ilustración 1 - PE3-0003 Evidencia Paso 5
[14](#_Toc222680727)](#_Toc222680727)

[Ilustración 1 - PE3-0003.01 Evidencia Paso 1
[15](#_Toc222680728)](#_Toc222680728)

[Ilustración 1 - PE3-0003.01 Evidencia Paso 2
[16](#_Toc222680729)](#_Toc222680729)

[Ilustración 1 - PE3-0003.01 Evidencia Paso 3
[17](#_Toc222680730)](#_Toc222680730)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 1
[18](#_Toc222680731)](#_Toc222680731)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 2
[19](#_Toc222680732)](#_Toc222680732)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 4
[19](#_Toc222680733)](#_Toc222680733)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 5
[20](#_Toc222680734)](#_Toc222680734)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 6
[20](#_Toc222680735)](#_Toc222680735)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 7
[21](#_Toc222680736)](#_Toc222680736)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 8
[21](#_Toc222680737)](#_Toc222680737)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 10
[22](#_Toc222680738)](#_Toc222680738)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 11
[22](#_Toc222680739)](#_Toc222680739)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 12
[23](#_Toc222680740)](#_Toc222680740)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 12
[23](#_Toc222680741)](#_Toc222680741)

[Ilustración 1 - PE3-0003.02 Evidencia Paso 12
[24](#_Toc222680742)](#_Toc222680742)

[Ilustración 1 - PE3-0004 Evidencia Paso 1
[25](#_Toc222680743)](#_Toc222680743)

[Ilustración 1 - PE3-0004 Evidencia Paso 1
[25](#_Toc222680744)](#_Toc222680744)

[Ilustración 1 - PE3-0004 Evidencia Paso 1
[26](#_Toc222680745)](#_Toc222680745)

[Ilustración 1 - PE3-0004 Evidencia Paso 1
[26](#_Toc222680746)](#_Toc222680746)

[Ilustración 1 - PE3-0005 Evidencia Paso 1
[27](#_Toc222680747)](#_Toc222680747)

[Ilustración 1 - PE3-0006 Evidencia Paso 1
[28](#_Toc222680748)](#_Toc222680748)

[Ilustración 1 - PE3-0006 Evidencia Paso 2
[29](#_Toc222680749)](#_Toc222680749)

[Ilustración 1 - PE3-0006 Evidencia Paso 3
[29](#_Toc222680750)](#_Toc222680750)

[Ilustración 1 - PE3-0006 Evidencia Paso 4
[30](#_Toc222680751)](#_Toc222680751)

[Ilustración 1 - PE3-0006 Evidencia Paso 5
[30](#_Toc222680752)](#_Toc222680752)

[Ilustración 1 - PE3-0006 Evidencia Paso 6
[31](#_Toc222680753)](#_Toc222680753)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 1
[32](#_Toc222680754)](#_Toc222680754)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 1
[32](#_Toc222680755)](#_Toc222680755)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 1
[33](#_Toc222680756)](#_Toc222680756)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 1
[33](#_Toc222680757)](#_Toc222680757)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 2
[34](#_Toc222680758)](#_Toc222680758)

[Ilustración 1 - PE3-0006.02 Evidencia Paso 2
[34](#_Toc222680759)](#_Toc222680759)

[Ilustración 1 - PE3-0006-03 Evidencia Paso 1
[35](#_Toc222680760)](#_Toc222680760)

[Ilustración 1 - PE3-0006-03 Evidencia Paso 2
[36](#_Toc222680761)](#_Toc222680761)

[Ilustración 1 - PE3-0006-03 Evidencia Paso 3
[36](#_Toc222680762)](#_Toc222680762)

[Ilustración 1 - PE3-0006-03 Evidencia Paso 5
[37](#_Toc222680763)](#_Toc222680763)

[Ilustración 1 - PE3-0007 Evidencia Paso 1
[38](#_Toc222680764)](#_Toc222680764)

[Ilustración 1 - PE3-0007 Evidencia Paso 2
[39](#_Toc222680765)](#_Toc222680765)

[Ilustración 1 - PE3-0007 Evidencia Paso 3
[40](#_Toc222680766)](#_Toc222680766)

[Ilustración 1 - PE3-0007 Evidencia Paso 4
[41](#_Toc222680767)](#_Toc222680767)

[Ilustración 1 - PE3-0007 Evidencia Paso 4
[41](#_Toc222680768)](#_Toc222680768)

[Ilustración 1 - PE3-0007 Evidencia Paso 5
[42](#_Toc222680769)](#_Toc222680769)

[Ilustración 1 - PE3-0007 Evidencia Paso 5
[42](#_Toc222680770)](#_Toc222680770)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 1
[43](#_Toc222680771)](#_Toc222680771)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 2
[44](#_Toc222680772)](#_Toc222680772)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 2
[45](#_Toc222680773)](#_Toc222680773)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 3
[46](#_Toc222680774)](#_Toc222680774)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 3
[46](#_Toc222680775)](#_Toc222680775)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 4
[47](#_Toc222680776)](#_Toc222680776)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 5
[48](#_Toc222680777)](#_Toc222680777)

[Ilustración 1 - PE3-0007.01 Evidencia Paso 5
[48](#_Toc222680778)](#_Toc222680778)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 1
[50](#_Toc222680779)](#_Toc222680779)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 2
[51](#_Toc222680780)](#_Toc222680780)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 2
[51](#_Toc222680781)](#_Toc222680781)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 3
[52](#_Toc222680782)](#_Toc222680782)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 3
[52](#_Toc222680783)](#_Toc222680783)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 4
[53](#_Toc222680784)](#_Toc222680784)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 5
[54](#_Toc222680785)](#_Toc222680785)

[Ilustración 1 - PE3-0007.02 Evidencia Paso 5
[54](#_Toc222680786)](#_Toc222680786)

[Ilustración 1 - PE3-0008 Evidencia Paso 1
[56](#_Toc222680787)](#_Toc222680787)

[Ilustración 1 - PE3-0008 Evidencia Paso 2
[57](#_Toc222680788)](#_Toc222680788)

[Ilustración 1 - PE3-0008 Evidencia Paso 3
[58](#_Toc222680789)](#_Toc222680789)

[Ilustración 1 - PE3-0008 Evidencia Paso 4
[59](#_Toc222680790)](#_Toc222680790)

[Ilustración 1 - PE3-0008 Evidencia Paso 5
[60](#_Toc222680791)](#_Toc222680791)

[Ilustración 1 - PE3-0008 Evidencia Paso 6
[61](#_Toc222680792)](#_Toc222680792)

[Ilustración 1 - PE3-0008 Evidencia Paso 7
[61](#_Toc222680793)](#_Toc222680793)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[64](#_Toc222680794)](#_Toc222680794)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[64](#_Toc222680795)](#_Toc222680795)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[65](#_Toc222680796)](#_Toc222680796)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[65](#_Toc222680797)](#_Toc222680797)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[66](#_Toc222680798)](#_Toc222680798)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 1
[66](#_Toc222680799)](#_Toc222680799)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[67](#_Toc222680800)](#_Toc222680800)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[67](#_Toc222680801)](#_Toc222680801)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[68](#_Toc222680802)](#_Toc222680802)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[68](#_Toc222680803)](#_Toc222680803)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[69](#_Toc222680804)](#_Toc222680804)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 2
[69](#_Toc222680805)](#_Toc222680805)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 3
[70](#_Toc222680806)](#_Toc222680806)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 3
[70](#_Toc222680807)](#_Toc222680807)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 3
[71](#_Toc222680808)](#_Toc222680808)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 3
[71](#_Toc222680809)](#_Toc222680809)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[72](#_Toc222680810)](#_Toc222680810)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[72](#_Toc222680811)](#_Toc222680811)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[73](#_Toc222680812)](#_Toc222680812)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[73](#_Toc222680813)](#_Toc222680813)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[73](#_Toc222680814)](#_Toc222680814)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 4
[74](#_Toc222680815)](#_Toc222680815)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 5
[74](#_Toc222680816)](#_Toc222680816)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 5
[75](#_Toc222680817)](#_Toc222680817)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 5
[75](#_Toc222680818)](#_Toc222680818)

[Ilustración 1 - PE3-0009.01 Evidencia Paso 5
[76](#_Toc222680819)](#_Toc222680819)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 1
[77](#_Toc222680820)](#_Toc222680820)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 2
[78](#_Toc222680821)](#_Toc222680821)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 3
[78](#_Toc222680822)](#_Toc222680822)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 4
[79](#_Toc222680823)](#_Toc222680823)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 4
[79](#_Toc222680824)](#_Toc222680824)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 5
[80](#_Toc222680825)](#_Toc222680825)

[Ilustración 1 - PE3-0009.02 Evidencia Paso 5
[80](#_Toc222680826)](#_Toc222680826)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 1
[81](#_Toc222680827)](#_Toc222680827)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 2
[82](#_Toc222680828)](#_Toc222680828)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 3
[82](#_Toc222680829)](#_Toc222680829)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 4
[83](#_Toc222680830)](#_Toc222680830)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 5
[83](#_Toc222680831)](#_Toc222680831)

[Ilustración 1 - PE3-0009.03 Evidencia Paso 6
[84](#_Toc222680832)](#_Toc222680832)

[Ilustración 1 - PE3-0009.04 Evidencia Paso 1
[85](#_Toc222680833)](#_Toc222680833)

[Ilustración 1 - PE3-0009.04 Evidencia Paso 2
[86](#_Toc222680834)](#_Toc222680834)

[Ilustración 1 - PE3-0009.04 Evidencia Paso 3
[86](#_Toc222680835)](#_Toc222680835)

[Ilustración 1 - PE3-0010 Evidencia Paso 1
[88](#_Toc222680836)](#_Toc222680836)

[Ilustración 1 - PE3-0010 Evidencia Paso 2
[89](#_Toc222680837)](#_Toc222680837)

[Ilustración 1 - PE3-0010 Evidencia Paso 3
[89](#_Toc222680838)](#_Toc222680838)

[Ilustración 1 - PE3-0010 Evidencia Paso 4
[90](#_Toc222680839)](#_Toc222680839)

[Ilustración 1 - PE3-0010 Evidencia Paso 5
[90](#_Toc222680840)](#_Toc222680840)

[Ilustración 1 - PE3-0010 Evidencia Paso 6
[91](#_Toc222680841)](#_Toc222680841)

[Ilustración 1 - PE3-0010 Evidencia Paso 7
[92](#_Toc222680842)](#_Toc222680842)

[Ilustración 1 - PE3-0010 Evidencia Paso 8
[92](#_Toc222680843)](#_Toc222680843)

[Ilustración 1 - PE3-0010 Evidencia Paso 9
[93](#_Toc222680844)](#_Toc222680844)

[Ilustración 1 - PE3-0010.01 Evidencia Paso 1
[94](#_Toc222680845)](#_Toc222680845)

[Ilustración 1 - PE3-0010.01 Evidencia Paso 2
[95](#_Toc222680846)](#_Toc222680846)

[Ilustración 1 - PE3-0010.01 Evidencia Paso 3
[95](#_Toc222680847)](#_Toc222680847)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 1
[96](#_Toc222680848)](#_Toc222680848)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 2
[97](#_Toc222680849)](#_Toc222680849)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 3
[98](#_Toc222680850)](#_Toc222680850)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 4
[98](#_Toc222680851)](#_Toc222680851)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 5
[99](#_Toc222680852)](#_Toc222680852)

[Ilustración 1 - PE3-0010.02 Evidencia Paso 6
[100](#_Toc222680853)](#_Toc222680853)

[Ilustración 1 - PE3-0011 Evidencia Paso 1
[101](#_Toc222680854)](#_Toc222680854)

[Ilustración 1 - PE3-0011 Evidencia Paso 2
[102](#_Toc222680855)](#_Toc222680855)

[Ilustración 1 - PE3-0011 Evidencia Paso 3
[103](#_Toc222680856)](#_Toc222680856)

[Ilustración 1 - PE3-0011 Evidencia Paso 4
[104](#_Toc222680857)](#_Toc222680857)

[Ilustración 1 - PE3-0011.01 Evidencia Paso 1
[105](#_Toc222680858)](#_Toc222680858)

[Ilustración 1 - PE3-0011.01 Evidencia Paso 1
[105](#_Toc222680859)](#_Toc222680859)

[Ilustración 1 - PE3-0011.02 Evidencia Paso 1
[107](#_Toc222680860)](#_Toc222680860)

[Ilustración 1 - PE3-0011.02 Evidencia Paso 1
[107](#_Toc222680861)](#_Toc222680861)

[Ilustración 1 - PE3-0012 Evidencia Paso 1
[108](#_Toc222680862)](#_Toc222680862)

[Ilustración 1 - PE3-0012 Evidencia Paso 2
[109](#_Toc222680863)](#_Toc222680863)

[Ilustración 1 - PE3-0012 Evidencia Paso 3
[109](#_Toc222680864)](#_Toc222680864)

[Ilustración 1 - PE3-0013 Evidencia Paso 1
[110](#_Toc222680865)](#_Toc222680865)

[Ilustración 1 - PE3-0013 Evidencia Paso 2
[111](#_Toc222680866)](#_Toc222680866)

[Ilustración 1 - PE3-0013 Evidencia Paso 3
[112](#_Toc222680867)](#_Toc222680867)

[Ilustración 1 - PE3-0013 Evidencia Paso 4
[112](#_Toc222680868)](#_Toc222680868)

[Ilustración 1 - PE3-0014 Evidencia Paso 1
[113](#_Toc210829001)](#_Toc210829001)

# INTRODUCCIÓN

## Propósito

Uno de los aspectos fundamentales de este proyecto de ingeniería es
contar con un plan de pruebas que pueda verificar el correcto
funcionamiento de la plataforma de acuerdo con las necesidades
establecidas y el TRL de destino.

Durante la etapa 3, se han estado ejecutando una serie de pruebas de
verificación planteadas dentro del documento del proyecto de ingeniería
entregado en la etapa 1, y revisado durante la etapa 2. Estas pruebas
han permitido validar el grado de cumplimiento y satisfacción de las
hipótesis y requisitos de partida, así como revisar los aspectos
críticos desde la perspectiva de usabilidad, y rendimiento de la
solución.

El propósito de este documento es recopilar los distintos escenarios y
casos de pruebas ejecutados en esta etapa de este proyecto de
ingeniería. Junto con cada caso de prueba, se incluye una descripción de
este donde se incluyen las precondiciones o aquellos aspectos
funcionales más críticos relativos al escenario a validar. También se
establecen los pasos ejecutados y las evidencias en forma de capturas de
pantalla correspondientes a cada caso. Por último, cada caso de prueba
irá acompañado del listado de actividades relacionadas que se incluían
en el plan de actividades del proyecto entregado en la etapa 1, y que
quedan verificadas con la ejecución de los distintos casos.

## Audiencia

La tabla siguiente proporciona información detallada sobre las
audiencias clave de este documento:

  -----------------------------------------------------------------------
  **Audience**                **Descripción**
  --------------------------- -------------------------------------------
  Equipo de trabajo de        Como soporte de las actividades de
  Deloitte                    desarrollo de nuevas funcionalidades y
                              supervisión y revisión de la arquitectura
                              de la aplicación

  Equipos de trabajo de       Como parte involucrada en el diseño y
  AirInstitute                desarrollo de la solución de arquitectura

  Entidad usuaria             Para la revisión de los requisitos y
                              necesidades funcionales establecidas, así
                              como la evaluación de los resultados de la
                              etapa 3.

  Equipos de auditoria        Para verificar el trabajo realizado.

  Equipo de INCIBE            Equipo encargado de garantizar los
                              compromisos adquiridos a lo largo de este
                              proyecto.
  -----------------------------------------------------------------------

  : []{#_Toc222680870 .anchor}Tabla 1 -- Audiencia

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
pagos recibidos por estas acciones. Es por ello que este reto busca dar
solución a los problemas actuales y futuros de trazabilidad, detección y
atribución de transacciones debidas a campañas originadas por el
cibercrimen.

Este documento incluye las pruebas de validación efectuadas durante la
etapa 3 de dicho proyecto. Estas pruebas han sido ejecutadas en la etapa
3, de acuerdo con la planificación inicial del proyecto. Estas pruebas
van alineadas con la verificación de los aspectos funcionales y no
funcionales descritos en el documento del proyecto de ingeniería, siendo
un elemento indispensable para confirmar el cumplimiento de los
requisitos y de los objetivos científicos establecidos inicialmente.

## Metodología de trabajo

De acuerdo con lo establecido en el documento de ingeniería del proyecto
entregado en la etapa 1, []{#_Toc145599529 .anchor}el principal objetivo
de definir una validación específica para la Etapa 3, es la de
establecer mecanismos que permitan validar el prototipo bajo unas
condiciones de uso equivalentes a las de un entorno real, así como
valorar si la solución ha alcanzado el nivel TRL de destino establecido.
Esto nos permitirá verificar el grado de corrección de la solución
propuesta, en relación con los requisitos, funcionalidades y objetivos
científicos planteados inicialmente, así como otros aspectos no
funcionales como la usabilidad, seguridad, interfaz de usuario,
mantenimiento, etc.

- **Usuarios:** Para ejecutar este tipo de verificación, se necesita
  contar con un conjunto de usuarios que actúen como verificadores de la
  solución. Este conjunto de usuarios ejecutará una serie flujos en la
  herramienta, tomando nota de cualquier tipo de circunstancia o aspecto
  a destacar.

- **Objetivos:** El objetivo será validar la corrección de la solución
  con relación a los requisitos y funcionalidades establecidos en la
  etapa 1, así como establecer si la solución cumple con el TRL de
  destino establecido. Para poder realizar esta validación, los
  requisitos incluirán un conjunto de criterios de aceptación que se
  establecieron inicialmente, de forma que sea más directo identificar
  los objetivos y aspectos a verificar.

- **Documentación y trazabilidad.** Para realizar esta tarea de
  validación, cada usuario contará con acceso a la herramienta de
  gestión de ticketing del proyecto (Azure DevOps). La plataforma
  permite asignar y gestionar el ciclo de vida de las distintas pruebas
  a realizar.

**Entorno de ejecución:** Se dispondrá de un entorno operacional
completo. Este entorno, que operativamente contará con todas las
funcionalidades y características incluidas en el prototipo, permitirá
la ejecución de los casos de pruebas. En el caso en el que haya alguno
que no se pueda verificar (porque dependa de alguna condicionante
externa que no se cumpla) se establecerán los mecanismos pertinentes
para su simulación.

**Simulaciones**: El sistema estará diseñado para soportar simulaciones,
éstas se utilizarán para generar datos sintéticos (dry run), de forma
que se pueda validar el funcionamiento del sistema ante escenarios
complejos y que sean difíciles de generar en un periodo corto de tiempo.
La ejecución de las simulaciones se realizará de manera coordinada con
todos los equipos implicados en la validación, de forma que estén al
tanto y puedan actuar de acorde a sus necesidades.

# Resultados VALIDACIÓN Etapa 3 

## PE3-0001 - Prueba global de integración de componentes.

Prueba de integración del SED con la Plataforma multimodal y la
Plataforma de operaciones. Simulación del flujo de operación estándar
desde el inicio de la búsqueda hasta reporte final. Comprobación de
almacenamiento de datos y de comunicación entre submódulos. Comprobación
de que los logs de auditoría incluyen información sobre las operaciones,
ofreciendo una trazabilidad completa sobre los flujos de datos.
Verificación de la monitorización del sistema. Smoke test de la
plataforma desde el punto de vista de usuario.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  OBJ-0002          Inteligencia artificial aplicada al análisis de
                    carteras

  OBJ-0003          Agrupación inteligente de información

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  OBJ-0002          Inteligencia artificial aplicada al análisis de
                    carteras

  OBJ-0003          Agrupación inteligente de información

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)
  -----------------------------------------------------------------------

  : []{#_Toc222680871 .anchor}Tabla 1 -- PE3-0001 Elementos relacionados

**Script de validación:**

- **Paso 1: Se verifica que todos los componentes están debidamente
  levantados**

**Resultados de la validación del paso:**

Las gráficas de consumo de recursos (memoria, CPU y red) de los
distintos elementos muestran valores dentro de lo esperado

**Evidencia**

![[]{#_Toc222680721 .anchor}Ilustración 1 - PE3-0001 Evidencia Paso
1](media/image5.jpeg){width="6.299212598425197in"
height="2.7883759842519686in"}

- **Paso 2: Verificar que los sistemas están debidamente configurados y
  reportando logs al sistema de trazas de la aplicacion**

**Resultados de la validación del paso:**

Dentro del sistema centralizado de logs, se observa la correcta
monitorizacion de todos los sistemas involucrados en la plataforma.

**Evidencia**

![[]{#_Toc222680722 .anchor}Ilustración 1 - PE3-0001 Evidencia Paso
2](media/image6.jpeg){width="6.299212598425197in"
height="2.4835367454068242in"}

![[]{#_Toc222680723 .anchor}Ilustración 1 - PE3-0001 Evidencia Paso
3](media/image7.jpeg){width="6.299212598425197in"
height="2.9303412073490813in"}

## PE3-0002 - Seguridad global de la herramienta.

Pruebas de seguridad de la plataforma: esto incluye pruebas de
penetración para identificar debilidades en la infraestructura y pruebas
de seguridad de código para garantizar que no hay fallos o puertas
traseras habilitadas por librerías o aplicaciones de terceros. Pruebas
de privacidad y protección de datos: se testeará la herramienta para
comprobar que se aplica el GCPR en todas las funcionalidades de esta.
Además, que se garantice su almacenamiento seguro y la anonimización en
caso de ser datos sensibles.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0001          ingesta de información de blockchains

  REQ-0002          Enriquecimiento desde fuentes externas

  REQ-0003          Correlación de información y descubrimiento
                    potenciado por inteligencia artificial

  REQ-0004          Trazabilidad y atribución potenciada por inteligencia
                    artificial

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  OBJ-0002          Inteligencia artificial aplicada al análisis de
                    carteras

  OBJ-0003          Agrupación inteligente de información

  ESN-0008          Conexiones seguras

  ESN-0009          Datos protegidos en reposo

  ESN-0011          Autenticación segura

  ESN-0012          Autorización por asignación de roles
  -----------------------------------------------------------------------

  : []{#_Toc222680872 .anchor}Tabla 1 -- PE3-0002 Elementos relacionados

**Script de validación:**

- **Paso 1: Ejecutar el proceso completo de penetration testing sobre el
  alcance autorizado, documentando los hallazgos y recopilando las
  evidencias necesarias para su validación, y elaborando las
  recomendaciones de remediación**

**Resultados de la validación del paso:**

Informe de pentesting generado y disponible (report emitido) con
hallazgos validados, evidencias y recomendaciones de remediación.

- **Paso 2: Ejecutar pruebas funcionales de privacidad sobre la
  herramienta para confirmar que se aplican los requisitos de GDPR en
  todas sus funcionalidades**

**Resultados de la validación del paso:**

Evidencia documentada de que la herramienta aplica GDPR en todas las
funcionalidades, con almacenamiento seguro y
anonimización/seudonimización efectiva para datos sensibles, incluyendo
incidencias detectadas y recomendaciones de corrección (si aplica)

## PE3-0003 - Carga y Volumetría

Pruebas que permitan identificar cuellos de botella o problema de carga
del sistema. Mediante diferentes pruebas se someterá a la aplicación a
distintos escenarios de estrés verificando que la respuesta operativa es
óptima.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0002          Enriquecimiento desde fuentes externas

  ESN-0002          Tiempo Real

  ESN-0001          Escalabilidad
  -----------------------------------------------------------------------

  : []{#_Toc222680873 .anchor}Tabla 1 -- PE3-0003 Elementos relacionados

**Script de validación:**

- **Paso 1: En primer lugar, se comprobará la existencia de métricas y
  controles en la propia infraestructura que permitan identificar
  cualquier problema de rendimiento, ya sea de manera local dentro de un
  determinado módulo o de manera general en alguno de los flujos de
  comunicación de datos**

**Resultados de la validación del paso:**

Revisar que, tanto los logs como las reglas están debidamente
configurados en el entorno, sirvidiendo como controles y elementos de
monitorizacion.

**Evidencia**

![[]{#_Toc222680724 .anchor}Ilustración 1 - PE3-0003 Evidencia Paso
1](media/image8.jpeg){width="6.299212598425197in"
height="0.27838254593175854in"}

- **Paso 2: Se establecerán diversos escenarios para ir verificando el
  correcto funcionando del sistema:**

**Resultados de la validación del paso:**

- **Paso 3: Escenario Bitcoin: Ejecutar los pasos requeridos para
  activar los mecanismos de ingesta y procesamiento de la blockchain de
  Bitcoin**

**Resultados de la validación del paso:**

Durante el proceso de activacion de los disitntos módulos y
funcionalidades, el sistema operará con normalidad. Las gráficas de
rendimiento y monitoirzacion de la infraestructura no mostrarán
problemas performance o cuellos de botella.

**Evidencia**

![[]{#_Toc222680725 .anchor}Ilustración 1 - PE3-0003 Evidencia Paso
3](media/image9.jpeg){width="6.299212598425197in"
height="0.338905293088364in"}

- **Paso 4: Escenario Ethereum: Ejecutar los pasos requeridos para
  activar los mecanismos de ingesta y procesamiento de la blockchain de
  Ethereum**

**Resultados de la validación del paso:**

Durante el proceso de activacion de los disitntos módulos y
funcionalidades, el sistema operará con normalidad. Las gráficas de
rendimiento y monitoirzacion de la infraestructura no mostrarán
problemas performance o cuellos de botella.

**Evidencia**

![[]{#_Toc222680726 .anchor}Ilustración 1 - PE3-0003 Evidencia Paso
4](media/image10.jpeg){width="6.299212598425197in"
height="0.29744422572178475in"}

- **Paso 5: Escenario Polygon: Ejecutar los pasos requeridos para
  activar los mecanismos de ingesta y procesamiento de la blockchain de
  Polygon**

**Resultados de la validación del paso:**

Durante el proceso de activacion de los disitntos módulos y
funcionalidades, el sistema operará con normalidad. Las gráficas de
rendimiento y monitoirzacion de la infraestructura no mostrarán
problemas performance o cuellos de botella.

**Evidencia**

![[]{#_Toc222680727 .anchor}Ilustración 1 - PE3-0003 Evidencia Paso
5](media/image11.jpeg){width="6.299212598425197in"
height="0.3125820209973753in"}

- **Paso 6:**

**Resultados de la validación del paso:**

## PE3-0003.01 - Pruebas de rendimiento de usuario

Hacer pruebas con distinto número de usuarios que actúen de manera
concurrente contra el sistema. Se verificará el correcto funcionamiento
y que el tiempo de respuesta del sistema es el adecuado. En la medida de
los posible este tipo de pruebas se automatizará de forma que se puedan
ejecutar de manera automática y recurrente, así como la trazabilidad en
el tiempo del flujo de ejecución establecido.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0008          Interface de usuario para investigación de casos e
                    Interoperabilidad

  ESF-0005          Sistema para la consulta del modelo de datos, y
                    generacion/gestion de informes por parte del equipo
                    de analistas.

  ESF-0004          Sistema de generación de casos de investigación para
                    analistas
  -----------------------------------------------------------------------

  : []{#_Toc222680874 .anchor}Tabla 1 -- PE3-0003.01 Elementos
  relacionados

**Script de validación:**

- **Paso 1: El usuario accederá a la plataforma y verificará el correcto
  funcionamiento de la aplicacion**

**Resultados de la validación del paso:**

El login funciona debidamente, permitiendole acceder a la aplicación

**Evidencia**

![[]{#_Toc222680728 .anchor}Ilustración 1 - PE3-0003.01 Evidencia Paso
1](media/image12.jpeg){width="6.299212598425197in"
height="3.218503937007874in"}

- **Paso 2: El usuario accederá a los distintos módulso a los que tiene
  acceso**

**Resultados de la validación del paso:**

El usuario tendrá acceso a los módulos de Incidentes, Alertas,
Monitorizacion, Direcciones.

**Evidencia**

![[]{#_Toc222680729 .anchor}Ilustración 1 - PE3-0003.01 Evidencia Paso
2](media/image13.jpeg){width="2.5083333333333333in" height="4.075in"}

- **Paso 3: El usuario podrá crear direcciones haciendo uso de las
  entidades anterioremente precargadas**

**Resultados de la validación del paso:**

El usuario podrá crear addresses relativas al tipo de Entidad:
\"Direccion de cliente\" que debidamente vendrá precargada en la
aplicacion.

**Evidencia**

![[]{#_Toc222680730 .anchor}Ilustración 1 - PE3-0003.01 Evidencia Paso
3](media/image14.jpeg){width="6.299212598425197in"
height="3.079853455818023in"}

## PE3-0003.02 - Rendimiento ingesta datos

Verificar que el flujo de ingesta de información no se ve afectado ante
una volumetría especialmente alta de datos a ingestar y que el sistema
es capaz de procesarlo, estableciendo los procedimientos asíncronos que
corresponda. Revisar el rendimiento en conjunto de la aplicacion,
revisando los logs desde la entrada de una transaccion hasta su
procesamiento final desde la capa de gestion de eventos o del sistema de
inteligencia artificial. Tomar nota de los tiempos de ejecucion, de
forma que se pueda verificar la perfecta sincronizacion y ajuste de los
distintos elementos.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0001          ingesta de información de blockchains

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  ESF-0002          Implementación mecanismos de búsqueda a partir de
                    indexadores establecidos

  ESF-0009          Estudio de alternativas para la Ingesta de
                    transacciones procedentes de blockchain Polygon

  ESF-0008          Estudio de alternativas para la Ingesta de
                    transacciones procedentes de blockchain Ethereum
  -----------------------------------------------------------------------

  : []{#_Toc222680875 .anchor}Tabla 1 -- PE3-0003.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: PKI-0001 Ingesta BTC Red Entrada (Network In por hora)**

**Resultados de la validación del paso:**

250 KB--4 MB/h

**Evidencia**

![[]{#_Toc222680731 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
1](media/image15.jpeg){width="6.299212598425197in"
height="2.252361111111111in"}

- **Paso 2: PKI-0002 Ingesta BTC Red Salida (Network Out por hora)**

**Resultados de la validación del paso:**

512 KB--8 MB/h

**Evidencia**

![[]{#_Toc222680732 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
2](media/image16.jpeg){width="6.299212598425197in"
height="2.7716535433070866in"}

- **Paso 3: PKI-0003 Ingesta BTC Bloques procesados por hora**

**Resultados de la validación del paso:**

4--10 bloques/h

- **Paso 4: PKI-0004 Ingesta BTC Transacciones por hora**

**Resultados de la validación del paso:**

6000--24000 tx/h

**Evidencia**

![[]{#_Toc222680733 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
4](media/image17.jpeg){width="6.299212598425197in"
height="2.272529527559055in"}

- **Paso 5: PKI-0005 Ingesta BTC CPU (4 vCPU)**

**Resultados de la validación del paso:**

5%--30%

**Evidencia**

![[]{#_Toc222680734 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
5](media/image18.jpeg){width="6.1in" height="2.45in"}

- **Paso 6: PKI-0006 IA Predicciones Duración ciclo ETL+predicción**

**Resultados de la validación del paso:**

23--40 minutos (media \~25)

**Evidencia**

![[]{#_Toc222680735 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
6](media/image19.jpeg){width="6.1in" height="1.7916666666666667in"}

- **Paso 7: PKI-0007 IA Predicciones CPU por ejecución**

**Resultados de la validación del paso:**

≤25% (1 vCPU al 100%)

**Evidencia**

![[]{#_Toc222680736 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
7](media/image20.jpeg){width="6.1in" height="1.775in"}

- **Paso 8: PKI-0008 IA Predicciones Red In por ejecución**

**Resultados de la validación del paso:**

≤35 MB

**Evidencia**

![[]{#_Toc222680737 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
8](media/image21.jpeg){width="6.1in" height="1.775in"}

- **Paso 9: PKI-0009 IA Predicciones Red Out por ejecución**

**Resultados de la validación del paso:**

≤10 MB

- **Paso 10: PKI-0010 IA Predicciones Disco por ejecución**

**Resultados de la validación del paso:**

\~500 MB

**Evidencia**

![[]{#_Toc222680738 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
10](media/image22.jpeg){width="6.1in" height="1.2916666666666667in"}

- **Paso 11: PKI-0011 Enriquecimiento Airflow/Neo4J CPU/RAM (m6a**

xlarge)

**Resultados de la validación del paso:**

30%--60% nominal alerta \>85%

**Evidencia**

![[]{#_Toc222680739 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
11](media/image23.jpeg){width="6.1in" height="2.0833333333333335in"}

- **Paso 12: PKI-0012 Motor de Reglas CPU/RAM (m6a**

2xlarge)

**Resultados de la validación del paso:**

40%--50% nominal alerta \>85%

**Evidencia**

![[]{#_Toc222680740 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
12](media/image24.jpeg){width="6.1in" height="2.225in"}

![[]{#_Toc222680741 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
12](media/image25.jpeg){width="6.1in" height="2.091666666666667in"}

![[]{#_Toc222680742 .anchor}Ilustración 1 - PE3-0003.02 Evidencia Paso
12](media/image26.jpeg){width="6.1in" height="2.0416655730533684in"}

- **Paso 13: PKI-0013 Motor de Reglas Lag Kafka**

**Resultados de la validación del paso:**

Alerta si lag supera umbral operativo (ej. menos de un minuto)

- **Paso 14: Revisar documento de pkis y rendimiento**

**Resultados de la validación del paso:**

## PE3-0004 - Testing menú disponibles

Landing con información general sobre el estado actual del sistema.
Búsquedas: que permitirá ejecutar búsquedas por distintos criterios y
mostrar el detalle relativo a activos. Alertas donde se visualizarán las
alertas a las que el usuario tiene acceso. Explorador de blockchains.
Incidentes donde se recogen los informes y reportes generados tanto de
manera automática como manual. Activos donde se mostrarán los activos
bajo una monitorización activa.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0008          Interface de usuario para investigación de casos e
                    Interoperabilidad

  OBJ-0003          Agrupación inteligente de información

  ESF-0001          Desarrollo POC de aplicación web
  -----------------------------------------------------------------------

  : []{#_Toc222680876 .anchor}Tabla 1 -- PE3-0004 Elementos relacionados

**Script de validación:**

- **Paso 1: Login en el portal visualización de la landing**

**Resultados de la validación del paso:**

Accesos a paneles que permitirá ejecutar búsquedas por distintos
criterios y mostrar el detalle relativo a activos. Alertas donde se
visualizarán las alertas a las que el usuario tiene acceso. Explorador
de blockchains. Incidentes donde se recogen los informes y reportes
generados tanto de manera automática como manual. Monitorizaciones donde
se mostrarán los activos bajo una monitorización activa.

**Evidencia**

![[]{#_Toc222680743 .anchor}Ilustración 1 - PE3-0004 Evidencia Paso
1](media/image27.jpeg){width="6.299212598425197in"
height="2.099737532808399in"}

![[]{#_Toc222680744 .anchor}Ilustración 1 - PE3-0004 Evidencia Paso
1](media/image28.jpeg){width="6.299212598425197in"
height="1.2332797462817149in"}

![[]{#_Toc222680745 .anchor}Ilustración 1 - PE3-0004 Evidencia Paso
1](media/image29.jpeg){width="6.299212598425197in"
height="1.6934372265966755in"}

![[]{#_Toc222680746 .anchor}Ilustración 1 - PE3-0004 Evidencia Paso
1](media/image30.jpeg){width="6.299212598425197in"
height="3.5277373140857393in"}

## PE3-0005 - Capacidades de la landing

Al entrar en la herramienta, el usuario tiene que tener una visión
general del estado de gestión de la información. En este sentido,
existirá una landing donde, de manera resumida, el usuario dispondrá de
contadores e información ajustado a las necesidades de su perfil. Se
verificará que se mostrará un resumen y accesos directo a aquellos
elementos que el sistema encuentre más relevantes para el usuario
actual. Esta landing será la pantalla inicial tras acceder al sistema,
de forma que pueda servir de referencia al usuario que está accediendo.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0008          Interface de usuario para investigación de casos e
                    Interoperabilidad

  OBJ-0003          Agrupación inteligente de información

  ESF-0001          Desarrollo POC de aplicación web
  -----------------------------------------------------------------------

  : []{#_Toc222680877 .anchor}Tabla 1 -- PE3-0005 Elementos relacionados

**Script de validación:**

- **Paso 1: La aplicación tendrá una landig al inicio con un resumen de
  la aplicación**

**Resultados de la validación del paso:**

Al entrar en la aplicación, se cargará de inicio una landing con
dashboard donde se resumen infomración de la aplicación

**Evidencia**

![[]{#_Toc222680747 .anchor}Ilustración 1 - PE3-0005 Evidencia Paso
1](media/image31.jpeg){width="6.299212598425197in"
height="3.7030653980752404in"}

## PE3-0006 - Capacidad de búsqueda

En un interface sencillo y cómodo, el usuario tendrá la capacidad de
establecer los criterios de búsqueda y lanzar la consulta. El usuario
podrá acceder al detalle de los elementos coincidentes con los criterios
establecidos.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0003          Correlación de información y descubrimiento
                    potenciado por inteligencia artificial

  ESF-0002          Implementación mecanismos de búsqueda a partir de
                    indexadores establecidos
  -----------------------------------------------------------------------

  : []{#_Toc222680878 .anchor}Tabla 1 -- PE3-0006 Elementos relacionados

**Script de validación:**

- **Paso 1: Acceso a traves del menú, al panel de Alertas**

**Resultados de la validación del paso:**

Listado de Alertas

**Evidencia**

![[]{#_Toc222680748 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
1](media/image32.jpeg){width="6.299212598425197in"
height="3.4363385826771653in"}

- **Paso 2: Sobre el listado de alertas, lanzar una busqueda aplicando
  las diferentes opciones de filtrado : fecha, address, nombre, tipo,
  source**

**Resultados de la validación del paso:**

En el listado debe mostrar alertas coincidentes con los criterios de los
filtros seleccionados

**Evidencia**

![[]{#_Toc222680749 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
2](media/image33.jpeg){width="6.299212598425197in"
height="1.24332239720035in"}

- **Paso 3: Acceso a traves del menú, al panel de incidentes**

**Resultados de la validación del paso:**

Listado de incidentes

**Evidencia**

![[]{#_Toc222680750 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
3](media/image34.jpeg){width="6.299212598425197in"
height="1.0176793525809273in"}

- **Paso 4: Sobre el listado de incidentes, lanzar busqueda aplicando el
  filtro de close Date**

**Resultados de la validación del paso:**

Listado que muestra los incidentes coincidentes con el filtro aplicado

**Evidencia**

![[]{#_Toc222680751 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
4](media/image35.jpeg){width="6.299212598425197in"
height="0.9237139107611548in"}

- **Paso 5: Acceso a traves del menú, al panel de addresses**

**Resultados de la validación del paso:**

Listado de addresses.

**Evidencia**

![[]{#_Toc222680752 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
5](media/image36.jpeg){width="6.299212598425197in"
height="1.8662095363079616in"}

- **Paso 6: Sobre el listado de addresses, lanzar busqueda aplicando
  filtros : address, network, identity**

**Resultados de la validación del paso:**

Listado que muestra las addresses coincidentes con el o los filtros
aplicados.

**Evidencia**

![[]{#_Toc222680753 .anchor}Ilustración 1 - PE3-0006 Evidencia Paso
6](media/image37.jpeg){width="6.299212598425197in"
height="1.0302241907261593in"}

## PE3-0006.02 - Búsquedas por Wallet

El sistema tiene la posibilidad de lanzar búsqueda por wallet. En este
sentido se mostrará el wallet, las transacciones relacionadas con el
mismo, la información de actores si el sistema ha identificado cualquier
tipo de coincidencia, información de ips, alertas generadas, etc...

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0003          Correlación de información y descubrimiento
                    potenciado por inteligencia artificial

  ESF-0002          Implementación mecanismos de búsqueda a partir de
                    indexadores establecidos
  -----------------------------------------------------------------------

  : []{#_Toc222680879 .anchor}Tabla 1 -- PE3-0006.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Dentro del frontal web del prototipo, el usuario tendrá la
  capacidad de lanzar una búsqueda por la dirección**

El usuario tendrá que indicar adicionalmente si la dirección pertenece a
una blockchain o a otra.

**Resultados de la validación del paso:**

El usuario tendrá la capacidad de lanzar una búsqueda a partir de la
informacion de la blockchain, y de la address sobre la que quiere
consultar la información.

**Evidencia**

![[]{#_Toc222680754 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
1](media/image38.jpeg){width="6.299212598425197in"
height="2.6280369641294836in"}

![[]{#_Toc222680755 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
1](media/image39.jpeg){width="6.299212598425197in"
height="2.8321259842519684in"}

![[]{#_Toc222680756 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
1](media/image40.jpeg){width="6.299212598425197in"
height="2.769653324584427in"}

![[]{#_Toc222680757 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
1](media/image41.jpeg){width="6.299212598425197in"
height="2.7241655730533685in"}

- **Paso 2: El sistema lanzará la petición al datalake, recuperando toda
  la información correspondiente de esa dirección**

**Resultados de la validación del paso:**

Busqueda relaciones de la address con otras addresses, transacciones,
tools, actors \...

**Evidencia**

![[]{#_Toc222680758 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
2](media/image42.jpeg){width="6.299212598425197in"
height="2.6368799212598426in"}

![[]{#_Toc222680759 .anchor}Ilustración 1 - PE3-0006.02 Evidencia Paso
2](media/image43.jpeg){width="6.299212598425197in"
height="2.8581299212598426in"}

## PE3-0006.03 - Búsquedas por IP

El sistema tiene la posibilidad de lanzar búsquedas por ip. En este
sentido se mostrará la información recopilada en el sistema que
corresponda con dicha IP, como por ejemplo Wallets, transacciones,
Actores, etc...

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0003          Correlación de información y descubrimiento
                    potenciado por inteligencia artificial

  ESF-0002          Implementación mecanismos de búsqueda a partir de
                    indexadores establecidos
  -----------------------------------------------------------------------

  : []{#_Toc222680880 .anchor}Tabla 1 -- PE3-0006-03 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Iniciar sesión y navegar a la pantalla del Explorer desde el
  menú : DataLake/Explorer**

**Resultados de la validación del paso:**

Se muestra el Explorer sin errores, con controles de búsqueda visibles.

**Evidencia**

![[]{#_Toc222680760 .anchor}Ilustración 1 - PE3-0006-03 Evidencia Paso
1](media/image44.jpeg){width="6.299212598425197in"
height="2.8955785214348206in"}

- **Paso 2: Seleccionar la opción "Búsqueda por IP" (tab, filtro o tipo
  de entidad)**

**Resultados de la validación del paso:**

El explorer cambia al modo IP (placeholder/formato IP, ayuda o
validación aplicable).

**Evidencia**

![[]{#_Toc222680761 .anchor}Ilustración 1 - PE3-0006-03 Evidencia Paso
2](media/image45.jpeg){width="6.299212598425197in"
height="2.4035148731408573in"}

- **Paso 3: Introducir IP y ejecutar la búsqueda**

**Resultados de la validación del paso:**

La búsqueda se ejecuta correctamente. Se muestra un resultado principal
asociado a IP (nodo IP o entidad equivalente) y/o un panel de
resultados.

**Evidencia**

![[]{#_Toc222680762 .anchor}Ilustración 1 - PE3-0006-03 Evidencia Paso
3](media/image46.jpeg){width="6.299212598425197in"
height="2.5690649606299214in"}

- **Paso 4: Revisar la tarjeta/panel del resultado principal de IP**

**Resultados de la validación del paso:**

Se muestran los atributos esperados mínimo IP, y metadatos si existen

- **Paso 5: Abrir la vista de grafo o sección de relaciones asociada a
  la IP**

**Resultados de la validación del paso:**

Se visualizan nodos relacionados a IP acorde al modelo (p. ej. Address,
Transaction, Actor, Tool, Event). La IP aparece conectada y el grafo es
navegable.

**Evidencia**

![[]{#_Toc222680763 .anchor}Ilustración 1 - PE3-0006-03 Evidencia Paso
5](media/image47.jpeg){width="6.299212598425197in"
height="2.3842038495188103in"}

## PE3-0007 - Monitoreo wallets

Ante la activación del monitoreo para un determinado wallet, al acceder
al wallet se verifica que existe una marca que identifica de manera
univoca que el elemento se esta monitorizando. Las trazas de auditoria
también mostrarán que ese wallet está siendo monitorizado. Se verificará
monitorización por incremento o reducción de capital.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0003          Agrupación inteligente de información

  ESF-0025          Evaluacion de técnicas de Machine Learning para la
                    identificación de comportamientos anómalos sin
                    supervisión
  -----------------------------------------------------------------------

  : []{#_Toc222680881 .anchor}Tabla 1 -- PE3-0007 Elementos relacionados

**Script de validación:**

- **Paso 1: El usuario registrará la Adress en case a la parametrización
  establecida**

**Resultados de la validación del paso:**

El sistema permitirá el registro de la address

**Evidencia**

![[]{#_Toc222680764 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
1](media/image48.jpeg){width="6.299212598425197in"
height="2.7922276902887138in"}

- **Paso 2: Verificar que, una vez registrada la Address, el usuario
  podrá acceder a la parte de monitorizacion y configurar las opciones
  que correspondan**

**Resultados de la validación del paso:**

El usuario podrá identificar la address de entre las opcioens que se le
presenten.

**Evidencia**

![[]{#_Toc222680765 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
2](media/image49.jpeg){width="6.299212598425197in"
height="3.1666087051618548in"}

- **Paso 3: El usuario podrá crear una regla de monitorizacion, de entre
  el conjunto existente, de monitorizacion**

**Resultados de la validación del paso:**

La regla de monitorizacion quedará debidamente registrada en el sisstema

**Evidencia**

![[]{#_Toc222680766 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
3](media/image50.jpeg){width="6.299212598425197in"
height="3.7139654418197727in"}

- **Paso 4: Tras la debida actaulizacion del sistema de monitoreo, el
  sistema comenzará a revisar el estado de ese activo**

**Resultados de la validación del paso:**

Se visualizarán trazas en los sistemas de log que permitan verificar que
la monitorizacion se está realizando de acuerdo a los parámetros
establecidos.

**Evidencia**

![[]{#_Toc222680767 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
4](media/image51.jpeg){width="6.299212598425197in"
height="3.1598272090988626in"}

![[]{#_Toc222680768 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
4](media/image52.jpeg){width="6.299212598425197in"
height="3.180761154855643in"}

- **Paso 5: En el caso en el que se identifique una coincidencia, de
  acuerdo a los parámetros del sistema, se generará una alerta**

**Resultados de la validación del paso:**

El sistema generará una consiguiente alerta a partir de la informacion
establecida.

**Evidencia**

![[]{#_Toc222680769 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
5](media/image53.jpeg){width="6.299212598425197in"
height="3.0237390638670165in"}

![[]{#_Toc222680770 .anchor}Ilustración 1 - PE3-0007 Evidencia Paso
5](media/image54.jpeg){width="6.299212598425197in"
height="3.0423173665791774in"}

## PE3-0007.01 - Monitorización de operación de entrada

Ante el escenario planteado en el punto PE3-0004, se verificará que,
ante una variación significativa en el balance o capital por una
transacción de una wallet bajo nuestro control, salta una alerta. Se
realizará una verificación de la alerta acorde sus características.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680882 .anchor}Tabla 1 -- PE3-0007.01 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Creación de monitorización**

El usuario dará de alta una regla de balance monitorizará una
determinada cartera.

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680771 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
1](media/image50.jpeg){width="6.299212598425197in"
height="3.7139654418197727in"}

- **Paso 2: El sistema identifica una casuística en base a los datos
  establecidos para la monitorizacion**

**Resultados de la validación del paso:**

El sistema monitoriza constemente el tráfico de la blockchain, y tiene
la capacidad de identificar cuando la address supera el limite de
variación de balance establecido y hace saltar la regla establecida en
el paso anterior. Se registra el match de la regla y se genera una
prealerta que luego se procesa.

**Evidencia**

![[]{#_Toc222680772 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
2](media/image52.jpeg){width="6.299212598425197in"
height="3.180761154855643in"}

![[]{#_Toc222680773 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
2](media/image51.jpeg){width="6.299212598425197in"
height="3.1598272090988626in"}

- **Paso 3: Generación de alerta**

Detectar transferencias inusualmente altas desde una cuenta
monitorizada, que exceden un porcentaje definido del saldo total

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con información sobre la
transacción y el porcentaje transferido

**Evidencia**

![[]{#_Toc222680774 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
3](media/image53.jpeg){width="6.299212598425197in"
height="3.0237390638670165in"}

![[]{#_Toc222680775 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
3](media/image54.jpeg){width="6.299212598425197in"
height="3.0423173665791774in"}

- **Paso 4: Se comprueba la generación de una alerta con información
  sobre la transacción y el porcentaje transferido**

**Resultados de la validación del paso:**

Verificar que el usuario tiene la capacidad de visualizar la nueva
alerta, con informacion suficiente para distinguirla del resto como un
nuevo elemento

**Evidencia**

![[]{#_Toc222680776 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
4](media/image55.jpeg){width="6.299212598425197in"
height="4.433191163604549in"}

- **Paso 5: Operativas de gestión de la alerta**

El usuario tiene la capacidad de descartar la alerta en base a la
información recibida.

**Resultados de la validación del paso:**

Se verifica que el usuario tiene la capacidad de acceder al detalle de
la alerta y actualizar su estado. El usuario podrá pasarla a estado
descartada, en el caso en el que lo considere necesario.

**Evidencia**

![[]{#_Toc222680777 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
5](media/image56.jpeg){width="6.299212598425197in"
height="4.401445756780403in"}

![[]{#_Toc222680778 .anchor}Ilustración 1 - PE3-0007.01 Evidencia Paso
5](media/image57.jpeg){width="6.299212598425197in"
height="3.939816272965879in"}

## PE3-0007.02 - Monitorización de operación de salida

Ante el escenario planteado en el punto PE3-0004, se verificará que
,ante una reducción de capital por una transacción bajo nuestro control,
se eleva una alerta. Se verificara el contenido de transacciones de la
alerta.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680883 .anchor}Tabla 1 -- PE3-0007.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Creación de monitorización**

El usuario dará de alta una regla de balance monitorizará una
determinada cartera.

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680779 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
1](media/image50.jpeg){width="6.299212598425197in"
height="3.7139654418197727in"}

- **Paso 2: El sistema identifica una casuística en base a los datos
  establecidos para la monitorizacion**

**Resultados de la validación del paso:**

El sistema monitoriza constemente el tráfico de la blockchain, y tiene
la capacidad de identificar cuando la address supera el limite de gasto
de balance establecido y hace saltar la regla establecida en el paso
anterior. Se registra el match de la regla y se genera una prealerta que
luego se procesa.

**Evidencia**

![[]{#_Toc222680780 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
2](media/image51.jpeg){width="6.299212598425197in"
height="3.1598272090988626in"}

![[]{#_Toc222680781 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
2](media/image52.jpeg){width="6.299212598425197in"
height="3.180761154855643in"}

- **Paso 3: Generación de alerta**

Detectar transferencias inusualmente altas desde una cuenta
monitorizada, que exceden un porcentaje definido del saldo total

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con información sobre la
transacción y el porcentaje transferido

**Evidencia**

![[]{#_Toc222680782 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
3](media/image54.jpeg){width="6.299212598425197in"
height="3.0423173665791774in"}

![[]{#_Toc222680783 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
3](media/image53.jpeg){width="6.299212598425197in"
height="3.0237390638670165in"}

- **Paso 4: Se comprueba la generación de una alerta con información
  sobre la transacción y el porcentaje transferido**

**Resultados de la validación del paso:**

Verificar que el usuario tiene la capacidad de visualizar la nueva
alerta, con informacion suficiente para distinguirla del resto como un
nuevo elemento

**Evidencia**

![[]{#_Toc222680784 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
4](media/image55.jpeg){width="6.299212598425197in"
height="4.433191163604549in"}

- **Paso 5: Operativas de gestión de la alerta**

El usuario tiene la capacidad de descartar la alerta en base a la
información recibida.

**Resultados de la validación del paso:**

Se verifica que el usuario tiene la capacidad de acceder al detalle de
la alerta y actualizar su estado. El usuario podrá pasarla a estado
descartada, en el caso en el que lo considere necesario.

**Evidencia**

![[]{#_Toc222680785 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
5](media/image56.jpeg){width="6.299212598425197in"
height="4.401445756780403in"}

![[]{#_Toc222680786 .anchor}Ilustración 1 - PE3-0007.02 Evidencia Paso
5](media/image57.jpeg){width="6.299212598425197in"
height="3.939816272965879in"}

## PE3-0008 - Gestión de alertas

Ante la generación de una alerta se verificará que se respeta la
configuración del usuario con relación al tipo de notificación que se
recibe. La alerta se visualizará en el panel de alertas acorde a
criterios de ordenación y filtrado mostrando estado, marca de tiempo, y
nivel. El usuario podrá gestionar la alerta y pivotar al activo
(wallets) relacionado. Se verificará la trazabilidad de forma que sea
posible identificar el origen, y el flujo seguido para su creación. El
objetivo de este escenario de verificación es el de verificar que un
usuario dispone de toda la información requerida para proceder a la
correcta gestión de la alerta, esta información, procedente tanto del
sistema de inteligencia artificial como de las propias decisiones del
equipo que opera la propia herramienta, tienen que proporcional
suficiente información para facilitar su gestión y establecer los pasos
requeridos.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680884 .anchor}Tabla 1 -- PE3-0008 Elementos relacionados

**Script de validación:**

- **Paso 1: El sistema habra creado una alerta en base a los criterios
  de monitorizacion que haya correspondido**

**Resultados de la validación del paso:**

Los usuarios asociados recibirán una notificacion con la informacion
correspondiente a la alerta

**Evidencia**

![[]{#_Toc222680787 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
1](media/image58.jpeg){width="6.299212598425197in"
height="3.497949475065617in"}

- **Paso 2: El usuario tendrá la capacidad de visualizar la alerta
  dentro del listado**

**Resultados de la validación del paso:**

El usuario podrá ver la alerta, confirmando los datos que ha recibido en
la notificación

**Evidencia**

![[]{#_Toc222680788 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
2](media/image58.jpeg){width="6.299212598425197in"
height="3.497949475065617in"}

- **Paso 3: El usuario podrá filtrar el listado en base a las distintas
  columnas disponibles, de forma que pueda quedarse únicamente con
  aquella que acaba de generarse**

**Resultados de la validación del paso:**

En las cabeceras de las distintas columnas, el usuario podrá establecer
los valores que considere oportuno y en base a ellos, poder visualizar
la alerta correspondiente

**Evidencia**

![[]{#_Toc222680789 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
3](media/image59.jpeg){width="6.299212598425197in"
height="3.52416447944007in"}

- **Paso 4: El usuario podrá acceder al detalle de la alerta**

**Resultados de la validación del paso:**

El sistema permite acceder a una vista donde se muestre el detalle de la
alerta que se ha generado

**Evidencia**

![[]{#_Toc222680790 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
4](media/image60.jpeg){width="6.299212598425197in"
height="3.2578740157480315in"}

- **Paso 5: Dentro del detalle, el usuario podrá visualizar la
  informacion asociada**

**Resultados de la validación del paso:**

Los campos principales son: Estado de la alerta, Tipo de alerta,
Criticidad de la alerta, Descripcion y Accion a realizar, y detalle
tecnico proporcionado por el motor de reglas.

**Evidencia**

![[]{#_Toc222680791 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
5](media/image61.jpeg){width="6.299212598425197in"
height="3.5212095363079614in"}

- **Paso 6: El usuario podrá cambiar el estado de la alerta, en base a
  los procesos que vaya ejecutando**

**Resultados de la validación del paso:**

El usuario tendrá a su disposicion el campo estado.

**Evidencia**

![[]{#_Toc222680792 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
6](media/image62.jpeg){width="6.299212598425197in"
height="3.1634656605424323in"}

- **Paso 7: La alerta quedará debidamente guardara y disponible en el
  sistema**

**Resultados de la validación del paso:**

La informacion quedará debidamente guardada en la bae de datos del
sistema.

**Evidencia**

![[]{#_Toc222680793 .anchor}Ilustración 1 - PE3-0008 Evidencia Paso
7](media/image63.jpeg){width="6.299212598425197in"
height="2.5403127734033246in"}

## PE3-0009 - Monitorización

El sistema realizará una monitorización automática, acorde a los
requisitos de IA establecidos para el proyecto.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0009          Gobierno del sistema

  OBJ-0003          Agrupación inteligente de información

  OBJ-0002          Inteligencia artificial aplicada al análisis de
                    carteras

  ESF-0027          Evaluación de mecanismos de monitorización de la
                    inteligencia artificial
  -----------------------------------------------------------------------

  : []{#_Toc222680885 .anchor}Tabla 1 -- PE3-0009 Elementos relacionados

**Script de validación:**

- **Paso 1: Verificar los procesos de programación del sistema,
  verificando la correcta parametrización de la ejecución de
  procesamiento de la información**

**Resultados de la validación del paso:**

El sistema está correctamente configurado, de acuerdo a las
parametrizaciones establecidas: Las claves se encuentran almacenadas en
los repositorios seguros, configuraciones de accesibilidad y red de
acuerdo al diagrama de arquitectura establecido en la documentación de
arquitectura, verificación de configuraciones de máquinas y servicios
dentro del proveedor cloud, comprobación de configuración establecido
para aplicación web. Así mismo se verifica que los procesos y sistemas
de monitorización y performance están debidamente activados y
configurados de acuerdo a los parámetros establecidos.

- **Paso 2: Verificar la monitorización de ese proceso, verificando la
  generación de trazas relativas a su propia ejecución**

**Resultados de la validación del paso:**

Se comprueba que, una vez en funcionamiento, el sistema es capaz de
generar trazas de ejecución, dejando evidencia de las actividades
internas, y las operaciones ejecutadas en el frontal web.

- **Paso 3: Verificar la performance global del sistema, de acuerdo a
  los aspectos técnicos establecidas para la vista**

**Resultados de la validación del paso:**

Las métricas obtenidas muestran la correcta ejecución del sistema. Estas
métricas muestran a nivel de servidor la ejecución dentro de los
parámetros operacionales establecidos, así como tiempos de respuesta
dentro de los rangos considerados aceptables para la ejecución de la
aplicación

- **Paso 4: Verificar la integración de todos los sistemas, así como
  comprobando la trazabilidad de las operaciones en todos los módulos
  implicados**

**Resultados de la validación del paso:**

Se verifica la conectividad entre todos los sistemas, partiendo desde
los sistemas de captura de fuentes externas (blockchain y otras
fuentes), pasando por el módulo de datalake y gestion de reglas, y las
capacidades de conexión y accesibilidad desde el frontal web.

## PE3-0009.01 - Generación de alerta

Ante un eventual matching o identificación de patrón sospechoso. El
sistema generará una alerta. Esta alerta incluirá la información
asociada al matching, así como cualquier otro tipo de información
asociado como puede ser: Información genérica sobre el hallazgo
Información de acciones correctivas de acuerdo a lo establecido por el
equipo gestor de la herramienta a traves de la propia aplicación web.
Este caso de verificación se ha dividido en varios sub elementos de
acuerdo a las propias capacidades de gestión de reglas dentro de la
aplicación y el soporte a las distintas blockchains. Permitiendo así
tener una visión lo más amplia posible de las capacidades reales del
sistema. En cada uno de los test de realizará la verificación de la
creación de la regla de identificación del caso, que incluye los
parámetros propios de la inteligencia artificial; luego la propia
ejecución del sistema, y por último la generación de la alerta y su
visualización dentro del componente web de la solución.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680886 .anchor}Tabla 1 -- PE3-0009.01 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Cuando en un bloque de la blockchain aparece una dirección
  que ha sido categorizada previamente en Neo4j como maliciosa u otra
  categoría relevante, se genera una alerta**

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con información sobre el
bloque, la dirección y la categoría asignada en Neo4j.

**Evidencia**

![[]{#_Toc222680794 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image64.jpeg){width="6.299212598425197in"
height="2.607049431321085in"}

![[]{#_Toc222680795 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image65.jpeg){width="6.299212598425197in"
height="3.027697944006999in"}

![[]{#_Toc222680796 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image66.jpeg){width="6.299212598425197in"
height="2.740240594925634in"}

![[]{#_Toc222680797 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image67.jpeg){width="6.299212598425197in"
height="2.7096609798775155in"}

![[]{#_Toc222680798 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image68.jpeg){width="6.299212598425197in"
height="2.64215113735783in"}

![[]{#_Toc222680799 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
1](media/image69.jpeg){width="6.299212598425197in"
height="2.942146762904637in"}

- **Paso 2: Cuando se realiza una inserción o actualización en Neo4j y
  se incluye una dirección con un flag específico (por ejemplo,
  malicious ), se genera una alerta**

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con los detalles del nodo
actualizado.

**Evidencia**

![[]{#_Toc222680800 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image70.jpeg){width="6.299212598425197in"
height="2.883205380577428in"}

![[]{#_Toc222680801 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image71.jpeg){width="6.299212598425197in"
height="2.764597550306212in"}

![[]{#_Toc222680802 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image72.jpeg){width="6.299212598425197in"
height="2.6145767716535433in"}

![[]{#_Toc222680803 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image73.jpeg){width="6.299212598425197in"
height="2.459141513560805in"}

![[]{#_Toc222680804 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image74.jpeg){width="6.299212598425197in"
height="2.682683727034121in"}

![[]{#_Toc222680805 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
2](media/image75.jpeg){width="6.299212598425197in"
height="2.6104844706911634in"}

- **Paso 3: Detectar cuando todo el saldo de una cuenta monitorizada se
  transfiere fuera, dejando la cuenta en cero**

Se generará la alerta correspondiente.

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con información sobre la
dirección y la transacción

**Evidencia**

![[]{#_Toc222680806 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
3](media/image76.jpeg){width="6.299212598425197in"
height="3.206441382327209in"}

![[]{#_Toc222680807 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
3](media/image77.jpeg){width="6.299212598425197in"
height="2.514971566054243in"}

![[]{#_Toc222680808 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
3](media/image78.jpeg){width="6.299212598425197in"
height="2.8005030621172353in"}

![[]{#_Toc222680809 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
3](media/image79.jpeg){width="6.299212598425197in"
height="2.712315179352581in"}

- **Paso 4: Detectar transferencias inusualmente altas desde una cuenta
  monitorizada, que exceden un porcentaje definido del saldo total**

Se generará una alerta.

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta con información sobre la
transacción y el porcentaje transferido.

**Evidencia**

![[]{#_Toc222680810 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image80.jpeg){width="6.299212598425197in"
height="2.909304461942257in"}

![[]{#_Toc222680811 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image81.jpeg){width="6.299212598425197in"
height="2.989580052493438in"}

![[]{#_Toc222680812 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image82.jpeg){width="6.299212598425197in"
height="2.4256167979002625in"}

![[]{#_Toc222680813 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image83.jpeg){width="6.299212598425197in"
height="2.7996500437445317in"}

![[]{#_Toc222680814 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image84.jpeg){width="6.299212598425197in"
height="1.469323053368329in"}

![[]{#_Toc222680815 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
4](media/image85.jpeg){width="6.299212598425197in"
height="2.7645100612423446in"}

- **Paso 5: Detectar patrones de transferencias peeling chain desde una
  dirección monitoreada**

**Resultados de la validación del paso:**

Se comprueba la generación de una alerta indicando el patrón detectado
en base a una regla Peeling Chain.

**Evidencia**

![[]{#_Toc222680816 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
5](media/image86.jpeg){width="6.299212598425197in"
height="3.1384372265966753in"}

![[]{#_Toc222680817 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
5](media/image87.jpeg){width="6.299212598425197in"
height="3.0435225284339458in"}

![[]{#_Toc222680818 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
5](media/image88.jpeg){width="6.299212598425197in"
height="2.7324146981627297in"}

![[]{#_Toc222680819 .anchor}Ilustración 1 - PE3-0009.01 Evidencia Paso
5](media/image89.jpeg){width="6.299212598425197in"
height="2.7675590551181104in"}

- **Paso 6: En la monitorización en tiempo de real de las blokchain si
  se detecta la interación aguas abajo en un límite de saltos definido,
  de una address monitorizada con addresses catalogadas como maliciosas
  en nuestra Neo4j, o con addresses para las que la ia nos haya dado una
  alta predicción de estar involucradas en operaciones de malware, se
  generará la alerta pertinente**

**Resultados de la validación del paso:**

Se comprueba que se ha generado la alerta, con información de la
jerarquía de saltos hasta llegar a interaccionar con la address o
addresses maliciosas. La address maliciosa se catalogará conmo maliciosa
o proveniente de prediccion de la ia.

## PE3-0009.02 - Simulación de alerta

Se generará la cadena de entrada necesaria para que el sistema basado en
IA genere una alerta. se validará que se generan las notificaciones
establecidas por el usuario con la información para identificar origen,
como se ha generado, los criterios que la han elevado, transacciones,
wallets, actores etc. Verificar existencia logs de auditoría. Ejecución
controlada y supervisada del sistema, demostrando la capacidad de
generar alertas en base a unos criterios y mecanismos establecidos. Este
mecanismos permitirá evaluar las capacidades del sistema para la
creación de alertas, así como su trazabilidad y seguimiento del sistema.
Tambien se considerará la capacidad de verificar que los usuarios
finales correspondientes reciben una notificación de acuerdo a las
configuraciones establecidas.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680887 .anchor}Tabla 1 -- PE3-0009.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Establecer el marco temporal requerido para efectuar la
  simulación**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680820 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
1](media/image90.jpeg){width="6.299212598425197in"
height="3.063588145231846in"}

- **Paso 2: Ejecutar la carga de información de manera controlada**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680821 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
2](media/image91.jpeg){width="6.299212598425197in"
height="3.196909448818898in"}

- **Paso 3: El sistema tendrá que mostrar la capacidad para identificar
  el patrón mediante mecanismos de IA**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680822 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
3](media/image92.jpeg){width="6.299212598425197in"
height="2.8517629046369204in"}

- **Paso 4: El sistema generará la alerta, en base al output
  proporcionado por el módulo de inteligencia artificial, y en base a la
  regla de negocio que corresponda**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680823 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
4](media/image93.jpeg){width="6.299212598425197in"
height="3.139491469816273in"}

![[]{#_Toc222680824 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
4](media/image94.jpeg){width="6.299212598425197in"
height="2.601415135608049in"}

- **Paso 5: La alerta será reportada al usuario y se permitirá su
  visualizacion y gestion**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680825 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
5](media/image95.jpeg){width="6.299212598425197in"
height="2.452671697287839in"}

![[]{#_Toc222680826 .anchor}Ilustración 1 - PE3-0009.02 Evidencia Paso
5](media/image96.jpeg){width="6.299212598425197in"
height="2.445653980752406in"}

## PE3-0009.03 - Descarte de alertas

Los usuarios tendrán la capacidad de descartar alertas en base a sus
criterios y tras un análisis de la misma. Un analista, tras observar la
información proporcionada por el sistema de inteligencia artificial, y
junto con otros parámetros como puede ser la información disponible
sobre las direcciones, así como la información relativa a las relaciones
de las direcciones y las transacciones, puede decidir que esa alerta
corresponde con un falso positivo. En ese caso tiene la capacidad de
marcarla como descartada en la propia aplicación.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680888 .anchor}Tabla 1 -- PE3-0009.03 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Tras la creación de una alerta esta quedará en estado
  creada**

**Resultados de la validación del paso:**

Se verifica que la alerta se encuentra en el estado inicial de creada,
pendiente de su gestión. Esta información es observable desde el listado
de alertas, donde también se dispone de la capacidad de filtrar por este
estado, así como ordenarlas por fecha para facilitar la propia gestión.

**Evidencia**

![[]{#_Toc222680827 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
1](media/image97.jpeg){width="6.299212598425197in"
height="2.3592705599300086in"}

- **Paso 2: El usuario tendrá la capacidad de acceder al detalle y
  revisar la información proporcionada por el motor de reglas, junto con
  el detalle proporcionado por la propia inteligencia artificial**

**Resultados de la validación del paso:**

El usuario tiene la capacidad de visualizar la información procedente
del motor de reglas.

**Evidencia**

![[]{#_Toc222680828 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
2](media/image98.jpeg){width="6.299212598425197in"
height="1.6730402449693789in"}

- **Paso 3: El usuario también tiene la capacidad de acceder al detalle
  de la regla de monitorización**

**Resultados de la validación del paso:**

El operador puede ser la información que se estableció durante la fase
de creación de la regla.

**Evidencia**

![[]{#_Toc222680829 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
3](media/image99.jpeg){width="6.299212598425197in"
height="1.1872561242344708in"}

- **Paso 4: El usuario, tiene la capacidad de añadir comentarios a la
  alerta, de acuerdo a sus propios criterios y observaciones**

**Resultados de la validación del paso:**

Se verifica que el sistema permite la inclusión de comentarios, así como
su visualización cronológica.

**Evidencia**

![[]{#_Toc222680830 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
4](media/image98.jpeg){width="6.299212598425197in"
height="1.6730402449693789in"}

- **Paso 5: El usuario tiene la capacidad de marcar la alerta como
  desestimada**

**Resultados de la validación del paso:**

El usuario tiene la capacidad de cambiar el estado de la alerta a
desestimada a traves de las opciones de cambio de estado.

**Evidencia**

![[]{#_Toc222680831 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
5](media/image100.jpeg){width="6.299212598425197in"
height="2.3500699912510936in"}

- **Paso 6: A partir de ese punto, la alerta se queda en ese estado,
  pudiendo ser filtrada de los listado de reglas que se muestran en el
  módulo de alertas**

**Resultados de la validación del paso:**

Posibilidad de filtrarla de los listados

**Evidencia**

![[]{#_Toc222680832 .anchor}Ilustración 1 - PE3-0009.03 Evidencia Paso
6](media/image101.jpeg){width="6.299212598425197in"
height="1.2157075678040246in"}

## PE3-0009.04 - Histórico de una alerta

Se verificará que ante un cambio en la alerta, el histórico mostrará
información sobre el cambio, así como el usuario o subsistema que ha
realizado el cambio.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0005          Monitorización continua

  OBJ-0004          Capacidad de Simulación y generación de datos
                    sintéticos para simular

  ESF-0028          Analisis y diseño de motor de eventos a partir de
                    operaciones generadas en las blockchains
  -----------------------------------------------------------------------

  : []{#_Toc222680889 .anchor}Tabla 1 -- PE3-0009.04 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Evaluar la capacidad del sistema de generar una alerta**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680833 .anchor}Ilustración 1 - PE3-0009.04 Evidencia Paso
1](media/image102.jpeg){width="6.299212598425197in"
height="3.1715551181102364in"}

- **Paso 2: Revisar las capacidad de actualizacion de una alerta en base
  a la recopilacion de nuevos datos, ya sea dentro de la blockchain o
  por el sistema de enriquecimiento de información**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680834 .anchor}Ilustración 1 - PE3-0009.04 Evidencia Paso
2](media/image103.jpeg){width="6.299212598425197in"
height="3.053080708661417in"}

- **Paso 3: Revisar los criterios de notificacion al usuario
  (principalmente por el UI) relativo a cualquier tipo de actualizacion
  que se realice de una alerta**

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680835 .anchor}Ilustración 1 - PE3-0009.04 Evidencia Paso
3](media/image104.jpeg){width="6.299212598425197in"
height="3.1995997375328082in"}

- **Paso 4:**

**Resultados de la validación del paso:**

## PE3-0010 - Gestión de Wallets

Uno de los aspectos más importantes de este sistema es la capacidad de
gestionar los wallets monitorizados. Las direcciones a gestionar
dependerán de las necesidades de gestión y supervisión que se
establezcan en la herramienta. Así en el caso de una entidad de gestión
financiera de wallets  puede corresponder con las direcciones de cuentas
de sus propios clientes. En el caso de otro tipo de entidad dedicada a
la gestión de la seguridad puede estar relacionada con direcciones sobre
las que se tienen sospechas sobre tu finalidad. El objetivo de esta
capacidad de gestión de direcciones es múltiple, por un lado la de
enumeración, proporcionando un sistema claro y sencillo para la gestión
de la información requerida, y por el otro la de definir el scope de
elementos que luego se podrá emplear para la monitorización del sistema.
Este sistema de gestión de wallets se divide en diversos elementos:
Gestión de entidades o clientes, donde es posible gestionar las
identidades de los propietarios o gestores principales de las
direcciones. Esta vista incluye capacidades para gestionar y monitorizar
el estado de estas entidades de acuerdo a las capacidades de este
sistema. Gestión de wallets, donde es posible visualizar y gestionar el
listado de direcciones, así como acceder a su detalle y mostrar la
información disponible en la blockchain. Dentro de este caso de
verificación se hace una revisión de las capacidades de gestión dentro
del listado de wallets.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0008          Interface de usuario para investigación de casos e
                    Interoperabilidad

  OBJ-0003          Agrupación inteligente de información

  ESF-0001          Desarrollo POC de aplicación web
  -----------------------------------------------------------------------

  : []{#_Toc222680890 .anchor}Tabla 1 -- PE3-0010 Elementos relacionados

**Script de validación:**

- **Paso 1: Nos logamos en el portal y accedemos al panel \"Adresses\"**

**Resultados de la validación del paso:**

Listado o panel de addreses, donde podemos gestionarlas. Ahí también
tenemos la posibilidad de crear una address nueva \"Add address\"

**Evidencia**

![[]{#_Toc222680836 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
1](media/image105.jpeg){width="6.299212598425197in"
height="3.2283464566929134in"}

- **Paso 2: Pulsamos en el botón de acción \"Add Adress\"**

**Resultados de la validación del paso:**

Formulario de creación de una nueva address

**Evidencia**

![[]{#_Toc222680837 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
2](media/image106.jpeg){width="6.299212598425197in"
height="3.0787489063867017in"}

- **Paso 3: Introducimos los valores de network (BTC, ETH, POL), address
  e identity**

Despues click en \"finish and send\"

**Resultados de la validación del paso:**

Nueva Address generada

**Evidencia**

![[]{#_Toc222680838 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
3](media/image107.jpeg){width="6.299212598425197in"
height="1.4161625109361329in"}

- **Paso 4: Buscar address mediante los diferentes filtros del panel :
  address, network, identity**

**Resultados de la validación del paso:**

Listado con la address o addresses que cumplen con el filtro
seleccionado

**Evidencia**

![[]{#_Toc222680839 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
4](media/image107.jpeg){width="6.299212598425197in"
height="1.4161625109361329in"}

- **Paso 5: Seleccionar visualización de una address en el listado**

**Resultados de la validación del paso:**

Panel con la información de la address seleccionada : Balance, network,
listado de transacciones de la address y posibilidad de añadir
comentarios con información relevante de la address

**Evidencia**

![[]{#_Toc222680840 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
5](media/image108.jpeg){width="6.299212598425197in"
height="3.4831856955380576in"}

- **Paso 6: Consultar transacciones de una address en visualización**

**Resultados de la validación del paso:**

Panel con información especifica de la transaccion seleccionada, como
inputs, outputs, hash, fecha.

**Evidencia**

![[]{#_Toc222680841 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
6](media/image109.jpeg){width="6.299212598425197in"
height="3.2349081364829395in"}

- **Paso 7: Editar una address desde el listado o panel de addresses**

**Resultados de la validación del paso:**

Panel de edición de address, con posibilidad de modificación de address
y network.

**Evidencia**

![[]{#_Toc222680842 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
7](media/image110.jpeg){width="6.299212598425197in"
height="3.142448600174978in"}

- **Paso 8: Edición de address para modificar su identity**

**Resultados de la validación del paso:**

Panel para modificar/añadir exculisivamente el identity de la address

**Evidencia**

![[]{#_Toc222680843 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
8](media/image111.jpeg){width="6.299212598425197in"
height="3.0598151793525807in"}

- **Paso 9: Seleccionar la opción de borrar identity en una de las
  addresses del listado del panel**

**Resultados de la validación del paso:**

Esta acción elimina la identity de la address que podemos comprobar el
en listado buscando la address concreta.

**Evidencia**

![[]{#_Toc222680844 .anchor}Ilustración 1 - PE3-0010 Evidencia Paso
9](media/image112.jpeg){width="6.299212598425197in"
height="3.0543700787401575in"}

## PE3-0010.01 - Elementos Wallet

Dentro de la vista de detalle, existirá la posibilidad de navegar a
otros elementos que se encuentren relacionados. Por ejemplo se mostrará
la relación con actores.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0008          Interface de usuario para investigación de casos e
                    Interoperabilidad

  OBJ-0003          Agrupación inteligente de información

  ESF-0001          Desarrollo POC de aplicación web
  -----------------------------------------------------------------------

  : []{#_Toc222680891 .anchor}Tabla 1 -- PE3-0010.01 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Acceso al explorer del data-lake**

**Resultados de la validación del paso:**

Se carga la pantalla de inicio del explorador

**Evidencia**

![[]{#_Toc222680845 .anchor}Ilustración 1 - PE3-0010.01 Evidencia Paso
1](media/image113.jpeg){width="6.299212598425197in"
height="2.8952274715660544in"}

- **Paso 2: Iniciamos la busqueda con start**

**Resultados de la validación del paso:**

Se presentan los filtros de busqueda para que en nuestro caso podamos
buscar por wallet o address.

**Evidencia**

![[]{#_Toc222680846 .anchor}Ilustración 1 - PE3-0010.01 Evidencia Paso
2](media/image114.jpeg){width="6.299212598425197in"
height="2.529844706911636in"}

- **Paso 3: Lanzamos busqueda por wallet (
  bc1q5jz804r308ffel4vvmpm3ayerq7de4u7du00ax )**

**Resultados de la validación del paso:**

Se muestra la address de busqueda, y en ese caso su relación con
actor/actores.

**Evidencia**

![[]{#_Toc222680847 .anchor}Ilustración 1 - PE3-0010.01 Evidencia Paso
3](media/image115.jpeg){width="6.299212598425197in"
height="2.8257524059492565in"}

## PE3-0010.02 - Wallets sospechosos

En el momento en el que un wallet se considere sospechoso, se generará
una alerta. El sistema permitirá lanzar búsquedas por Wallets que tengan
la marca de sospechosos. Dentro del detalle se mostrará una marca visual
para identificarlo como sospechoso, así como los criterios y flujos
seguimos para categorizarlo así.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0003          Correlación de información y descubrimiento
                    potenciado por inteligencia artificial

  OBJ-0003          Agrupación inteligente de información

  ESF-0024          Entrenamiento para la detección de patrones
                    sospechosos a partir de casos previamente analizados
  -----------------------------------------------------------------------

  : []{#_Toc222680892 .anchor}Tabla 1 -- PE3-0010.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Se accede al explorer del data lake**

**Resultados de la validación del paso:**

Pantalla de inicio del explorer

**Evidencia**

![[]{#_Toc222680848 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
1](media/image113.jpeg){width="6.299212598425197in"
height="2.8952274715660544in"}

- **Paso 2: Se inicia la busqueda cargando los filtros**

**Resultados de la validación del paso:**

Pantalla de filtros para la busqueda

**Evidencia**

![[]{#_Toc222680849 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
2](media/image114.jpeg){width="6.299212598425197in"
height="2.529844706911636in"}

- **Paso 3: Seleccionamos una busqueda actor lockbit sin filtro de
  suspicius level**

**Resultados de la validación del paso:**

Pantalla con filtros de busqueda aplicados

**Evidencia**

![[]{#_Toc222680850 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
3](media/image116.jpeg){width="6.299212598425197in"
height="2.942902449693788in"}

- **Paso 4: Se lanza la busqueda para el filtro seleccionado**

**Resultados de la validación del paso:**

Se muestra el actor con todas sus addresse relacionadas

**Evidencia**

![[]{#_Toc222680851 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
4](media/image117.jpeg){width="6.299212598425197in"
height="2.810216535433071in"}

- **Paso 5: Seleccionamos una busqueda actor lockbit con filtro de
  suspicius level para addresses relacionadas**

**Resultados de la validación del paso:**

Pantalla con filtros de busqueda aplicados

**Evidencia**

![[]{#_Toc222680852 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
5](media/image118.jpeg){width="6.299212598425197in"
height="2.845133420822397in"}

- **Paso 6: Se lanza la busqueda para el filtro seleccionado**

**Resultados de la validación del paso:**

Se muestra el actor con todas sus addresse relacionadas con el filtro de
suspicius level aplicado

**Evidencia**

![[]{#_Toc222680853 .anchor}Ilustración 1 - PE3-0010.02 Evidencia Paso
6](media/image119.jpeg){width="6.299212598425197in"
height="2.9174606299212598in"}

## PE3-0011 - Gestión de incidentes

Verificar la capacidad de un usuario de generar un informe sobre un caso
concreto. Comprobar que solo este usuario puede acceder al informe y
solo el puede modificarlo en primera instancia. Verificar que el usuario
tiene capacidad para compartir el informe y así darle acceso a otros
usuarios de la herramienta. Para su mejor gestión, este caso de prueba
se subdividide en los dos casos principales: creación de un incidente a
traves del frontal web, o la creación a traves del escalado de una
alerta publicada. Estos dos flujos presentan características propias y
singulares que deben ser tratadas como dos casos independientes.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0006          Reporting, investigación y soporte a operativas de
                    servicio

  ESF-0005          Sistema para la consulta del modelo de datos, y
                    generacion/gestion de informes por parte del equipo
                    de analistas.

  PE3-0011.01       Gestión de incidentes: Desde listado de incidentes

  PE3-0011.02       Gestión de incidentes: Escalado de alerta
  -----------------------------------------------------------------------

  : []{#_Toc222680893 .anchor}Tabla 1 -- PE3-0011 Elementos relacionados

**Script de validación:**

- **Paso 1: 1a - Se crea un Incidente en el portal Web**

Para ello se selecciona el tipo (ransomeware, spyware, otros), se
selecciona el cliente del incidente, la address y protocolo (BTC, ETH,
POL) y la descripción detallando el incidente.

**Resultados de la validación del paso:**

Nuevo incidente que el usuario podrá modificar, compartir y podrá
generar un informe asociado a este incidente.

**Evidencia**

![[]{#_Toc222680854 .anchor}Ilustración 1 - PE3-0011 Evidencia Paso
1](media/image120.jpeg){width="6.299212598425197in"
height="3.1984765966754156in"}

- **Paso 2: 1b - Sobre el incidente anterior, en primera instancia, solo
  asignado a usuario que lo crea**

Este usuario tendrá capacidad de modificarlo y compartirlo.

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680855 .anchor}Ilustración 1 - PE3-0011 Evidencia Paso
2](media/image121.jpeg){width="6.299212598425197in"
height="3.0564020122484687in"}

- **Paso 3: 2a - Creacion de un incidente desde la edición de una alerta
  publicada**

Para ello se accede a la alerta y se crea el incidente desde \"Escalar
Incidente\". Se selecciona el el tipo (ransomeware, spyware, otros), se
selecciona el cliente del incidente y se añade la descripción detallando
el incidente asociado a la alerta. La address y el protocolo vendrán de
la propia alerta desde la que se genera el incidente.

**Resultados de la validación del paso:**

Nuevo incidente que el usuario podrá modificar, compartir y podrá
generar un informe asociado a este incidente.

**Evidencia**

![[]{#_Toc222680856 .anchor}Ilustración 1 - PE3-0011 Evidencia Paso
3](media/image122.jpeg){width="6.299212598425197in"
height="3.562852143482065in"}

- **Paso 4: 2b - Sobre el incidente anterior, en primera instancia, solo
  asignado a usuario que lo crea**

Este usuario tendrá capacidad de modificarlo y compartirlo.

**Resultados de la validación del paso:**

**Evidencia**

![[]{#_Toc222680857 .anchor}Ilustración 1 - PE3-0011 Evidencia Paso
4](media/image123.jpeg){width="6.299212598425197in"
height="3.6255030621172355in"}

## PE3-0011.01 - Gestión de incidentes: Desde listado de incidentes

Verificar la capacidad de un usuario de generar un informe sobre un caso
concreto a partir de la creación desde el listado de incidentes.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0006          Reporting, investigación y soporte a operativas de
                    servicio

  ESF-0005          Sistema para la consulta del modelo de datos, y
                    generacion/gestion de informes por parte del equipo
                    de analistas.

  PE3-0011          Gestión de incidentes

  PE3-0011.02       Gestión de incidentes: Escalado de alerta
  -----------------------------------------------------------------------

  : []{#_Toc222680894 .anchor}Tabla 1 -- PE3-0011.01 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Un usuario con rol Operador, tendrá la capacidad de generar
  un nuevo incidente**

El punto de partida de un incidente puede ser una petición de cliente, o
el propia interés del propio analista en base a unas evidencias
obtenidas.

**Resultados de la validación del paso:**

Se verifica que el usuario tiene la capacidad de crear el incidente a
traves del propio listado de incidentes de la aplicación. En el mismo el
usuario dispone de un botón \"crear incidente\" que al pulsarlo se le
muestra un formulario para proceder a su alta.

**Evidencia**

![[]{#_Toc222680858 .anchor}Ilustración 1 - PE3-0011.01 Evidencia Paso
1](media/image124.jpeg){width="6.299212598425197in"
height="3.0697779965004375in"}

![[]{#_Toc222680859 .anchor}Ilustración 1 - PE3-0011.01 Evidencia Paso
1](media/image125.jpeg){width="6.299212598425197in"
height="2.32666447944007in"}

- **Paso 2:**

**Resultados de la validación del paso:**

- **Paso 3:**

**Resultados de la validación del paso:**

## PE3-0011.02 - Gestión de incidentes: Escalado de alerta

Verificar la capacidad de un usuario de generar un informe sobre un caso
concreto a partir del escalado de una alerta.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0006          Reporting, investigación y soporte a operativas de
                    servicio

  ESF-0005          Sistema para la consulta del modelo de datos, y
                    generacion/gestion de informes por parte del equipo
                    de analistas.

  PE3-0011.01       Gestión de incidentes: Desde listado de incidentes

  PE3-0011          Gestión de incidentes
  -----------------------------------------------------------------------

  : []{#_Toc222680895 .anchor}Tabla 1 -- PE3-0011.02 Elementos
  relacionados

**Script de validación:**

- **Paso 1: Un usuario son rol Operador, tendrá la capacidad de generar
  un nuevo incidente**

El punto de partida en este caso será el escalado de una alerta
disponible en el sistema. Esta alerta, se podrá haber generado de manera
automática a traves del motor de reglas, de acuerdo a la configuración
establecida por la regla, y las características de la inteligencia
artificial.

**Resultados de la validación del paso:**

Nuevo incidente que el usuario podrá modificar, compartir y podrá
generar un informe asociado a este incidente.

**Evidencia**

![[]{#_Toc222680860 .anchor}Ilustración 1 - PE3-0011.02 Evidencia Paso
1](media/image126.jpeg){width="6.299212598425197in"
height="3.2251443569553806in"}

![[]{#_Toc222680861 .anchor}Ilustración 1 - PE3-0011.02 Evidencia Paso
1](media/image127.jpeg){width="6.299212598425197in"
height="3.2449496937882762in"}

## PE3-0012 - Gestión de activos

Será posible visualizar el detalle de activos: wallets, ips, actores,
países. Se podrá visualizar toda la metainformación generada por el
sistema relacionada con los activos. El sistema mostrará la información
almacenada en el datalake, así como la posibilidad de mostrar otros
elementos relacionados de acuerdo a la naturaleza del mismo.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0001          ingesta de información de blockchains

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  ESF-0013          Técnicas de indexación de información para consulta
                    óptima de información considerando volumetría

  ESF-0012          Estudio del almacenamiento de transacciones en bases
                    de datos NOSQL
  -----------------------------------------------------------------------

  : []{#_Toc222680896 .anchor}Tabla 1 -- PE3-0012 Elementos relacionados

**Script de validación:**

- **Paso 1: El usuario realizará una consulta para visualiza un
  determinado elemento**

**Resultados de la validación del paso:**

El usuario puede visualizar el elemento obtenido a partir del criterio
de busqueda que ha establecido.

**Evidencia**

![[]{#_Toc222680862 .anchor}Ilustración 1 - PE3-0012 Evidencia Paso
1](media/image128.jpeg){width="6.299212598425197in"
height="1.4161625109361329in"}

- **Paso 2: Una vez que el elemento es cargado, el usuario tendrá la
  capacidad de hacer una petición para recuperar su detalle**

**Resultados de la validación del paso:**

El sistema mostrará el detalle, con la informacion registrada en el
sistema para el mismo.

**Evidencia**

![[]{#_Toc222680863 .anchor}Ilustración 1 - PE3-0012 Evidencia Paso
2](media/image129.jpeg){width="6.299212598425197in"
height="3.4470898950131232in"}

- **Paso 3: Este detalle mostrará también la fecha de ultima
  actualización de los datos**

**Resultados de la validación del paso:**

El usuario podrá saber si la informacion se ha actualizado recientemente
o no.

**Evidencia**

![[]{#_Toc222680864 .anchor}Ilustración 1 - PE3-0012 Evidencia Paso
3](media/image130.jpeg){width="6.299212598425197in"
height="0.8311198600174978in"}

## PE3-0013 - Testing custodia de evidencias

Ante la detección de actividades potencialmente litigiosos y la
generación a través de los metadatos y trazas técnicas de una evidencia
digital se comprobará que la evidencia es custodiada durante el periodo
de años requerido por la ley. Se comprueba la integridad(la evidencia no
se corrompe ante recuperación de backup) autenticidad de la firma. El
sistema dispondrá de mecanismos para gestionar evidencias a partir del
análisis de un determinado caso bajo estudio. Luego, esta evidencia
podrá ser marcada para su gestión y tramitación por un custodio. Los
requisitos de gestión de custodia establecen que es necesario contar con
mecanismos para poder gestionar y garantizar la integridad y
autenticidad de la firma de un determinado documento. En este sentido la
herramienta tiene que facilitar el control de estos procedimientos, de
acuerdo con las capacidades establecidas por el custodio, ya sea en
forma de API o gestión manual de la información.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0001          ingesta de información de blockchains

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  ESF-0011          Comparativa de técnicas de almacenamiento de
                    transacciones en Datalake
  -----------------------------------------------------------------------

  : []{#_Toc222680897 .anchor}Tabla 1 -- PE3-0013 Elementos relacionados

**Script de validación:**

- **Paso 1: La aplicación permite generar un informe de custodia a
  partir de los datos gestionados dentro de un incidente**

**Resultados de la validación del paso:**

Se verifica que dentro de un incidente es posible generar un informe a
traves de las opciones que habilitan dicha opción.

**Evidencia**

![[]{#_Toc222680865 .anchor}Ilustración 1 - PE3-0013 Evidencia Paso
1](media/image131.jpeg){width="6.299212598425197in"
height="1.021020341207349in"}

- **Paso 2: El usuario tiene la capacidad de acceder al listado de
  informes**

**Resultados de la validación del paso:**

El usuario tiene la capacidad de acceder al listado y ver los informes
que actualmente existen

**Evidencia**

![[]{#_Toc222680866 .anchor}Ilustración 1 - PE3-0013 Evidencia Paso
2](media/image132.jpeg){width="6.299212598425197in"
height="1.731748687664042in"}

- **Paso 3: El usuario tiene la capacidad de seleccionar un informe y
  visualizarlo**

**Resultados de la validación del paso:**

Se observa como el usuario puede entrar en el detalle, visualizando los
campos y la información recogida en el informe.

**Evidencia**

![[]{#_Toc222680867 .anchor}Ilustración 1 - PE3-0013 Evidencia Paso
3](media/image133.jpeg){width="6.299212598425197in"
height="3.345281058617673in"}

- **Paso 4: El usuario puede cerrar y eliminar el informe previamente
  generado**

**Resultados de la validación del paso:**

Se observa que el usuario puede eliminar dicho informe.

**Evidencia**

![[]{#_Toc222680868 .anchor}Ilustración 1 - PE3-0013 Evidencia Paso
4](media/image134.jpeg){width="6.299212598425197in"
height="1.7679625984251968in"}

## PE3-0014 - Backups

Verificar que el backup se ejecuta con la debida frecuencia, con
garantía de integridad, que se cumple el periodo de retención
establecido. Verificar recuperación de backup y restablecimiento
sistema.

Elementos funcionales y no funcionales relacionados con esta prueba:

  -----------------------------------------------------------------------
  **Código**        **Título**
  ----------------- -----------------------------------------------------
  REQ-0001          ingesta de información de blockchains

  OBJ-0001          Captura, transformación y almacenamiento de
                    información procedente de las redes blockchain
                    seleccionadas (Bitcoin, Ethereum, Polygon)

  ESN-0007          Alta disponibilidad
  -----------------------------------------------------------------------

  : []{#_Toc222680898 .anchor}Tabla 1 -- PE3-0014 Elementos relacionados

**Script de validación:**

- **Paso 1: En AWS Backup se revisa el Vault Deloitte-backup-vault para
  comprobar que se ajusta al plan : frecuencia semanal, retención 7
  días**

Resources: instancias ec2 con el Tag Name=Deloitte y cluster rds con Tag
Name = Deloitte.

**Resultados de la validación del paso:**

Recovery Points : 5 imágenes para cada una de las instancias EC2. Un
snapshot del cluster Aurora - Mysql.

**Evidencia**

![[]{#_Toc210829001 .anchor}Ilustración 1 - PE3-0014 Evidencia Paso
1](media/image135.jpeg){width="6.299212598425197in"
height="1.8002482502187227in"}

- **Paso 2: Restore del recovery point, en este caso la image de una de
  las instancias EC2**

Se selecciona el recovery point, y se selecciona la accion restore. Todo
esto desde la consola AWS, AWS Backup, Vaults en la seccion Recovery
points de nuestro Vault.

**Resultados de la validación del paso:**

Nueva instancia levantada y operativa con el recovery point o backup
seleccionado.

- **Paso 3: Restore del recovery point, en este caso un snapshot del
  cluster Aurora**

Se selecciona el recovery point, y se selecciona la accion restore. Todo
esto desde la consola AWS, AWS Backup, Vaults en la seccion Recovery
points de nuestro Vault.

**Resultados de la validación del paso:**

Instancia Aurora corriendo y operativa con el snapshot recuperado.

# Conclusiones

En consecuencia, y tras la ejecución completa y satisfactoria de todas
las actividades de validación previstas para la etapa 3, puede afirmarse
que la plataforma ha alcanzado un nivel de solidez técnica y funcional
plenamente alineado con los requisitos definidos en las etapas previas
del proyecto. La correcta resolución de los 29 casos de verificación,
junto con la ejecución de 127 pasos unitarios y la recopilación de 106
evidencias, demuestra que el sistema opera con estabilidad, rendimiento
adecuado y plena integración entre sus componentes críticos.

Los resultados obtenidos confirman que los mecanismos de ingesta,
correlación, monitorización, análisis inteligente y gestión de eventos
funcionan de manera coherente y eficaz en un entorno relevante,
validando las hipótesis de diseño y los criterios de aceptación
establecidos. Asimismo, la plataforma ha mostrado consistencia operativa
bajo diferentes escenarios, incluyendo pruebas de carga, seguridad,
trazabilidad, monitorización continua y gestión avanzada de incidentes,
lo que evidencia su madurez para adoptar casos de uso reales con niveles
elevados de exigencia.

Gracias a esta consolidación técnica y funcional, y al comportamiento
observado durante todo el proceso de validación, puede concluirse que la
solución alcanza el **Nivel de Madurez Tecnológica TRL7**, demostrando
su capacidad para operar en un entorno próximo al real y evidenciando la
preparación necesaria para avanzar hacia las siguientes fases.

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

[]{#_Toc222675280 .anchor}ANEXO I. ÍNDICE de Requisitos

En la siguiente tabla se pueden observar un índice inverso de los casos
de prueba por requisito.

  -----------------------------------------------------------------------
  Código            Título
  ----------------- -----------------------------------------------------
  **REQ-0001**      **ingesta de información de blockchains**

                    PE3-0002: Seguridad global de la herramienta.

                    PE3-0003.02: Rendimiento ingesta datos

                    PE3-0012: Gestión de activos

                    PE3-0013: Testing custodia de evidencias

                    PE3-0014: Backups

  **REQ-0002**      **Enriquecimiento desde fuentes externas**

                    PE3-0002: Seguridad global de la herramienta.

                    PE3-0003: Carga y Volumetría

  **REQ-0003**      **Correlación de información y descubrimiento
                    potenciado por inteligencia artificial**

                    PE3-0002: Seguridad global de la herramienta.

                    PE3-0006: Capacidad de búsqueda

                    PE3-0006-03: Búsquedas por IP

                    PE3-0006.02: Búsquedas por Wallet

                    PE3-0010.02: Wallets sospechosos

  **REQ-0004**      **Trazabilidad y atribución potenciada por
                    inteligencia artificial**

                    PE3-0002: Seguridad global de la herramienta.

  **REQ-0005**      **Monitorización continua**

                    PE3-0007: Monitoreo wallets

                    PE3-0007.01: Monitorización de operación de entrada

                    PE3-0007.02: Monitorización de operación de salida

                    PE3-0008: Gestión de alertas

                    PE3-0009.01: Generación de alerta

                    PE3-0009.02: Simulación de alerta

                    PE3-0009.03: Descarte de alertas

                    PE3-0009.04: Histórico de una alerta

  **REQ-0006**      **Reporting, investigación y soporte a operativas de
                    servicio**

                    PE3-0011: Gestión de incidentes

                    PE3-0011.01: Gestión de incidentes: Desde listado de
                    incidentes

                    PE3-0011.02: Gestión de incidentes: Escalado de
                    alerta

  **REQ-0008**      **Interface de usuario para investigación de casos e
                    Interoperabilidad**

                    PE3-0003.01: Pruebas de rendimiento de usuario

                    PE3-0004: Opciones de menú disponibles

                    PE3-0004: Testing menú disponibles

                    PE3-0005: Capacidades de la landing

                    PE3-0010: Gestión de Wallets

                    PE3-0010.01: Elementos Wallet

  **REQ-0009**      **Gobierno del sistema**

                    PE3-0009: Monitorización

                    PE3-0003.02: Rendimiento ingesta datos

                    PE3-0012: Gestión de activos

                    PE3-0013: Testing custodia de evidencias

                    PE3-0014: Backups

  **REQ-0002**      **Enriquecimiento desde fuentes externas**

                    PE3-0002: Seguridad global de la herramienta.

                    PE3-0003: Carga y Volumetría

  **REQ-0003**      **Correlación de información y descubrimiento
                    potenciado por inteligencia artificial**

                    PE3-0002: Seguridad global de la herramienta.

                    PE3-0006: Capacidad de búsqueda

                    PE3-0006-03: Búsquedas por IP

                    PE3-0006.02: Búsquedas por Wallet

                    PE3-0010.02: Wallets sospechosos

  **REQ-0004**      **Trazabilidad y atribución potenciada por
                    inteligencia artificial**

                    PE3-0002: Seguridad global de la herramienta.

  **REQ-0005**      **Monitorización continua**

                    PE3-0007: Monitoreo wallets

                    PE3-0007.01: Monitorización de operación de entrada

                    PE3-0007.02: Monitorización de operación de salida

                    PE3-0008: Gestión de alertas

                    PE3-0009.01: Generación de alerta

                    PE3-0009.02: Simulación de alerta

                    PE3-0009.03: Descarte de alertas

                    PE3-0009.04: Histórico de una alerta

  **REQ-0006**      **Reporting, investigación y soporte a operativas de
                    servicio**

                    PE3-0011: Gestión de incidentes

                    PE3-0011.01: Gestión de incidentes: Desde listado de
                    incidentes

                    PE3-0011.02: Gestión de incidentes: Escalado de
                    alerta

  **REQ-0008**      **Interface de usuario para investigación de casos e
                    Interoperabilidad**

                    PE3-0003.01: Pruebas de rendimiento de usuario

                    PE3-0004: Opciones de menú disponibles

                    PE3-0004: Testing menú disponibles

                    PE3-0005: Capacidades de la landing

                    PE3-0010: Gestión de Wallets

                    PE3-0010.01: Elementos Wallet

  **REQ-0009**      **Gobierno del sistema**

                    PE3-0009: Monitorización
  -----------------------------------------------------------------------

  : []{#_Toc222680899 .anchor}Tabla 1 -- Relación de casos de prueba por
  requisito

[]{#_Toc222675281 .anchor}ANEXO II. HISTÓRICO DE MODIFICACIONES

  ---------------------------------------------------------------------------
   Versión     Fecha          Autor      Modificaciones
  --------- ------------ --------------- ------------------------------------
     0.1     22/07/2025     Deloitte     Primera versión del documento

     0.2     22/02/2026     Deloitte     Generación y revisión del documento

                                         

                                         

                                         

                                         

                                         

                                         
  ---------------------------------------------------------------------------

  : []{#_Toc133437760 .anchor}Tabla 1 -- Histórico de modificaciones
