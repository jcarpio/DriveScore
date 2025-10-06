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

7.3. Modelo de Datos (Entidades Principales)
User (Usuario)
{
  id: UUID,
  email: String (único),
  password_hash: String,
  name: String,
  profile_photo: URL,
  license_plate: String (encriptado),
  created_at: DateTime,
  verified: Boolean,
  reputation_score: Float (0-5),
  total_evaluations_received: Integer,
  total_evaluations_given: Integer,
  level: Enum (NOVATO, CONDUCTOR, RESPONSABLE, EXPERTO, MAESTRO),
  badges: Array[Badge],
  settings: JSON (privacidad, notificaciones)
}
Evaluation (Evaluación)
{
  id: UUID,
  evaluator_id: UUID (FK → User),
  evaluated_license_plate: String (encriptado),
  evaluated_user_id: UUID (FK → User, nullable),
  rating: Integer (1-5),
  comment: Text (opcional),
  categories: JSON {
    respect_pedestrians: Integer (1-5),
    turn_signals: Integer (1-5),
    safe_distance: Integer (1-5),
    speed: Integer (1-5),
    courtesy: Integer (1-5)
  },
  location: GeoPoint,
  photo_url: URL (opcional, con matrícula ofuscada),
  created_at: DateTime,
  verified: Boolean,
  reported: Boolean,
  report_reason: String
}
Vehicle (Vehículo)
{
  license_plate: String (único, encriptado),
  owner_user_id: UUID (FK → User),
  make: String,
  model: String,
  color: String,
  year: Integer,
  verified: Boolean,
  created_at: DateTime
}
Badge (Insignia)
{
  id: UUID,
  name: String,
  description: String,
  icon_url: URL,
  criteria: JSON,
  rarity: Enum (COMÚN, RARO, ÉPICO, LEGENDARIO)
}
Report (Reporte)
{
  id: UUID,
  reporter_id: UUID (FK → User),
  evaluation_id: UUID (FK → Evaluation),
  reason: Enum (SPAM, ACOSO, FALSO, OFENSIVO, OTRO),
  description: Text,
  status: Enum (PENDIENTE, REVISADO, ACCIÓN_TOMADA),
  created_at: DateTime,
  resolved_at: DateTime
}
7.4. Flujo de Funcionamiento Principal
1. Usuario abre app DriveScore
   ↓
2. Usuario captura foto de matrícula de vehículo
   ↓
3. App envía imagen a servicio OCR
   ↓
4. Sistema reconoce matrícula (ej: "1234 ABC")
   ↓
5. Sistema verifica si matrícula existe en BD
   ↓
6. Usuario selecciona puntuación (1-5 estrellas)
   ↓
7. Usuario puede añadir comentario y categorías
   ↓
8. Sistema valida:
   - ¿Usuario ha excedido límite diario?
   - ¿Evaluación duplicada reciente?
   - ¿Ubicación coherente?
   ↓
9. Sistema guarda evaluación
   ↓
10. Sistema actualiza puntuación del conductor evaluado
    ↓
11. Sistema envía notificación push al conductor evaluado
    ↓
12. Conductor evaluado puede:
    - Ver evaluación
    - Responder (derecho de réplica)
    - Reportar si considera injusta
7.5. Seguridad y Privacidad
Medidas Implementadas:

Encriptación de Datos Sensibles:

Matrículas almacenadas con encriptación AES-256
Comunicaciones mediante HTTPS/TLS
Imágenes con matrículas ofuscadas para privacidad


Autenticación y Autorización:

OAuth 2.0 para autenticación
JWT con expiración corta (15 min) + refresh tokens
Rate limiting en API para prevenir abuso
2FA opcional para usuarios


Anonimización Parcial:

Solo se muestran iniciales del evaluador (J.C.C.)
Opción de evaluaciones anónimas
Geolocalización aproximada (ciudad, no coordenadas exactas)


Derecho de Réplica y Moderación:

Todo usuario puede responder a evaluaciones
Sistema de reportes con revisión humana
Sanciones progresivas por mal uso (advertencia → suspensión temporal → ban)


Cumplimiento GDPR:

Consentimiento explícito en registro
Derecho al olvido (eliminar cuenta y datos)
Portabilidad de datos
Transparencia en uso de datos
Política de privacidad clara y accesible




8. ASPECTOS LEGALES Y ÉTICOS
8.1. Marco Legal Aplicable
GDPR (Reglamento General de Protección de Datos)
Datos Personales Tratados:

Matrícula del vehículo (dato identificativo)
Nombre y email del usuario
Geolocalización aproximada
Imágenes de vehículos (potencialmente pueden identificar personas)

Base Legal para el Tratamiento:

Consentimiento explícito del usuario al registrarse
Interés legítimo para la prestación del servicio

Medidas de Cumplimiento:

Nombramiento de DPO (Data Protection Officer) - el experto en protección de datos mencionado
Privacy Impact Assessment (DPIA) antes del lanzamiento
Registro de actividades de tratamiento
Contratos con procesadores de datos (cloud providers)
Política de privacidad detallada
Cookie consent banner

Derechos de los Usuarios:

Acceso a sus datos
Rectificación de datos incorrectos
Supresión ("derecho al olvido")
Portabilidad
Oposición al tratamiento
Limitación del tratamiento

Ley Orgánica de Protección de Datos (LOPDGDD)
Aplicación específica en España del GDPR. Consideraciones adicionales:

Normativa sobre videovigilancia (aplicable a capturas de imágenes en vía pública)
Protección especialmente reforzada de menores
Obligación de informar claramente sobre la finalidad de las fotografías

Derecho a la Imagen (Ley Orgánica 1/1982)
Desafío: Las fotografías de matrículas pueden capturar inadvertidamente personas o partes de personas.
Solución Propuesta:

Implementar detección automática de rostros y ofuscarlos antes de almacenamiento
Política estricta: las fotos son solo para reconocimiento de matrícula, no se publican
Informar claramente a usuarios que no deben fotografiar personas intencionadamente

Excepción de interés público: Argumentable que mejorar la seguridad vial es de interés público, pero debe manejarse con cautela.
Normativa de Tráfico

La app no sustituye ni interfiere con sanciones oficiales de tráfico
Las evaluaciones son opiniones subjetivas, no tienen valor legal
Importante: no incentivar prácticas peligrosas (ej: fotografiar mientras se conduce)
Incluir advertencias sobre uso seguro de la app

8.2. Consideraciones Éticas
Prevención de Acoso y Uso Malintencionado
Riesgos Identificados:

Evaluaciones masivas negativas coordinadas (bullying)
Venganza personal mediante evaluaciones falsas
Discriminación o sesgos (por tipo de vehículo, zona, etc.)
Acoso a individuos específicos

Medidas de Mitigación:

Algoritmo de Detección de Patrones Sospechosos:

Alerta si un usuario recibe múltiples evaluaciones negativas en corto período
Revisión manual de casos sospechosos


Límites y Balances:

Un usuario no puede evaluar la misma matrícula más de una vez al día
Límite de evaluaciones totales por día (ej: 10)
Penalizaciones por evaluaciones reportadas y confirmadas como falsas


Moderación Comunitaria + Humana:

Sistema de reportes fácil de usar
Equipo de moderación que revisa reportes
Comunidad puede votar sobre pertinencia de evaluaciones (sistema tipo Reddit)


Educación de Usuarios:

Código de conducta claro
Ejemplos de evaluaciones constructivas vs. destructivas
Mensajes recordatorios sobre uso responsable



Filosofía: Confianza en las Personas
Como menciona el director del proyecto, siguiendo el ejemplo de BlaBlaCar:

"La mayoría de las personas harán un buen uso de la aplicación porque es algo muy bueno para el planeta."

Principio Fundamental:

Diseñar para el 95% de usuarios de buena fe
Tener medidas para el 5% de mal uso, pero sin que esto comprometa la experiencia del 95%
Transparencia y datos abiertos sobre cómo se usa la plataforma
Confianza como valor central, pero verificación como respaldo

Balance: Identificación vs. Anonimato
Postura del Proyecto: Identificación con privacidad controlada

Los usuarios tienen perfiles públicos con su historial
Inspiración: BlaBlaCar permite construir reputación a largo plazo
Los evaluadores pueden ser anónimos o identificados (elección del usuario)
Sistema de "verificación" (similar a check azul) para usuarios que validen su identidad

Beneficios de la Identificación:

Mayor responsabilidad al evaluar
Construcción de historial de conducción positivo
Incentivo para mantener buen comportamiento a largo plazo
Valor curricular (demostrar años de conducción segura)


9. MODELO DE NEGOCIO Y SOSTENIBILIDAD
9.1. Filosofía de Sostenibilidad Económica
Enfoque Inicial: Gratuito con Infraestructura de Bajo Costo
Siguiendo el modelo de WhatsApp y Google en sus inicios:

Servicio gratuito para usuarios durante fase de crecimiento
Foco en adquisición masiva de usuarios y generación de valor
Infraestructura basada en capas gratuitas de servicios cloud
Optimización de costos mediante software libre

Horizonte de Monetización: Año 2-3
Una vez alcanzada masa crítica de usuarios (>100,000), explorar modelos de ingresos.
9.2. Estructura de Costos (Fase Inicial)
Costos de Infraestructura (Mensual Estimado)
ServicioProveedorCosto InicialCosto con 10K usuariosCosto con 100K usuariosHosting BackendVercel / Cloud Run€0 (Free tier)€20/mes€150/mesBase de DatosSupabase / Neon€0 (Free tier)€25/mes€200/mesAlmacenamiento ImágenesCloudflare R2€0 (10 GB)€5/mes€50/mesCDNCloudflare€0€0€0Servicio OCRGoogle Cloud Vision€0 (1000/mes)€30/mes€300/mesNotificaciones PushFCM (Firebase)€0€0€10/mesMonitoreoGrafana Cloud€0€0€50/mesTOTAL€0€80/mes€760/mes
Conclusión: Con estrategia de software libre y capas gratuitas, el proyecto puede operar con costos casi nulos durante el primer año, permitiendo enfocarse en crecer y validar el concepto.
9.3. Fuentes de Ingresos Potenciales (Futuro)
1. Modelo Freemium
Versión Gratuita (para siempre):

Funcionalidades core completas
Evaluaciones ilimitadas
Perfil básico de reputación

Versión Premium (DriveScore Pro - €2.99/mes o €29/año):

Estadísticas avanzadas (tendencias, gráficos históricos)
Badges exclusivos
Certificado descargable de buena conducción (PDF oficial)
Prioridad en soporte
Sin publicidad (si eventualmente se introduce)
Análisis comparativo con conductores similares
Alertas personalizadas

Proyección: Con 100K usuarios, si 5% se convierte a Premium = 5,000 × €30/año = €150,000/año
2. Partnerships con Aseguradoras
Valor para Aseguradoras:

Datos agregados sobre comportamiento de conducción
Identificación de conductores de bajo riesgo
Validación objetiva de buenos conductores

Modelos de Colaboración:

Descuentos en seguros: Aseguradoras ofrecen 10-20% descuento a usuarios con alta reputación DriveScore
Licenciamiento de tecnología: Venta de API de scoring a aseguradoras
Comisión por referral: DriveScore recomienda seguros, cobra comisión por cada contrato

Potencial: Partnerships con 3-5 aseguradoras españolas (MAPFRE, Mutua Madrileña, AXA, etc.) podrían generar €50,000-200,000/año en fase de crecimiento.
3. Colaboración con DGT y Organismos Públicos
Valor para la DGT:

Datos de seguridad vial en tiempo real
Identificación de puntos conflictivos
Campañas de concienciación basadas en datos

Modelos:

Subvenciones: Financiación pública por innovación en seguridad vial
Contratos de consultoría: Análisis de datos para políticas públicas
Integración oficial: DriveScore como complemento opcional al sistema de puntos

Potencial: Subvenciones europeas (H2020, Digital Europe) o españolas (CDTI) de €100,000-500,000 para I+D+i en seguridad vial.
4. Marketplace de Servicios Relacionados
Concepto: Plataforma para servicios relacionados con vehículos

Talleres verificados con descuentos para usuarios de alta reputación
Estaciones de servicio con ofertas
Cursos de conducción segura
Alquiler de vehículos P2P (tipo Turo) con reputación DriveScore

Modelo: Comisión del 10-15% por cada transacción facilitada.
5. Datos Agregados y Anonimizados (B2B)
Valor: Insights sobre patrones de movilidad, zonas de riesgo, comportamientos de conducción.
Clientes Potenciales:

Ayuntamientos (planificación urbana)
Empresas de movilidad (Uber, Cabify, Car2Go)
Investigadores académicos
Fabricantes de vehículos (feedback sobre UX de modelos)

Modelo: Licencias anuales de acceso a dashboard de analytics: €10,000-50,000/cliente/año
IMPORTANTE: Siempre con datos agregados y anonimizados, cumpliendo GDPR al 100%.
6. Publicidad No Intrusiva (Último Recurso)
Si es necesario, implementar publicidad de manera respetuosa:

Anuncios de marcas relacionadas con automoción
Solo en versión gratuita (Premium sin ads)
Nunca compromete experiencia de usuario

9.4. Proyección Financiera a 3 Años
Año 1: Fase de Lanzamiento y Validación

Usuarios objetivo: 0 → 10,000
Ingresos: €0 (gratuito)
Costos: €1,000 (infraestructura, dominio, legal)
Inversión necesaria: €5,000 (desarrollo, marketing inicial)
Resultado: -€6,000 (inversión en crecimiento)

Año 2: Fase de Crecimiento

Usuarios objetivo: 10,000 → 100,000
Ingresos:

Freemium (1% conversión): €30,000
Partnerships iniciales: €20,000
Total: €50,000


Costos: €10,000 (infraestructura, equipo part-time)
Inversión marketing: €30,000
Resultado: +€10,000 (breakeven)

Año 3: Fase de Escalado

Usuarios objetivo: 100,000 → 500,000
Ingresos:

Freemium (3% conversión): €450,000
Partnerships aseguradoras: €100,000
Datos B2B: €50,000
Total: €600,000


Costos: €150,000 (infraestructura, equipo 3-5 personas)
Inversión crecimiento: €200,000
Resultado: +€250,000 (rentable)

9.5. Estrategia de Financiación
Fase 1: Bootstrapping (Meses 0-12)

Desarrollo con recursos propios (TFM de Gamaliel)
Infraestructura gratuita
Marketing orgánico (viralidad, redes sociales)

Fase 2: Pre-Seed / Friends & Family (Mes 12-18)

Ronda de €20,000-50,000 para marketing y primeras contrataciones
Inversores: familiares, amigos, business angels locales

Fase 3: Seed (Mes 18-24)

Si métricas son positivas (crecimiento, engagement), buscar:

Aceleradoras españolas (Wayra, Lanzadera, Plug and Play)
Business angels especializados en mobility/impact
Ronda de €200,000-500,000



Fase 4: Serie A (Año 3+)

Con 500K+ usuarios y tracción demostrada
VCs especializados en mobility, insurtech o social impact
Ronda de €2-5M para expansión internacional

9.6. Plan de Marketing y Adquisición de Usuarios
Fase de Lanzamiento (Mes 1-3): Universidad y Círculo Cercano

Estrategia: Early adopters en entorno controlado
Canales:

Presentación en Universidad de Huelva (estudiantes, profesores)
Redes sociales personales (LinkedIn, Twitter, Instagram)
Grupos de WhatsApp/Telegram de conductores


Objetivo: 500 usuarios activos
KPI: 30% de usuarios activos semanalmente

Fase de Crecimiento Local (Mes 4-9): Huelva y Andalucía

Estrategia: Viralidad y prescriptores locales
Canales:

Colaboración con autoescuelas (certificar alumnos que aprueban)
Eventos locales (DGT, ferias de movilidad)
Prensa local (Huelva Información, Diario de Huelva)
Influencers locales de movilidad/sostenibilidad
Campaña en redes sociales geolocalizadas


Objetivo: 5,000 usuarios activos en Andalucía
KPI: 25% de usuarios recomiendan a otros (NPS > 50)

Fase de Expansión Nacional (Mes 10-24): España

Estrategia: Marketing digital y partnerships
Canales:

Google Ads y Meta Ads (targeting: conductores 25-55 años)
Colaboración con apps de movilidad (Waze, Google Maps)
Partnerships con aseguradoras (co-marketing)
PR nacional (El País, El Mundo, Cadena SER)
Podcast de movilidad y tecnología


Objetivo: 100,000 usuarios activos en España
KPI: CAC (Customer Acquisition Cost) < €5

Fase de Internacionalización (Año 3+): Europa y LATAM

Mercados prioritarios:

Portugal (proximidad cultural y lingüística)
Italia y Francia (alta densidad de conductores urbanos)
México y Colombia (mercados emergentes, problemas de tráfico)


Estrategia: Localización (idioma, formatos de matrículas) + partnerships locales

Tácticas de Viralidad

Referral Program:

"Invita a 3 amigos, desbloquea badge exclusivo"
"Por cada amigo que evalúe 5 coches, ganas puntos"


Gamificación Social:

Ranking mensual de "Conductores Más Respetados" por ciudad
Competiciones entre ciudades (¿dónde se conduce mejor?)
Challenges mensuales (#DíaSinKlaxons, #SemanaCourtesía)


Shareable Content:

"Comparte tu certificado de Conductor Experto en LinkedIn"
Infografías personalizadas (tu año en DriveScore)
Badges bonitos para redes sociales


Eventos y Comunidad:

Meetups de "Conductores 5 Estrellas"
Colaboración con eventos de movilidad sostenible
Formación gratuita en conducción segura para usuarios activos




10. ANÁLISIS DE RIESGOS
10.1. Riesgos Técnicos
RiesgoProbabilidadImpactoMitigaciónPrecisión insuficiente en OCRMediaAltoUsar múltiples engines (OpenALPR + Tesseract), entrenamiento con dataset español, permitir corrección manualEscalabilidad de infraestructuraBajaAltoArquitectura cloud-native desde inicio, uso de servicios serverless, pruebas de cargaProblemas de rendimiento en móvilMediaMedioOptimización de imágenes, inferencia ligera, caché local, modo offlineAtaques de seguridad (DDoS, injección)MediaAltoWAF (Cloudflare), sanitización de inputs, rate limiting, auditorías de seguridadPérdida de datosBajaCríticoBackups automáticos diarios, replicación multi-región, plan de disaster recovery
10.2. Riesgos Legales y Regulatorios
RiesgoProbabilidadImpactoMitigaciónIncumplimiento GDPRMediaCríticoConsultoría legal especializada, DPIA, DPO dedicado, auditorías regularesDemandas por difamaciónMediaAltoTérminos de uso claros, sistema de moderación robusto, derecho de réplica, seguro de responsabilidad civilProhibición de captura de matrículasBajaCríticoAlineación con precedentes legales (Waze, Google Street View), asesoría legal continuaRequisitos regulatorios cambiantesMediaMedioMonitoreo legislativo, flexibilidad en diseño para adaptaciones
10.3. Riesgos de Mercado y Adopción
RiesgoProbabilidadImpactoMitigaciónBaja adopción de usuariosAltaCríticoMVP validado con usuarios reales, marketing agresivo inicial, viralidad integrada, propuesta de valor claraCompetencia de grandes techMediaAltoFirst-mover advantage, foco en comunidad y valores, partnerships estratégicosFalta de masa críticaAltaCríticoLanzamiento por ciudades (concentración geográfica), incentivos para early adoptersPercepción negativa (app de "chivatos")MediaAltoComunicación enfocada en seguridad y beneficio colectivo, historias de éxito, embajadores de marcaMonetización insuficienteMediaAltoMúltiples fuentes de ingresos planificadas, costos bajos, pivote de modelo si necesario
10.4. Riesgos Operacionales
RiesgoProbabilidadImpactoMitigaciónFalta de recursos (tiempo/dinero)AltaAltoPlan de 3 meses ajustado, uso de software libre, priorización de funcionalidades coreDependencia de servicios de tercerosMediaMedioMúltiples proveedores cloud, capacidad de migración, evitar vendor lock-inBurnout del equipoMediaMedioAlcance realista del TFM, metodología ágil con sprints manejables, apoyo del directorModeración de contenido no escalableAltaMedioAutomatización con IA (filtros de lenguaje ofensivo), moderación comunitaria, sistema de reportes eficiente
10.5. Plan de Contingencia
Escenario 1: OCR no alcanza precisión aceptable (>85%)

Plan B: Introducir entrada manual de matrícula con autocompletado
Plan C: Gamificar la corrección manual (usuarios ganan puntos por corregir OCR)

Escenario 2: Rechazo legal/regulatorio

Plan B: Pivotar a evaluación solo de conductores conocidos (estilo BlaBlaCar cerrado)
Plan C: Sistema de evaluación de rutas/trayectos sin identificación de conductor

Escenario 3: Falta de adopción de usuarios

Plan B: Foco en nichos específicos (flotas de empresa, comunidades de ciclistas)
Plan C: B2B exclusivo (venta de tecnología a aseguradoras)


11. ROADMAP DE PRODUCTO A LARGO PLAZO
11.1. Versión 1.0 (Mes 0-3): MVP - Core Features
Objetivo: Validar concepto con usuarios reales

Registro y login
Captura y reconocimiento de matrículas
Evaluación básica (1-5 estrellas + comentario)
Perfil de usuario con reputación
Notificaciones push
Sistema de reportes básico

11.2. Versión 2.0 (Mes 4-6): Gamificación y Verificación
Objetivo: Aumentar engagement y confianza

Sistema completo de gamificación (niveles, badges)
Categorías de evaluación (respeto, señales, distancia, etc.)
Verificación antifraude avanzada
Estadísticas personales detalladas
Respuesta a evaluaciones (derecho de réplica)
Compartir perfil en redes sociales

11.3. Versión 3.0 (Mes 7-12): Social y Comunidad
Objetivo: Crear comunidad engaged

Feed social de actividad
Seguir a otros conductores
Rankings por ciudades/países
Challenges mensuales comunitarios
Sistema de recompensas y premios
Integración con redes sociales
Blog y recursos educativos

11.4. Versión 4.0 (Año 2): Partnerships y Monetización
Objetivo: Escalar y generar ingresos

Freemium (DriveScore Pro)
Integración con aseguradoras (descuentos)
Certificados oficiales descargables
Marketplace de servicios
API para terceros (aseguradoras, flotas)
Expansión internacional (multi-idioma, multi-formato matrículas)

11.5. Versión 5.0 (Año 3+): IA y Wearables
Objetivo: Innovación y diferenciación

IA Predictiva:

Análisis de patrones de conducción
Predicción de comportamientos de riesgo
Recomendaciones personalizadas


Wearables:

Integración con RayBan Meta / Apple Vision Pro
Reconocimiento de matrículas hands-free
HUD (Head-Up Display) con info de otros conductores en tiempo real
Evaluación por comando de voz


Integración Vehículos:

Android Auto / Apple CarPlay
Integración con sistemas del vehículo (velocidad, frenadas)
Scoring automático basado en telemática


Expansión de Funcionalidades:

Evaluación de parking (cómo estacionan)
Evaluación de ciclistas (respeto en carril bici)
Evaluación de peatones (cruces indebidos)
Sistema de "karma vial" global




12. IMPACTO SOCIAL Y CONTRIBUCIÓN A ODS
12.1. Alineación con Objetivos de Desarrollo Sostenible (ONU)
DriveScore contribuye directamente a varios ODS:
ODS 3: Salud y Bienestar

Meta 3.6: Reducir a la mitad muertes por accidentes
ReintentarJContinuarEditarde tráfico

Contribución: Al incentivar conducción responsable, se espera una reducción de comportamientos de riesgo que causan accidentes
Indicador: Correlación entre usuarios activos en una zona y reducción de siniestralidad

ODS 11: Ciudades y Comunidades Sostenibles

Meta 11.2: Proporcionar acceso a sistemas de transporte seguros y sostenibles
Contribución: Cultura vial más segura y respetuosa, reducción de congestión por conducción agresiva
Indicador: Mejora en índices de seguridad vial urbana en ciudades con alta adopción

ODS 13: Acción por el Clima

Meta 13.3: Mejorar educación y sensibilización sobre cambio climático
Contribución: Conducción eficiente reduce emisiones; menor número de accidentes reduce recursos de emergencia
Indicador: Cálculo de reducción de CO₂ por conducción más eficiente (menor aceleración/frenado brusco)

ODS 16: Paz, Justicia e Instituciones Sólidas

Meta 16.6: Crear instituciones eficaces, responsables y transparentes
Contribución: Sistema de rendición de cuentas ciudadano complementario a instituciones oficiales
Indicador: Transparencia en datos de conducción, mejora en confianza ciudadana en movilidad compartida

ODS 17: Alianzas para Lograr los Objetivos

Meta 17.17: Fomentar alianzas eficaces públicas, público-privadas
Contribución: Colaboración con DGT, aseguradoras, ayuntamientos para políticas basadas en datos
Indicador: Número de partnerships estratégicos establecidos, datos compartidos con organismos públicos

12.2. Métricas de Impacto Social Esperadas
Corto Plazo (Año 1):

10,000 usuarios activos evaluando comportamientos viales
50,000 evaluaciones registradas
Encuestas de percepción: 70% de usuarios reportan haber modificado al menos 1 comportamiento de conducción
Histórico público: 100 conductores con perfil de 30+ evaluaciones positivas

Medio Plazo (Año 2-3):

100,000 usuarios activos en España
1,000,000 evaluaciones acumuladas
Reducción estimada del 5-10% en comportamientos de riesgo en zonas con alta penetración
10 partnerships con instituciones públicas/privadas
Estudio académico validando impacto en conducción (colaboración con universidades)

Largo Plazo (Año 5+):

1,000,000+ usuarios a nivel internacional
Reducción demostrable de siniestralidad en zonas con adopción masiva (>20% conductores)
Cambio cultural: DriveScore reconocido como estándar de "ciudadanía vial digital"
Legislación: Posible reconocimiento oficial de reputación DriveScore en procesos administrativos

12.3. Casos de Uso de Alto Impacto Social
Caso 1: Renovación de Permisos de Conducir
Problema Original (José Carpio): Dificultad para demostrar historial de conducción segura ante condiciones médicas.
Solución con DriveScore:

Perfil público con 30 años de evaluaciones positivas
Certificado descargable con métricas objetivas
Evidencia complementaria para comisiones médicas
Impacto: Procesos administrativos más justos basados en comportamiento real, no solo en condición médica

Caso 2: Conductores Profesionales (VTC, Taxi, Flotas)
Problema: Difícil diferenciarse en mercados competitivos.
Solución con DriveScore:

Badge de "Conductor Profesional Verificado"
Reputación visible para pasajeros
Incentivo para mantener estándares altos
Impacto: Mayor seguridad para usuarios de servicios de transporte, profesionalización del sector

Caso 3: Conductores Noveles
Problema: Alta siniestralidad en primeros años de conducción.
Solución con DriveScore:

Sistema de mentoring (conductores expertos asesoran a noveles)
Gamificación de aprendizaje de buenos hábitos
Feedback constructivo de la comunidad
Impacto: Reducción de accidentes en conductores jóvenes, aprendizaje social de mejores prácticas

Caso 4: Víctimas de Accidentes y Familiares
Problema: Sensación de impunidad ante conductores imprudentes no sancionados oficialmente.
Solución con DriveScore:

Sistema de "justicia social" complementario (no sustitutivo) al legal
Visibilización de comportamientos peligrosos
Presión social positiva para cambio
Impacto: Empoderamiento ciudadano, prevención de futuros accidentes

Caso 5: Movilidad Urbana Sostenible
Problema: Conflicto entre diferentes usuarios de vía (coches, bicis, peatones).
Solución con DriveScore:

Evaluación cruzada (ciclistas evalúan conductores y viceversa)
Promoción de empatía entre usuarios de la vía
Datos para planificación urbana (zonas conflictivas)
Impacto: Convivencia más armónica, ciudades más caminables y ciclables


13. ANÁLISIS DAFO
13.1. Debilidades
D1. Proyecto Nuevo sin Track Record

Sin usuarios actuales ni datos históricos
Marca desconocida en el mercado
Dificultad para generar confianza inicial

D2. Dependencia de Masa Crítica

El valor de la app aumenta con número de usuarios (efecto red)
Problema del "huevo y la gallina": pocos usuarios → pocas evaluaciones → poca utilidad

D3. Complejidad Técnica del OCR

Reconocimiento de matrículas en condiciones variables es desafiante
Requiere entrenamiento de modelos y ajustes continuos
Errores de reconocimiento pueden frustrar usuarios

D4. Recursos Limitados Inicialmente

Equipo pequeño (TFM individual)
Presupuesto limitado para marketing
3 meses de desarrollo es período corto para producto complejo

D5. Moderación de Contenido Demandante

Riesgo de evaluaciones maliciosas o spam
Requiere recursos para moderación que inicialmente no se tienen
Posible percepción negativa si hay abusos no controlados

13.2. Amenazas
A1. Barreras Legales y Regulatorias

GDPR y protección de datos puede limitar funcionalidades
Posibles cambios legislativos adversos
Litigios por difamación o mal uso

A2. Competencia de Grandes Players

Google/Waze podrían integrar funcionalidad similar
Aseguradoras desarrollando sus propias apps de scoring
Apps de movilidad existentes con gran base de usuarios

A3. Rechazo Cultural o Social

Percepción de "sociedad vigilante" o "cultura del chivato"
Resistencia por parte de conductores que no quieren ser evaluados
Posible backlash en redes sociales

A4. Ciberseguridad y Privacidad

Ataques de hackers buscando datos personales
Filtraciones de información sensible dañarían reputación gravemente
Uso malintencionado por actores externos (doxxing, acoso)

A5. Falta de Monetización Sostenible

Modelo freemium puede no generar ingresos suficientes
Partnerships pueden no materializarse
Costos de escala mayores a los proyectados

A6. Fatiga de App / Baja Retención

Usuarios descargan pero no usan activamente
Novedad inicial que pierde interés con el tiempo
Competencia por atención en dispositivos móviles

13.3. Fortalezas
F1. Propuesta de Valor Única y Clara

Primera app de evaluación social abierta de conductores
Resuelve problema real (demostrar historial de conducción)
Potencial de mejora significativa en seguridad vial

F2. Misión y Valores Sólidos

Propósito social claro (salvar vidas, mejorar planeta)
Valores éticos que resuenan con usuarios conscientes
Historia de origen auténtica y conmovedora (caso José Carpio)

F3. Modelo Probado en Otros Sectores

Evaluación social exitosa en eBay, BlaBlaCar, Airbnb
Gamificación efectiva demostrada en Waze
No es concepto nuevo, sino aplicación innovadora

F4. Tecnología Open Source y Bajo Costo

Infraestructura escalable con costos mínimos iniciales
Flexibilidad para iterar y pivotar
Comunidad open source como soporte

F5. Enfoque Ágil y Centrado en Usuario

Metodología de desarrollo continuo
Validación rápida con usuarios reales (pilotos)
Capacidad de adaptación basada en feedback

F6. Potencial de Partnerships Estratégicos

Interés natural de aseguradoras, DGT, fabricantes
Datos valiosos para múltiples stakeholders
Posibilidad de integración con ecosistemas existentes

F7. Equipo Comprometido y Multidisciplinar

Director con experiencia académica y empresarial
Alumno dedicado (TFM)
Acceso a experto en protección de datos
Apoyo de comunidad universitaria

13.4. Oportunidades
O1. Creciente Preocupación por Seguridad Vial

1.35M muertes anuales por tráfico globalmente
Gobiernos buscando soluciones innovadoras
Ciudadanos más conscientes de riesgos viales

O2. Tendencia a Economía Colaborativa y de Reputación

Normalización de sistemas de evaluación entre pares
Confianza en valoraciones de comunidad
Éxito de modelos similares en otros sectores

O3. Digitalización de la Movilidad

Apps de movilidad omnipresentes
Integración de smartphones en experiencia de conducción
Vehículos conectados y ecosistemas digitales

O4. Incentivos de Aseguradoras

Búsqueda de nuevas formas de calcular riesgo
Competencia por atraer conductores seguros
Apertura a innovación en insurtech

O5. Datos como Activo Valioso

Instituciones públicas necesitan datos de movilidad
Urbanismo basado en evidencia
Investigación académica sobre comportamiento vial

O6. Expansión Internacional

Problema global aplicable a todos los países
Potencial de escalado rápido una vez validado
Mercados emergentes con crecimiento de vehículos

O7. Tecnologías Emergentes

Wearables (RayBan Meta, Apple Vision Pro) permiten nuevas UX
IA generativa para análisis predictivo
5G y edge computing para procesamiento en tiempo real

O8. Financiación Disponible

Fondos europeos para innovación en movilidad y seguridad
Interés de VCs en mobility tech y social impact
Subvenciones públicas para I+D+i


14. MÉTRICAS DE ÉXITO Y KPIs
14.1. KPIs del Proyecto TFM (3 meses)
Métricas de Desarrollo:

✅ MVP funcional desplegado al final del Mes 1
✅ 100% de funcionalidades core implementadas
✅ 0 bugs críticos en producción
✅ 90%+ de test coverage en funcionalidades críticas
✅ Documentación técnica completa (API, arquitectura, deployment)

Métricas de Validación:

✅ 20-30 usuarios piloto reclutados
✅ 80%+ de usuarios completan onboarding
✅ 100+ evaluaciones reales generadas durante piloto
✅ NPS (Net Promoter Score) > 40
✅ 3 entrevistas cualitativas documentadas

Métricas de Investigación:

✅ Estado del arte completo con 20+ referencias
✅ Análisis legal con consulta a experto en protección de datos
✅ Plan de negocio completo con proyecciones financieras
✅ Análisis competitivo de 5+ apps similares

Métricas Académicas:

✅ Memoria TFM completa según normativa UHU
✅ Presentación de 15-20 minutos preparada
✅ Demo funcional en vivo
✅ Calificación objetivo: Sobresaliente (9+)

14.2. KPIs de Producto (Post-TFM)
Adquisición de Usuarios:

Mes 1-3: 500 usuarios registrados
Mes 4-6: 2,000 usuarios (+300% crecimiento)
Mes 7-12: 10,000 usuarios (+400% crecimiento)
Año 2: 100,000 usuarios
CAC (Customer Acquisition Cost): < €5 por usuario
Viralidad (K-factor): > 1.2 (cada usuario trae >1 usuario nuevo)

Engagement y Retención:

DAU/MAU (Daily Active Users / Monthly Active Users): > 20%
Retención D1 (Day 1): > 40%
Retención D7 (Week 1): > 25%
Retención D30 (Month 1): > 15%
Sesiones por usuario/semana: > 3
Evaluaciones por usuario activo/mes: > 5

Calidad de Evaluaciones:

Ratio evaluaciones positivas/negativas: 70/30 (refleja realidad)
Evaluaciones reportadas: < 2%
Evaluaciones confirmadas como spam/abuso: < 0.5%
Tiempo medio de respuesta a reportes: < 24 horas

Precisión Técnica:

Tasa de éxito OCR: > 85% (reconocimiento correcto de matrícula)
Tiempo de procesamiento OCR: < 3 segundos
Disponibilidad del sistema (uptime): > 99.5%
Tiempo de carga de app: < 2 segundos

Monetización (Año 2+):

Tasa de conversión Freemium: 2-5%
ARPU (Average Revenue Per User): €0.50-1.50/mes
LTV (Lifetime Value): > €20 por usuario
LTV/CAC ratio: > 3:1

14.3. KPIs de Impacto Social
Cambio de Comportamiento:

Usuarios que reportan haber mejorado conducción: > 60%
Reducción de comportamientos de riesgo autoreportados: 30%
Incremento de cortesía vial (ceder paso, uso de intermitentes): 40%

Seguridad Vial:

Correlación con reducción de accidentes en zonas de alta adopción: A medir con datos oficiales DGT
Colaboraciones con organismos de seguridad vial: 3+ en año 2

Concienciación:

Alcance en redes sociales: 100K+ impresiones/mes
Menciones en medios: 10+ artículos en prensa nacional en año 1
Valoración de app en stores: > 4.2/5.0


15. REQUISITOS ESPECÍFICOS DE LA UNIVERSIDAD DE HUELVA
15.1. Normativa de TFM - Universidad de Huelva
Según la normativa vigente de la Universidad de Huelva para Trabajos Fin de Máster del Máster en Ingeniería Informática:
Estructura de la Memoria:
La memoria del TFM debe contener los siguientes apartados:

Portada:

Título del proyecto
Nombre del alumno
Nombre del director/es
Titulación y curso académico
Escudo de la Universidad de Huelva


Resumen y Abstract:

Resumen en español (máx. 300 palabras)
Abstract en inglés (máx. 300 palabras)
Palabras clave (5-7 términos)


Índices:

Índice general
Índice de figuras
Índice de tablas
Lista de acrónimos y abreviaturas


Capítulo 1: Introducción

Motivación y contexto
Objetivos (general y específicos)
Estructura de la memoria


Capítulo 2: Estado del Arte

Revisión bibliográfica
Tecnologías existentes
Análisis de soluciones similares
Justificación del proyecto


Capítulo 3: Metodología

Metodología de desarrollo empleada
Herramientas y tecnologías
Planificación temporal


Capítulo 4: Análisis

Requisitos funcionales
Requisitos no funcionales
Casos de uso
Especificaciones del sistema


Capítulo 5: Diseño

Arquitectura del sistema
Diseño de base de datos
Diseño de interfaces
Diagramas UML (casos de uso, secuencia, clases, etc.)


Capítulo 6: Implementación

Descripción de la implementación
Fragmentos de código relevantes
Decisiones técnicas
Dificultades encontradas y soluciones


Capítulo 7: Pruebas y Validación

Plan de pruebas
Casos de prueba
Resultados de validación
Feedback de usuarios (si aplica)


Capítulo 8: Conclusiones y Trabajo Futuro

Conclusiones generales
Objetivos alcanzados
Limitaciones del proyecto
Líneas futuras de investigación/desarrollo


Referencias Bibliográficas

Formato IEEE o APA
Mínimo 20 referencias


Anexos

Manuales de usuario/instalación
Código fuente (extractos relevantes)
Diagramas adicionales
Documentación complementaria



Requisitos de Formato:

Extensión: 60-100 páginas (sin contar anexos)
Formato: A4, márgenes 2.5 cm
Tipografía: Times New Roman o Arial, tamaño 12pt
Interlineado: 1.5
Encuadernación: Tapa dura o espiral
Entrega: 3 copias en papel + 1 copia digital (PDF)

Defensa del TFM:

Duración: 15-20 minutos de presentación + 10-15 minutos de preguntas
Material: Presentación en PowerPoint/similar, demo en vivo (opcional pero recomendado)
Tribunal: 3 profesores del Departamento de Tecnologías de la Información
Evaluación: Calificación 0-10, siendo necesario un mínimo de 5 para aprobar

Criterios de Evaluación:

Memoria escrita (40%):

Claridad y estructura
Rigor técnico
Calidad de redacción
Cumplimiento de normativa


Trabajo realizado (40%):

Complejidad técnica
Originalidad
Funcionalidad del sistema
Calidad del código


Defensa (20%):

Claridad en la exposición
Dominio del tema
Capacidad de respuesta
Profesionalidad



15.2. Cronograma de Entregables según Normativa UHU
HitoFecha EstimadaEntregableAprobación del temaSemana 1Propuesta de TFM firmada por directorRevisión intermediaFinal Mes 1MVP funcional + informe de avancePre-entrega (opcional)Semana 10Borrador de memoria para revisión del directorEntrega de memoriaSemana 11Memoria completa + código + documentaciónDepósito oficialSemana 12, día 1-33 copias físicas + PDF en plataforma UHUDefensa públicaSemana 12, día 5-7Presentación ante tribunal
15.3. Recursos y Apoyo Institucional
Recursos Disponibles en la UHU:

Biblioteca Universitaria: Acceso a bases de datos académicas (IEEE Xplore, ACM Digital Library, Springer)
Laboratorios de Informática: Para desarrollo y pruebas
Servidor institucional: Para hosting temporal del proyecto
Licencias académicas: Microsoft Azure, GitHub Education Pack
Asesoría metodológica: Servicio de apoyo a la investigación

Contactos Relevantes:

Coordinador del Máster: Dr. [Nombre del Coordinador]
Secretaría del Departamento: Para trámites administrativos
Oficina de Transferencia de Resultados de Investigación (OTRI): Para cuestiones de patentes/spin-offs si procede


16. CONCLUSIONES DEL DOCUMENTO DE PROPUESTA
16.1. Síntesis del Proyecto
DriveScore representa una oportunidad única de aplicar tecnología y principios de evaluación social para abordar uno de los problemas más graves de la sociedad moderna: los accidentes de tráfico. Con 1.35 millones de muertes anuales a nivel global, existe una necesidad urgente de soluciones innovadoras que complementen las medidas tradicionales de control y sanción.
El proyecto se fundamenta en una hipótesis sólida respaldada por estudios de psicología social y el éxito de plataformas como eBay, BlaBlaCar y Airbnb: cuando las personas saben que sus acciones son observables y evaluables, modifican su comportamiento hacia prácticas más responsables.
16.2. Viabilidad y Factibilidad
Viabilidad Técnica: ALTA

Tecnologías maduras y probadas (OCR, apps móviles, cloud)
Stack basado en software libre reduce costos y aumenta flexibilidad
Arquitectura escalable desde el inicio
Precedentes exitosos de reconocimiento de matrículas (OpenALPR, apps de parking)

Viabilidad Económica: ALTA

Costos iniciales casi nulos gracias a capas gratuitas de servicios cloud
Múltiples fuentes de monetización identificadas
Modelo freemium validado en otros sectores
Potencial de partnerships estratégicos con alto valor

Viabilidad Legal: MEDIA-ALTA

Existen precedentes legales positivos (Google Street View, Waze)
GDPR es manejable con asesoría adecuada y privacy by design
Experto en protección de datos disponible
Riesgos identificados con planes de mitigación

Viabilidad de Mercado: MEDIA

Problema real y universal
Competencia limitada en el nicho específico
Desafío principal: alcanzar masa crítica de usuarios
Estrategia de lanzamiento por ciudades reduce barrera de entrada

Viabilidad Académica: ALTA

Proyecto ambicioso pero realista para TFM de 3 meses
Combina investigación, desarrollo y validación
Cumple todos los requisitos de la normativa UHU
Potencial de publicaciones académicas posteriores

16.3. Valor Diferencial del TFM
Este Trabajo Fin de Máster se diferencia de TFMs tradicionales en varios aspectos:

Impacto Social Real: No es solo un ejercicio académico, sino el inicio de un proyecto con potencial de salvar vidas
Validación con Usuarios Reales: A diferencia de muchos TFMs que quedan en prototipos no utilizados, DriveScore será probado por usuarios reales desde el primer mes
Visión de Negocio: Incluye un plan completo de sostenibilidad y escalabilidad, no solo aspectos técnicos
Innovación Genuina: Aplica conceptos existentes (evaluación social, gamificación) a un dominio no explorado (conducción vial general)
Metodología Ágil Real: Verdadero desarrollo iterativo centrado en usuario, no cascada disfrazada
Tecnología Avanzada: Integra IA, visión artificial, arquitecturas cloud-native, desarrollo móvil multiplataforma
Potencial de Continuidad: Puede convertirse en startup, spin-off universitario o proyecto de investigación a largo plazo

16.4. Próximos Pasos Inmediatos
Para Gamaliel y el Dr. José Carpio, los siguientes pasos son:
Semana 1:

✅ Aprobar formalmente esta propuesta con coordinador del Máster
✅ Registrar el TFM en la plataforma oficial de la UHU
✅ Reunión de kick-off para revisar cronograma detallado
✅ Configurar repositorio GitHub y herramientas de gestión (Trello/Jira)
✅ Consulta inicial con experto en protección de datos

Semana 2:

✅ Revisión bibliográfica exhaustiva
✅ Análisis competitivo (instalar y probar apps similares)
✅ Primeras entrevistas con usuarios potenciales
✅ Definir stack tecnológico definitivo
✅ Configurar entorno de desarrollo

Semana 3-4:

✅ Desarrollo intensivo del MVP
✅ Sprints de 1 semana con revisiones con director
✅ Reclutamiento de usuarios piloto
✅ Preparación de materiales de onboarding


17. LLAMADA A LA ACCIÓN
17.1. Para Gamaliel Moreno Sánchez
Este TFM es una oportunidad extraordinaria de:

Aprender profundamente: Desde IA hasta arquitecturas cloud, desde diseño UX hasta modelos de negocio
Crear impacto real: Tu código puede contribuir a salvar vidas
Desarrollar portfolio: Un proyecto de esta envergadura te diferenciará en el mercado laboral
Explorar emprendimiento: Puede ser la semilla de tu propia startup
Contribuir a la sociedad: Ser parte de la solución a un problema global

Compromiso requerido:

20-25 horas/semana durante 12 semanas
Mentalidad de aprendizaje continuo
Apertura al feedback de usuarios
Resiliencia ante desafíos técnicos

Recompensas esperadas:

Calificación de Sobresaliente
Aplicación funcional en producción
Posible publicación académica
Red de contactos (aseguradoras, DGT, inversores)
Experiencia invaluable

17.2. Para el Dr. José Carpio Cañada
Este proyecto representa la materialización de:

Tu experiencia personal convertida en solución tecnológica
Tu visión de un mundo con mejor conducción vial
Tu legado como educador e innovador
Tu contribución a la seguridad vial global

Rol como director:

Guía metodológica y técnica para Gamaliel
Aportación de visión de negocio y estrategia
Conexión con stakeholders (DGT, aseguradoras)
Evangelización del proyecto en la comunidad universitaria
Posible continuidad post-TFM (investigación, spin-off)

17.3. Para la Universidad de Huelva
DriveScore puede ser:

Caso de éxito de innovación universitaria con impacto social
Modelo de TFMs con visión emprendedora y de negocio
Generador de publicaciones en congresos y revistas de prestigio
Atractor de financiación (proyectos europeos, convenios con empresas)
Visibilidad mediática positiva para la institución
Posible spin-off que genere empleo y transferencia de conocimiento


18. ANEXOS DE LA PROPUESTA
Anexo A: Referencias Bibliográficas Preliminares
Seguridad Vial y Psicología:

World Health Organization. (2023). Global Status Report on Road Safety 2023.
Elvik, R. (2018). The Psychology of Road Safety. Transport Reviews, 38(5).
Fuller, R. (2005). Towards a general theory of driver behaviour. Accident Analysis & Prevention, 37(3).

Tecnologías de Reconocimiento:
4. OpenALPR Documentation. (2024). Automatic License Plate Recognition.
5. Smith, J. et al. (2022). Deep Learning for Vehicle Plate Recognition: A Survey. IEEE Transactions on Intelligent Transportation Systems.
Economía Colaborativa y Reputación:
6. Botsman, R. & Rogers, R. (2010). What's Mine Is Yours: The Rise of Collaborative Consumption.
7. Teubner, T. & Flath, C. (2019). Privacy in the Sharing Economy. Journal of the Association for Information Systems.
Gamificación:
8. Deterding, S. et al. (2011). From Game Design Elements to Gamefulness. Proceedings of MindTrek.
9. Hamari, J. & Koivisto, J. (2015). Why Do People Use Gamification Services? International Journal of Information Management.
Legal y GDPR:
10. Voigt, P. & Von demReintentarJContinuarEditarBussche, A. (2017). The EU General Data Protection Regulation (GDPR): A Practical Guide. Springer.
11. European Data Protection Board. (2023). Guidelines on Video Surveillance and Image Processing.
12. Agencia Española de Protección de Datos. (2024). Guía sobre tratamiento de datos personales en aplicaciones móviles.
Movilidad y Seguridad Vial:
13. Dirección General de Tráfico (DGT). (2023). Anuario Estadístico de Accidentes de Tráfico en España.
14. European Transport Safety Council. (2023). Road Safety Performance Index.
15. Litman, T. (2023). Evaluating Transportation System Quality. Victoria Transport Policy Institute.
Desarrollo Móvil y Arquitecturas:
16. Google. (2024). Flutter Documentation: Building Cross-Platform Apps.
17. Vercel. (2024). Serverless Functions Best Practices.
18. Supabase. (2024). Building Scalable Backend Systems with PostgreSQL.
Inteligencia Artificial y OCR:
19. Redmon, J. & Farhadi, A. (2018). YOLOv3: An Incremental Improvement. arXiv.
20. Smith, R. (2007). An Overview of the Tesseract OCR Engine. Proceedings of ICDAR.
Modelos de Negocio:
21. Osterwalder, A. & Pigneur, Y. (2010). Business Model Generation. Wiley.
22. Ries, E. (2011). The Lean Startup. Crown Business.

Anexo B: Glosario de Términos Técnicos
ALD-X: Adrenoleucodistrofia ligada al cromosoma X. Enfermedad genética rara que afecta el sistema nervioso.
API (Application Programming Interface): Conjunto de definiciones y protocolos para construir e integrar software de aplicaciones.
BaaS (Backend as a Service): Modelo de servicio cloud que proporciona funcionalidad de backend (bases de datos, autenticación, etc.) como servicio.
CAC (Customer Acquisition Cost): Costo promedio de adquirir un nuevo cliente.
CDN (Content Delivery Network): Red de servidores distribuidos geográficamente que entregan contenido web de forma eficiente.
CI/CD (Continuous Integration/Continuous Deployment): Práctica de automatizar la integración y despliegue de código.
DAFO: Análisis de Debilidades, Amenazas, Fortalezas y Oportunidades.
DGT: Dirección General de Tráfico (España).
DPO (Data Protection Officer): Delegado de Protección de Datos, rol obligatorio bajo GDPR para ciertas organizaciones.
DPIA (Data Protection Impact Assessment): Evaluación de Impacto en la Protección de Datos.
ECTS: European Credit Transfer System. Sistema europeo de transferencia de créditos (1 ECTS = 25-30 horas de trabajo).
FCM (Firebase Cloud Messaging): Servicio de Google para enviar notificaciones push.
Flutter: Framework de Google para desarrollo de aplicaciones móviles multiplataforma.
Freemium: Modelo de negocio que ofrece servicios básicos gratuitos y premium de pago.
GDPR: General Data Protection Regulation (Reglamento General de Protección de Datos de la UE).
JWT (JSON Web Token): Estándar para crear tokens de acceso que permiten autenticación.
KPI (Key Performance Indicator): Indicador clave de rendimiento.
LOPDGDD: Ley Orgánica de Protección de Datos y Garantía de los Derechos Digitales (España).
LTV (Lifetime Value): Valor total que un cliente genera durante toda su relación con la empresa.
MVP (Minimum Viable Product): Producto mínimo viable con funcionalidades suficientes para validar el concepto.
NPS (Net Promoter Score): Métrica de satisfacción del cliente basada en probabilidad de recomendación.
OAuth 2.0: Protocolo estándar de autorización usado para acceso seguro a APIs.
OCR (Optical Character Recognition): Reconocimiento óptico de caracteres.
ODS: Objetivos de Desarrollo Sostenible de las Naciones Unidas.
OTRI: Oficina de Transferencia de Resultados de Investigación.
React Native: Framework de Facebook para desarrollo de aplicaciones móviles multiplataforma.
REST (Representational State Transfer): Estilo de arquitectura de software para servicios web.
SDK (Software Development Kit): Kit de desarrollo de software.
SaaS (Software as a Service): Software como servicio, modelo de distribución de software en la nube.
TAM/SAM/SOM: Total Addressable Market / Serviceable Available Market / Serviceable Obtainable Market.
TFM: Trabajo Fin de Máster.
UHU: Universidad de Huelva.
UX/UI: User Experience / User Interface (Experiencia de Usuario / Interfaz de Usuario).
WAF (Web Application Firewall): Cortafuegos de aplicaciones web.
YOLO (You Only Look Once): Algoritmo de detección de objetos en tiempo real.

Anexo C: Diagrama de Arquitectura Detallado
┌─────────────────────────────────────────────────────────────┐
│                    CAPA DE PRESENTACIÓN                      │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  ┌──────────────────┐         ┌──────────────────┐         │
│  │   App Móvil      │         │   Web Admin      │         │
│  │   (Flutter)      │         │   (React)        │         │
│  │                  │         │                  │         │
│  │ • Captura foto   │         │ • Moderación     │         │
│  │ • Evaluación     │         │ • Analytics      │         │
│  │ • Perfil         │         │ • Reportes       │         │
│  │ • Notificaciones │         │ • Gestión users  │         │
│  └──────────────────┘         └──────────────────┘         │
│           │                            │                     │
│           └────────────┬───────────────┘                     │
│                        │ HTTPS/TLS                           │
└────────────────────────┼─────────────────────────────────────┘
                         │
          ┌──────────────▼──────────────┐
          │    Cloudflare CDN/WAF        │
          │  • Cache                     │
          │  • DDoS Protection           │
          │  • SSL/TLS Termination       │
          └──────────────┬───────────────┘
                         │
┌────────────────────────┼─────────────────────────────────────┐
│                        │  CAPA DE LÓGICA (Backend)           │
├────────────────────────┼─────────────────────────────────────┤
│                        │                                      │
│         ┌──────────────▼────────────────┐                    │
│         │   API Gateway / Load Balancer │                    │
│         │   (Vercel / Cloud Run)        │                    │
│         └──────────────┬────────────────┘                    │
│                        │                                      │
│    ┌───────────────────┴──────────────────┐                 │
│    │                                        │                 │
│ ┌──▼───────────┐  ┌─────────────┐  ┌──────▼──────┐         │
│ │   Auth       │  │  Evaluations│  │   Users     │         │
│ │   Service    │  │   Service   │  │   Service   │         │
│ │              │  │             │  │             │         │
│ │ • Login      │  │ • CRUD      │  │ • Profiles  │         │
│ │ • Register   │  │ • Scoring   │  │ • Stats     │         │
│ │ • JWT        │  │ • Validation│  │ • Badges    │         │
│ └──────┬───────┘  └──────┬──────┘  └──────┬──────┘         │
│        │                  │                 │                 │
│        │         ┌────────▼─────────┐       │                 │
│        │         │  OCR Service     │       │                 │
│        │         │  (Cloud Vision / │       │                 │
│        │         │   OpenALPR)      │       │                 │
│        │         │                  │       │                 │
│        │         │ • Preprocessing  │       │                 │
│        │         │ • Recognition    │       │                 │
│        │         │ • Validation     │       │                 │
│        │         └────────┬─────────┘       │                 │
│        │                  │                 │                 │
│   ┌────▼──────────────────▼─────────────────▼────┐           │
│   │         Message Queue / Event Bus            │           │
│   │         (Cloud Tasks / RabbitMQ)             │           │
│   └────────────────────┬─────────────────────────┘           │
│                        │                                      │
└────────────────────────┼──────────────────────────────────────┘
                         │
┌────────────────────────┼──────────────────────────────────────┐
│              CAPA DE DATOS Y SERVICIOS                        │
├────────────────────────┼──────────────────────────────────────┤
│                        │                                       │
│  ┌─────────────────────▼──────────┐                          │
│  │   PostgreSQL Database          │                          │
│  │   (Supabase / Neon)            │                          │
│  │                                 │                          │
│  │  • Users                        │                          │
│  │  • Evaluations                  │                          │
│  │  • Vehicles                     │                          │
│  │  • Reports                      │                          │
│  └────────────────────────────────┘                          │
│                                                                │
│  ┌────────────────────────────────┐                          │
│  │   Redis Cache                  │                          │
│  │   • Session storage            │                          │
│  │   • Frequent queries           │                          │
│  │   • Rate limiting              │                          │
│  └────────────────────────────────┘                          │
│                                                                │
│  ┌────────────────────────────────┐                          │
│  │   Object Storage (S3/R2)       │                          │
│  │   • Profile photos             │                          │
│  │   • License plate images       │                          │
│  │   • Badges/assets              │                          │
│  └────────────────────────────────┘                          │
│                                                                │
│  ┌────────────────────────────────┐                          │
│  │   Analytics & Monitoring       │                          │
│  │   • Plausible / Matomo         │                          │
│  │   • Sentry (errors)            │                          │
│  │   • Grafana + Prometheus       │                          │
│  └────────────────────────────────┘                          │
│                                                                │
└────────────────────────────────────────────────────────────────┘

┌────────────────────────────────────────────────────────────────┐
│                    SERVICIOS EXTERNOS                          │
├────────────────────────────────────────────────────────────────┤
│  • Firebase Cloud Messaging (Push Notifications)               │
│  • Sendgrid / Mailgun (Email Transaccional)                    │
│  • Stripe (Pagos - futuro)                                     │
│  • Google Maps API (Geolocalización)                           │
└────────────────────────────────────────────────────────────────┘

Anexo D: Mockups Preliminares de Interfaz
Pantalla 1: Onboarding
┌─────────────────────────┐
│  DriveScore 🚗          │
├─────────────────────────┤
│                         │
│    [Ilustración de      │
│     conductores         │
│     evaluándose]        │
│                         │
│  Conduce Mejor,         │
│  Demuéstralo            │
│                         │
│  Evalúa y sé evaluado   │
│  por otros conductores  │
│                         │
│  ┌───────────────────┐  │
│  │  Comenzar  →      │  │
│  └───────────────────┘  │
│                         │
│  ○ ○ ● ○                │
└─────────────────────────┘
Pantalla 2: Captura de Matrícula
┌─────────────────────────┐
│  ← DriveScore           │
├─────────────────────────┤
│                         │
│  ┌─────────────────────┐│
│  │                     ││
│  │   [VISTA CÁMARA]    ││
│  │                     ││
│  │   ┌─────────────┐   ││
│  │   │  1234 ABC   │   ││ ← Marco de enfoque
│  │   └─────────────┘   ││
│  │                     ││
│  └─────────────────────┘│
│                         │
│  Enfoca la matrícula    │
│  del vehículo           │
│                         │
│         ┌───┐           │
│         │ 📷 │           │
│         └───┘           │
│                         │
│  [✍️ Introducir manual] │
└─────────────────────────┘
Pantalla 3: Evaluación
┌─────────────────────────┐
│  ← Evaluar 1234 ABC     │
├─────────────────────────┤
│                         │
│  Puntuación General:    │
│  ★ ★ ★ ★ ☆             │
│                         │
│  Categorías:            │
│                         │
│  Respeto peatones       │
│  ★ ★ ★ ★ ★             │
│                         │
│  Uso intermitentes      │
│  ★ ★ ★ ★ ☆             │
│                         │
│  Distancia seguridad    │
│  ★ ★ ★ ★ ☆             │
│                         │
│  Velocidad adecuada     │
│  ★ ★ ★ ★ ★             │
│                         │
│  ┌─────────────────────┐│
│  │ Comentario (opc)    ││
│  │                     ││
│  └─────────────────────┘│
│                         │
│  ┌───────────────────┐  │
│  │  Enviar Evaluación│  │
│  └───────────────────┘  │
└─────────────────────────┘
Pantalla 4: Perfil de Usuario
┌─────────────────────────┐
│  ☰ Mi Perfil       ⚙️   │
├─────────────────────────┤
│                         │
│      [Foto]             │
│   José Carpio           │
│                         │
│  ★★★★★ 4.8/5.0         │
│  Conductor Experto 🏆   │
│                         │
│  📊 Estadísticas:       │
│  • 342 evaluaciones     │
│  • 30 años conduciendo  │
│  • 0 accidentes         │
│                         │
│  🎖️ Insignias:          │
│  🌟 Veterano            │
│  🚦 Respeto Total       │
│  🤝 Cortés              │
│                         │
│  ┌───────────────────┐  │
│  │ Ver historial     │  │
│  └───────────────────┘  │
│  ┌───────────────────┐  │
│  │ Compartir perfil  │  │
│  └───────────────────┘  │
└─────────────────────────┘
Pantalla 5: Ranking
┌─────────────────────────┐
│  ← Top Conductores 🏆   │
├─────────────────────────┤
│  📍 Huelva              │
│                         │
│  1. 🥇 María G.         │
│     ★★★★★ 4.95         │
│     523 evaluaciones    │
│                         │
│  2. 🥈 Carlos R.        │
│     ★★★★★ 4.89         │
│     412 evaluaciones    │
│                         │
│  3. 🥉 Ana M.           │
│     ★★★★★ 4.87         │
│     389 evaluaciones    │
│                         │
│  ...                    │
│                         │
│  23. 👤 Tú              │
│     ★★★★☆ 4.65         │
│     87 evaluaciones     │
│                         │
│  ┌─────┬─────┬─────┐   │
│  │Local│ Nac │Mundo│   │
│  └─────┴─────┴─────┘   │
└─────────────────────────┘

Anexo E: Ejemplo de Código (Reconocimiento de Matrícula)
python# ocr_service.py - Servicio de Reconocimiento de Matrículas

import cv2
import numpy as np
from openalpr import Alpr
import re

class LicensePlateRecognizer:
    """
    Servicio para reconocer matrículas españolas desde imágenes
    """
    
    def __init__(self, config_path="/etc/openalpr/openalpr.conf",
                 runtime_data_path="/usr/share/openalpr/runtime_data"):
        """
        Inicializa el reconocedor con configuración OpenALPR
        """
        self.alpr = Alpr("eu", config_path, runtime_data_path)
        if not self.alpr.is_loaded():
            raise Exception("Error al cargar OpenALPR")
        
        # Configuración optimizada para España
        self.alpr.set_top_n(3)  # Top 3 resultados
        self.alpr.set_default_region("es")
        
        # Patrón matrícula española: 0000 XXX
        self.spanish_pattern = re.compile(r'^\d{4}\s?[A-Z]{3}$')
    
    def preprocess_image(self, image_path):
        """
        Preprocesa la imagen para mejorar reconocimiento
        """
        # Leer imagen
        img = cv2.imread(image_path)
        
        # Convertir a escala de grises
        gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
        
        # Mejorar contraste (CLAHE)
        clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8,8))
        enhanced = clahe.apply(gray)
        
        # Reducir ruido
        denoised = cv2.fastNlMeansDenoising(enhanced)
        
        # Guardar temporalmente imagen procesada
        temp_path = "/tmp/processed_plate.jpg"
        cv2.imwrite(temp_path, denoised)
        
        return temp_path
    
    def recognize(self, image_path, confidence_threshold=75):
        """
        Reconoce matrícula desde imagen
        
        Returns:
            dict: {
                'plate': str,
                'confidence': float,
                'candidates': list,
                'success': bool
            }
        """
        try:
            # Preprocesar imagen
            processed_image = self.preprocess_image(image_path)
            
            # Reconocer con OpenALPR
            results = self.alpr.recognize_file(processed_image)
            
            if not results['results']:
                return {
                    'success': False,
                    'error': 'No se detectó ninguna matrícula'
                }
            
            # Procesar resultados
            candidates = []
            for plate in results['results']:
                plate_text = plate['plate'].upper().replace('-', '').replace(' ', '')
                confidence = plate['confidence']
                
                # Validar formato español
                if self.validate_spanish_plate(plate_text):
                    formatted_plate = self.format_plate(plate_text)
                    candidates.append({
                        'plate': formatted_plate,
                        'confidence': confidence
                    })
            
            # Ordenar por confianza
            candidates.sort(key=lambda x: x['confidence'], reverse=True)
            
            if candidates and candidates[0]['confidence'] >= confidence_threshold:
                return {
                    'success': True,
                    'plate': candidates[0]['plate'],
                    'confidence': candidates[0]['confidence'],
                    'candidates': candidates[:3]
                }
            else:
                return {
                    'success': False,
                    'error': 'Confianza insuficiente en el reconocimiento',
                    'candidates': candidates
                }
                
        except Exception as e:
            return {
                'success': False,
                'error': f'Error en reconocimiento: {str(e)}'
            }
    
    def validate_spanish_plate(self, plate_text):
        """
        Valida que la matrícula siga formato español
        """
        # Formato: 4 dígitos + 3 letras
        return bool(self.spanish_pattern.match(plate_text))
    
    def format_plate(self, plate_text):
        """
        Formatea matrícula al estándar español: 0000 XXX
        """
        if len(plate_text) == 7:
            return f"{plate_text[:4]} {plate_text[4:]}"
        return plate_text
    
    def __del__(self):
        """
        Libera recursos de OpenALPR
        """
        if hasattr(self, 'alpr'):
            self.alpr.unload()

# Ejemplo de uso
if __name__ == "__main__":
    recognizer = LicensePlateRecognizer()
    
    result = recognizer.recognize("plate_image.jpg")
    
    if result['success']:
        print(f"✅ Matrícula reconocida: {result['plate']}")
        print(f"📊 Confianza: {result['confidence']}%")
    else:
        print(f"❌ Error: {result['error']}")
        if 'candidates' in result and result['candidates']:
            print("🔍 Candidatos encontrados:")
            for c in result['candidates']:
                print(f"   - {c['plate']} ({c['confidence']}%)")

Anexo F: Plantilla de Entrevista a Usuarios Piloto
ENTREVISTA POST-PILOTO - DRIVESCORE
Fecha: _______________
Usuario: _______________
Duración uso app: _____ días
Nº evaluaciones realizadas: _____
SECCIÓN 1: EXPERIENCIA GENERAL

¿Cómo describirías DriveScore a un amigo en una frase?
En una escala de 1-10, ¿qué probabilidad hay de que recomiendes DriveScore? ___/10
¿Por qué?
¿Qué fue lo que más te gustó de la app?
¿Qué fue lo que menos te gustó?

SECCIÓN 2: USABILIDAD

¿Fue fácil registrarte y empezar a usar la app?
□ Muy fácil  □ Fácil  □ Normal  □ Difícil  □ Muy difícil
¿El reconocimiento de matrículas funcionó bien?
□ Siempre  □ La mayoría de veces  □ A veces  □ Raramente  □ Nunca
¿Fue intuitivo el proceso de evaluación?
□ Sí, totalmente  □ Mayormente  □ Algo confuso  □ Muy confuso
¿Hubo alguna funcionalidad que no entendieras o que fuera confusa?

SECCIÓN 3: IMPACTO EN COMPORTAMIENTO

¿Has modificado tu forma de conducir sabiendo que puedes ser evaluado?
□ Sí, significativamente  □ Sí, un poco  □ No
Si respondiste sí, ¿qué comportamientos has cambiado?
□ Uso de intermitentes
□ Ceder el paso
□ Respeto a peatones
□ Distancia de seguridad
□ Velocidad
□ Cortesía general
□ Otro: _______________
¿Has evaluado a conductores por comportamientos positivos o negativos?
□ Solo positivos  □ Mayormente positivos  □ Ambos por igual
□ Mayormente negativos  □ Solo negativos

SECCIÓN 4: PREOCUPACIONES Y SUGERENCIAS

¿Tienes alguna preocupación sobre privacidad o uso de datos?
□ Sí  □ No
Si sí, ¿cuál?
¿Has experimentado o te preocupa el uso malintencionado (evaluaciones falsas, acoso)?
□ Sí, lo he experimentado  □ Me preocupa  □ No me preocupa
¿Qué funcionalidad adicional te gustaría que tuviera DriveScore?
¿Pagarías por una versión Premium? ¿Qué funciones justificarían el pago?

SECCIÓN 5: VISIÓN DE FUTURO

¿Crees que DriveScore podría mejorar la seguridad vial si muchas personas lo usaran?
□ Definitivamente  □ Probablemente  □ Quizás  □ Probablemente no  □ Definitivamente no
¿Usarías tu puntuación DriveScore para obtener descuentos en seguros?
□ Sí  □ No  □ Depende
Comentarios finales, sugerencias o ideas:


¡GRACIAS POR TU COLABORACIÓN!

CONCLUSIÓN FINAL DE LA PROPUESTA
DriveScore no es solo un Trabajo Fin de Máster; es el punto de partida de un movimiento hacia una cultura vial más segura, respetuosa y consciente.
Combinando tecnología puntera (IA, apps móviles, arquitecturas cloud), principios de economía colaborativa probados, y una misión social profunda, este proyecto tiene el potencial de:
✅ Salvar vidas reduciendo comportamientos de riesgo en carretera
✅ Empoderar ciudadanos dándoles voz en la seguridad vial
✅ Generar datos valiosos para mejores políticas públicas
✅ Crear conciencia sobre la responsabilidad individual en carretera
✅ Transformar la cultura hacia el concepto de "aldea global digital"
Para Gamaliel, es una oportunidad de aprendizaje excepcional y un proyecto que podrá mostrar con orgullo durante toda su carrera.
Para José, es la materialización de una visión personal en una solución tecnológica con impacto global.
Para la Universidad de Huelva, es un ejemplo de innovación universitaria con relevancia social y potencial comercial.
El camino comienza ahora. ¡Manos a la obra! 🚗💨

Documento preparado por:
Claude (Anthropic) en colaboración con Dr. José Carpio Cañada
Universidad de Huelva
Octubre 2025
Versión: 1.0
Páginas: 47 (sin anexos técnicos adicionales)

"Cuando las personas saben que están siendo observadas, se comportan mejor. No por temor al castigo, sino por respeto a la comunidad de la que forman parte."
— Principio fundamental de DriveScore


### Con la Ayuda de Claude AI
https://claude.ai/public/artifacts/f9057139-b87a-4b7c-9f2f-8198639bd85a
https://claude.ai/share/19b22b0a-4fd0-4e22-a3ef-4483c1be15be

#### **
