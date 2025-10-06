# PROPUESTA DE TRABAJO FIN DE MÁSTER
## Máster Universitario en Ingeniería Informática
### Escuela Técnica Superior de Ingeniería - Universidad de Huelva

---

## INFORMACIÓN GENERAL

**Título del Proyecto:** DriveScore - Plataforma de Evaluación Social de Conducción para la Mejora de la Seguridad Vial

**Alumno:** Gamaliel Moreno Sánchez

**Director:** Dr. José Carpio Cañada  
Departamento de Tecnologías de la Información  
Área de Ciencias de la Computación

**Duración estimada:** 3 meses (12 ECTS - 300 horas)

**Curso académico:** 2024-2025

---

## RESUMEN EJECUTIVO

DriveScore es una plataforma tecnológica innovadora que aplica el concepto de evaluación social entre pares al ámbito de la conducción de vehículos. Inspirada en modelos exitosos como eBay, BlaBlaCar, Wallapop y CouchSurfing, esta aplicación permitirá a los conductores evaluarse mutuamente, creando así un sistema de reputación que incentive conductas responsables y seguras en las vías públicas.

El proyecto surge de una necesidad real: la dificultad de demostrar objetivamente el historial de conducción segura de un conductor, especialmente en situaciones administrativas como renovaciones de permisos de conducir. Más allá de resolver este problema particular, DriveScore aspira a transformar la cultura vial global mediante la aplicación del concepto de "aldea global digital", donde los conductores son conscientes de que sus acciones son observables y evaluables por la comunidad.

**Palabras clave:** Evaluación social, seguridad vial, gamificación, responsabilidad cívica, tecnología móvil, reconocimiento de matrículas, inteligencia artificial, software libre.

---

## 1. MOTIVACIÓN Y CONTEXTO

### 1.1. Origen del Proyecto

El proyecto DriveScore nace de una experiencia personal del director del proyecto, el Dr. José Carpio Cañada, quien tras 30 años de conducción sin accidentes se ha encontrado con barreras administrativas para renovar su permiso de conducir debido a una condición médica (Adrenoleucodistrofia ALD-X). A pesar de tener un historial impecable de conducción y encontrarse en proceso de recuperación, no existe un mecanismo objetivo que permita demostrar su competencia como conductor más allá de informes médicos.

Esta situación evidencia una carencia sistémica: **la ausencia de un sistema de acreditación positiva del comportamiento vial**.

### 1.2. El Problema Global de la Seguridad Vial

Según la Organización Mundial de la Salud:
- Los accidentes de tráfico causan aproximadamente 1.35 millones de muertes al año a nivel mundial
- Son la principal causa de muerte entre personas de 5 a 29 años
- El 90% de las muertes por accidentes de tráfico ocurren en países de ingresos bajos y medianos
- El costo económico global se estima en un 3% del PIB mundial

La mayoría de estos accidentes están relacionados con comportamientos evitables: exceso de velocidad, conducción agresiva, no respetar prioridades, distracciones al volante, etc.

### 1.3. El Anonimato como Factor de Riesgo

Múltiples estudios en psicología social han demostrado que el anonimato percibido incrementa comportamientos antisociales. En la carretera, este fenómeno se manifiesta en:
- Conducción agresiva
- Falta de cortesía vial
- No ceder el paso
- Infracciones deliberadas
- Comportamientos de riesgo

**Hipótesis central del proyecto:** Si los conductores supieran que sus acciones pueden ser evaluadas y que esta evaluación queda registrada en su perfil público, modificarían su comportamiento hacia prácticas más seguras y corteses.

### 1.4. Precedentes Exitosos de Evaluación Social

El éxito de plataformas basadas en la evaluación entre pares demuestra la viabilidad del concepto:

**eBay:** Sistema de reputación que ha permitido construir confianza en transacciones entre desconocidos, facilitando un mercado global de comercio electrónico C2C.

**BlaBlaCar:** Ha transportado a más de 100 millones de personas gracias a un sistema de evaluaciones mutuas que genera confianza entre conductores y pasajeros. El director del proyecto tiene experiencia personal como usuario con valoraciones positivas que certifican su calidad como conductor.

**Airbnb:** Ha revolucionado el sector del alojamiento mediante evaluaciones bidireccionales.

**Wallapop:** Ha creado confianza en transacciones locales de segunda mano.

Estos casos demuestran que:
1. Las personas modifican su comportamiento cuando saben que serán evaluadas
2. Los sistemas de reputación generan confianza y mejoran las interacciones
3. La presión social positiva puede escalar para generar cambios culturales significativos

---

## 2. MISIÓN, VISIÓN Y VALORES

### 2.1. Misión

Aportar los conocimientos tecnológicos y empresariales necesarios para desarrollar e implementar soluciones innovadoras que mejoren la vida de las personas, centrándose en la seguridad vial mediante la aplicación de tecnologías de evaluación social y gamificación.

### 2.2. Visión

Hacer que los ciudadanos del planeta conduzcan de manera más segura, cortés y responsable gracias al concepto de la "aldea global digital", donde las personas no son anónimas y están motivadas intrínsecamente a comportarse de manera ejemplar, creando así una cultura vial global basada en el respeto mutuo y la responsabilidad compartida.

### 2.3. Valores Fundamentales

**Honestidad:** Transparencia total en el funcionamiento del sistema, protección contra manipulaciones y valoraciones falsas, comunicación clara sobre el uso de datos.

**Cuidado del Planeta:** Reducción de accidentes y congestión vehicular que contribuye a menor contaminación. Promoción de conducción eficiente que reduce emisiones. Uso de infraestructura tecnológica sostenible y eficiente energéticamente.

**Tratar al Prójimo como a Ti Mismo:** Fomentar la empatía y cortesía en la carretera. Crear una comunidad que se cuida mutuamente. Promover el respeto por todos los usuarios de la vía (conductores, ciclistas, peatones).

**Optimización del Tiempo:** Utilizar software libre y herramientas existentes para maximizar la eficiencia del desarrollo. Enfoque ágil centrado en entregar valor rápidamente a los usuarios.

---

## 3. OBJETIVOS DEL PROYECTO

### 3.1. Objetivo General

Diseñar, desarrollar y validar una plataforma tecnológica móvil que permita a los conductores evaluarse mutuamente de forma segura, justa y verificable, creando así un sistema de reputación vial que incentive comportamientos responsables y contribuya a la mejora de la seguridad vial global.

### 3.2. Objetivos Específicos

#### Objetivos Técnicos:

1. **Desarrollar una aplicación móvil multiplataforma** utilizando tecnologías de software libre que permita:
   - Captura de imágenes de matrículas vehiculares
   - Reconocimiento automático de matrículas mediante IA
   - Sistema de evaluación con puntuación y comentarios
   - Visualización de perfil de reputación del conductor

2. **Implementar un sistema de reconocimiento de matrículas** basado en visión artificial y machine learning que funcione en condiciones reales de uso (diferentes ángulos, iluminación, distancias).

3. **Diseñar una arquitectura de backend escalable** que soporte:
   - Gestión de usuarios y autenticación segura
   - Almacenamiento y procesamiento de evaluaciones
   - Cálculo de puntuaciones de reputación
   - API REST para la comunicación con la aplicación móvil

4. **Establecer mecanismos de verificación** para prevenir:
   - Evaluaciones fraudulentas
   - Acoso o uso malintencionado
   - Manipulación del sistema de puntuación
   - Suplantación de identidad

5. **Implementar un sistema de gamificación** que incluya:
   - Niveles de reputación
   - Insignias por comportamientos ejemplares
   - Ranking de conductores responsables
   - Estadísticas personales y comparativas

#### Objetivos de Investigación y Análisis:

6. **Realizar un estudio de viabilidad técnica y económica** que analice:
   - Tecnologías disponibles y su idoneidad
   - Costos de infraestructura y mantenimiento
   - Modelos de monetización sostenibles
   - Análisis competitivo

7. **Analizar el marco legal y normativo** aplicable:
   - Cumplimiento con GDPR y protección de datos
   - Regulaciones sobre captura de imágenes en vía pública
   - Aspectos legales de la evaluación de terceros
   - Propiedad intelectual y licenciamiento

8. **Diseñar una estrategia de adopción y escalabilidad** que contemple:
   - Plan de lanzamiento y piloto inicial
   - Estrategias de crecimiento de usuarios
   - Alianzas estratégicas (DGT, aseguradoras, fabricantes)
   - Expansión internacional

#### Objetivos de Validación:

9. **Desarrollar un prototipo funcional (MVP)** en el primer mes que pueda ser probado por usuarios reales.

10. **Realizar pruebas de usabilidad y aceptación** con un grupo piloto de usuarios, recopilando feedback para mejoras iterativas.

11. **Validar las hipótesis del proyecto** sobre el cambio de comportamiento de los conductores mediante métricas cuantitativas y cualitativas.

---

## 4. ESTADO DEL ARTE Y ANÁLISIS COMPETITIVO

### 4.1. Aplicaciones de Monitoreo de Conducción

Existen varias aplicaciones en el mercado que monitorizan hábitos de conducción, pero con enfoques diferentes a DriveScore:

#### **TrueMotion / TrueMotion Family**
- **Enfoque:** Monitoreo individual mediante sensores del smartphone
- **Funcionalidad:** Calcula puntuaciones basadas en velocidad, frenadas, uso del móvil
- **Uso:** Principalmente para descuentos en seguros y comparativas familiares
- **Limitación:** No incluye evaluación social por otros conductores

#### **EverDrive / DriveWell (Cambridge Mobile Telematics)**
- **Enfoque:** Telemática y scoring individual
- **Funcionalidad:** Registra comportamientos y entrega un "Drive score"
- **Uso:** Competición dentro de comunidades cerradas, integración con aseguradoras
- **Limitación:** Sistema cerrado, sin evaluación abierta entre conductores

#### **Zendrive**
- **Enfoque:** B2B, "Mobility Risk Intelligence"
- **Funcionalidad:** SDKs para integración en apps, métricas para empresas/flotas
- **Limitación:** Orientado a empresas, no a consumidores finales

#### **Hum by Verizon**
- **Enfoque:** Dispositivo OBD + app
- **Funcionalidad:** Safety Score semanal, compartir con familia
- **Limitación:** Requiere hardware adicional, enfoque familiar cerrado

#### **Metromile**
- **Enfoque:** Aseguradora "pay-per-mile"
- **Funcionalidad:** Análisis de conducción para descuentos
- **Limitación:** Limitado a clientes de seguro

#### **BlaBlaCar**
- **Enfoque:** Compartir coche para viajes largos
- **Funcionalidad:** Sistema de evaluaciones entre conductores y pasajeros
- **Diferencia con DriveScore:** Limitado a usuarios que comparten coche, no evalúa comportamiento general en carretera

### 4.2. Análisis de Gaps y Oportunidades

**Ninguna de las soluciones existentes combina:**
1. Evaluación social abierta entre conductores (sin necesidad de interacción previa)
2. Enfoque en comportamiento vial general (no solo telemática personal)
3. Democratización del acceso (solo requiere smartphone)
4. Visión de comunidad global (no limitada a seguros o grupos cerrados)
5. Reconocimiento automático de vehículos para facilitar evaluaciones

**DriveScore se diferencia por:**
- **Apertura:** Cualquier conductor puede evaluar a cualquier otro
- **Universalidad:** No requiere relación previa (vs. BlaBlaCar) ni hardware adicional
- **Foco social:** Prioriza el cambio cultural sobre la telemática individual
- **Reconocimiento IA:** Facilita la evaluación mediante identificación automática de matrículas
- **Transparencia:** Perfil público de reputación vial

### 4.3. Waze como Referencia de Red Social Vial

**Waze** es el ejemplo más exitoso de red social aplicada al tráfico:
- 140 millones de usuarios activos
- Compartición de información en tiempo real (accidentes, policía, obstáculos)
- Gamificación (puntos, rangos, logros)
- Comunidad colaborativa

**Aprendizajes de Waze para DriveScore:**
- La gamificación funciona para engagement en contextos de conducción
- Los usuarios están dispuestos a contribuir información si ven beneficios
- La comunidad puede autoregularse con buenos mecanismos
- La integración simple (solo app móvil) facilita adopción masiva

---

## 5. METODOLOGÍA DE DESARROLLO

### 5.1. Marco Metodológico: Desarrollo Ágil Centrado en el Usuario

El proyecto adoptará una metodología híbrida basada en:

**Lean Startup:**
- Construir → Medir → Aprender
- MVP (Minimum Viable Product) en el primer mes
- Iteraciones rápidas basadas en feedback real

**Scrum Adaptado:**
- Sprints de 2 semanas
- Revisiones continuas con director
- Retrospectivas para mejora continua

**Design Thinking:**
- Empatía con usuarios (conductores, peatones, ciclistas)
- Prototipado rápido
- Testeo con usuarios reales

### 5.2. Principios de Desarrollo

1. **Software Libre First:** Priorizar herramientas y frameworks open source
2. **Cloud Native:** Arquitectura cloud para escalabilidad y costos bajos
3. **Mobile First:** Diseño prioritario para dispositivos móviles
4. **API First:** Arquitectura desacoplada que facilite futuras integraciones
5. **Privacy by Design:** Protección de datos desde el diseño inicial
6. **Continuous Deployment:** Entregas continuas al entorno de pruebas

### 5.3. Stack Tecnológico Propuesto (Software Libre)

#### Frontend - Aplicación Móvil:
- **Flutter** o **React Native**: Desarrollo multiplataforma (iOS/Android)
- **Expo** (si React Native): Acelera desarrollo y testing
- Justificación: Reducir tiempo de desarrollo al 50% vs. apps nativas separadas

#### Backend:
- **Node.js** con **Express** o **FastAPI** (Python): APIs REST
- **PostgreSQL** o **MongoDB**: Base de datos
- **Neo4j** (gratuito): Para análisis de grafos sociales (opcional)
- Justificación: Ecosistemas maduros con amplia comunidad y documentación

#### Reconocimiento de Matrículas (OCR + IA):
- **OpenALPR** (open source): Reconocimiento de matrículas
- **Tesseract OCR**: Alternativa open source
- **TensorFlow Lite** o **ONNX Runtime**: Inferencia en dispositivo móvil
- **YOLO** o **EasyOCR**: Detección y reconocimiento
- Justificación: Soluciones probadas con alta precisión, ejecutables en móvil

#### Infraestructura Cloud (Capa Gratuita):
- **Vercel**: Hosting frontend y funciones serverless
- **Google Cloud Platform** / **AWS Free Tier**: Servicios cloud
- **Cloudflare**: CDN, seguridad y optimización
- **Supabase** o **Firebase**: Backend as a Service (BaaS)
- Justificación: Capas gratuitas generosas, escalabilidad automática

#### Autenticación y Seguridad:
- **OAuth 2.0** con **Auth0** o **Supabase Auth**
- **JWT** para tokens
- Cifrado end-to-end para datos sensibles

#### DevOps y CI/CD:
- **GitHub Actions**: Integración continua
- **Docker**: Contenedorización
- **GitHub**: Control de versiones y colaboración

#### Analytics y Monitoreo:
- **Plausible** o **Matomo**: Analytics respetando privacidad
- **Sentry**: Monitoreo de errores
- **Grafana** + **Prometheus**: Monitoreo de infraestructura

---

## 6. PLAN DE TRABAJO Y CRONOGRAMA

### 6.1. Estructura Temporal (3 meses)

El proyecto se divide en 3 fases principales de 1 mes cada una, con entregables concretos y validación continua con usuarios.

---

### **MES 1: INVESTIGACIÓN, DISEÑO Y MVP**

#### **Semana 1-2: Investigación y Análisis**
**Actividades:**
- Revisión bibliográfica sobre seguridad vial y cambio de comportamiento
- Análisis exhaustivo del marco legal (GDPR, protección de datos, imagen)
- Estudio de tecnologías de reconocimiento de matrículas (benchmarking)
- Entrevistas con usuarios potenciales (conductores, expertos en tráfico)
- Análisis de apps competidoras (pruebas prácticas)
- Consulta con experto en protección de datos

**Entregables:**
- Estado del arte documentado
- Análisis legal preliminar
- Informe de análisis competitivo
- Especificación de requisitos funcionales y no funcionales
- Documento de arquitectura del sistema

#### **Semana 3-4: Diseño y Desarrollo del MVP**
**Actividades:**
- Diseño de experiencia de usuario (wireframes, mockups)
- Diseño de base de datos y modelos de datos
- Configuración del entorno de desarrollo
- Desarrollo del MVP con funcionalidades core:
  - Registro y login de usuarios
  - Captura de foto de matrícula
  - Reconocimiento básico de matrícula (integración OpenALPR/Tesseract)
  - Formulario de evaluación (puntuación 1-5 estrellas + comentario)
  - Perfil de usuario con puntuación agregada
  - Lista de evaluaciones recibidas
- Testing inicial
- Despliegue en entorno de pruebas

**Entregables:**
- Prototipos de interfaz (Figma/Adobe XD)
- MVP funcional desplegado
- Documentación técnica inicial
- Plan de pruebas piloto

---

### **MES 2: VALIDACIÓN, ITERACIÓN Y FUNCIONALIDADES AVANZADAS**

#### **Semana 5-6: Prueba Piloto y Validación de Concepto**
**Actividades:**
- Reclutamiento de 20-30 usuarios piloto (entorno UHU y conocidos)
- Sesiones de onboarding con usuarios piloto
- Monitoreo activo del uso durante 2 semanas
- Recopilación de feedback mediante:
  - Encuestas de satisfacción
  - Entrevistas cualitativas
  - Análisis de métricas de uso (Google Analytics / Mixpanel)
- Identificación de bugs y problemas de usabilidad
- Análisis de datos iniciales sobre comportamiento

**Entregables:**
- Informe de validación del MVP
- Métricas de uso y engagement
- Lista priorizada de mejoras
- Casos de uso reales documentados

#### **Semana 7-8: Iteración y Funcionalidades Avanzadas**
**Actividades:**
Basándose en el feedback, implementar mejoras y nuevas funcionalidades:
- **Mejoras de UX identificadas en piloto**
- **Sistema de verificación antifraude:**
  - Límite de evaluaciones por día/semana
  - Verificación de geolocalización (evaluación en lugar razonable)
  - Sistema de reportes de evaluaciones inapropiadas
  - Algoritmo de detección de patrones sospechosos
- **Sistema de gamificación:**
  - Niveles de reputación (Novato, Conductor Responsable, Experto, Maestro)
  - Insignias por hitos (100 evaluaciones positivas, 6 meses sin negativas, etc.)
  - Estadísticas personales (tendencias, gráficos)
- **Funcionalidades sociales:**
  - Perfil público más completo
  - Respuesta a evaluaciones (derecho de réplica)
  - Share de perfil en redes sociales
- **Mejoras en reconocimiento de matrículas:**
  - Entrenamiento con más datos
  - Mejor handling de casos edge (matrículas borrosas, ángulos extremos)
- Testing exhaustivo de nuevas funcionalidades

**Entregables:**
- Versión 2.0 de la aplicación
- Sistema de verificación funcional
- Documentación de funcionalidades avanzadas
- Casos de test automatizados

---

### **MES 3: PLAN DE NEGOCIO, ESCALABILIDAD Y DOCUMENTACIÓN FINAL**

#### **Semana 9-10: Plan de Negocio y Escalabilidad**
**Actividades:**
- **Desarrollo del plan de negocio:**
  - Análisis de mercado (TAM, SAM, SOM)
  - Modelo de ingresos (freemium, partnerships, data insights)
  - Proyecciones financieras a 3 años
  - Plan de marketing y adquisición de usuarios
  - Análisis DAFO (Debilidades, Amenazas, Fortalezas, Oportunidades)
- **Estrategia de escalabilidad:**
  - Plan de crecimiento de usuarios (0 → 100K → 1M)
  - Infraestructura necesaria en cada fase
  - Estrategia de internacionalización
- **Identificación de partners estratégicos:**
  - DGT (Dirección General de Tráfico)
  - Compañías de seguros
  - Fabricantes de vehículos
  - Apps de movilidad (Waze, Google Maps)
- **Evaluación de impacto social:**
  - Métricas de impacto esperadas (reducción accidentes, mejora comportamiento)
  - Contribución a ODS (Objetivos de Desarrollo Sostenible)
- **Roadmap de producto a largo plazo:**
  - Wearables (RayBan Meta, Apple Vision Pro)
  - Integración con sistemas del vehículo (Android Auto, CarPlay)
  - IA predictiva de comportamiento
  - Marketplace de servicios relacionados

**Entregables:**
- Plan de negocio completo (Business Plan)
- Estrategia de escalabilidad
- Pitch deck para inversores/partners
- Proyecciones financieras

#### **Semana 11-12: Documentación Final y Preparación de Defensa**
**Actividades:**
- **Redacción de la memoria del TFM:**
  - Introducción y motivación
  - Estado del arte
  - Metodología
  - Análisis y diseño del sistema
  - Implementación
  - Pruebas y validación
  - Plan de negocio
  - Conclusiones y trabajo futuro
  - Anexos (código relevante, manuales, etc.)
- **Documentación técnica completa:**
  - Manual de instalación y despliegue
  - Documentación de API
  - Guía de usuario
  - Documentación de arquitectura
- **Preparación de la defensa:**
  - Presentación (slides)
  - Demo en vivo de la aplicación
  - Video explicativo (2-3 minutos)
- **Revisión final con director**
- **Depósito del TFM según normativa UHU**

**Entregables:**
- Memoria completa del TFM (documento PDF)
- Código fuente completo (repositorio GitHub)
- Documentación técnica
- Presentación para defensa
- Demo funcional de la aplicación
- Material complementario (videos, infografías)

---

### 6.2. Diagrama de Gantt Simplificado

```
MES 1: INVESTIGACIÓN, DISEÑO Y MVP
├── S1-S2: Investigación y Análisis
│   └── Entregable: Estado del arte + Requisitos + Arquitectura
└── S3-S4: Diseño y Desarrollo MVP
    └── Entregable: MVP Funcional + Documentación técnica

MES 2: VALIDACIÓN E ITERACIÓN
├── S5-S6: Prueba Piloto
│   └── Entregable: Informe de validación + Métricas
└── S7-S8: Iteración + Funcionalidades Avanzadas
    └── Entregable: Versión 2.0 + Sistema antifraude + Gamificación

MES 3: NEGOCIO Y DOCUMENTACIÓN
├── S9-S10: Plan de Negocio + Escalabilidad
│   └── Entregable: Business Plan + Pitch Deck
└── S11-S12: Documentación Final + Defensa
    └── Entregable: Memoria TFM + Presentación + Demo
```

---

## 7. ARQUITECTURA DEL SISTEMA

### 7.1. Visión General

DriveScore seguirá una arquitectura de **tres capas** con principios de **microservicios** para facilitar la escalabilidad:

```
┌─────────────────────────────────────────┐
│     CAPA DE PRESENTACIÓN (Frontend)     │
│   - App Móvil (Flutter/React Native)    │
│   - Progressive Web App (Futuro)        │
└─────────────────────────────────────────┘
                    ↕ API REST
┌─────────────────────────────────────────┐
│      CAPA DE LÓGICA (Backend API)       │
│   - Autenticación y Autorización        │
│   - Gestión de Evaluaciones             │
│   - Cálculo de Reputación               │
│   - Sistema de Verificación             │
│   - Notificaciones                      │
└─────────────────────────────────────────┘
                    ↕
┌─────────────────────────────────────────┐
│   CAPA DE DATOS Y SERVICIOS EXTERNOS    │
│   - Base de Datos (PostgreSQL)          │
│   - Almacenamiento de Imágenes (S3)     │
│   - Servicio OCR (OpenALPR/Tesseract)   │
│   - Cache (Redis)                       │
│   - Queue (RabbitMQ/Cloud Tasks)        │
└─────────────────────────────────────────┘
```

### 7.2. Componentes Principales

#### **1. Aplicación Móvil**
- **Tecnología:** Flutter (primera elección) o React Native
- **Funcionalidades:**
  - Captura de fotos optimizada
  - Interfaz de evaluación intuitiva
  - Visualización de perfil y estadísticas
  - Notificaciones push
  - Modo offline (evaluaciones en cola)

#### **2. Backend API**
- **Tecnología:** Node.js + Express o FastAPI (Python)
- **Endpoints principales:**
  - `/auth/*` - Registro, login, recuperación contraseña
  - `/users/*` - Gestión de perfiles
  - `/evaluations/*` - CRUD de evaluaciones
  - `/vehicles/*` - Información de vehículos
  - `/ocr/*` - Servicio de reconocimiento de matrículas
  - `/stats/*` - Estadísticas y rankings

#### **3. Servicio de Reconocimiento (OCR)**
- **Tecnología:** OpenALPR (C++ con bindings Python) o TensorFlow
- **Proceso:**
  1. Recepción de imagen
  2. Preprocesamiento (mejora de contraste, rectificación)
  3. Detección de región de matrícula
  4. Reconocimiento de caracteres
  5. Validación de formato (patrón matrícula española: 0000 XXX)
  6. Devolución de resultado con nivel de confianza

#### **4. Sistema de Verificación y Antifraude**
- **Reglas implementadas:**
  - Límite de evaluaciones por usuario/día (ej: 10 evaluaciones)
  - Verificación de geolocalización (evalúas donde estás)
  - Detección de patrones (múltiples evaluaciones negativas seguidas al mismo vehículo)
  - Cooldown entre evaluaciones a la misma matrícula (ej: 24h)
  - Sistema de reportes y moderación

#### **5. Motor de Cálculo de Reputación**
- **Algoritmo propuesto:**
  ```
  Puntuación = (Σ evaluaciones ponderadas por fecha) / Total evaluaciones
  
  Ponderación:
  - Evaluaciones recientes (< 3 meses): peso 1.0
  - Evaluaciones antiguas (3-12 meses): peso 0.7
  - Evaluaciones muy antiguas (>12 meses): peso 0.4
  
  Badges/Niveles:
  - Novato: < 10 evaluaciones
  - Conductor: 10-50 evaluaciones, promedio > 3.5
  - Responsable: 50-200 evaluaciones, promedio > 4.0
  - Experto: 200-1000 evaluaciones, promedio > 4.3
  - Maestro: >1000 evaluaciones, promedio > 4.5
  ```

### 7.3. Modelo de Datos (Entidades Principales)

#### **
