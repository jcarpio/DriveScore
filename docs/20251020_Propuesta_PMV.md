# DriveSkore: Sistema de Reconocimiento Social para Conductores Responsables

## Documento Técnico del Proyecto

**Versión:** 1.0  
**Fecha:** Octubre 2025  
**Autores:** Equipo DriveSkore  
**Estado:** Diseño MVP

---

## Tabla de Contenidos

1. [Introducción al Problema](#1-introducción-al-problema)
2. [Nudo: Desarrollo del Problema](#2-nudo-desarrollo-del-problema)
3. [Desenlace: Solución Propuesta](#3-desenlace-solución-propuesta)
4. [Arquitectura Técnica](#4-arquitectura-técnica)
5. [Plan de Desarrollo](#5-plan-de-desarrollo)
6. [Referencias](#6-referencias)

---

## 1. Introducción al Problema

### 1.1 El Contexto de la Seguridad Vial Global

La seguridad vial constituye uno de los desafíos de salud pública más importantes del siglo XXI. Según la Organización Mundial de la Salud (OMS), aproximadamente 1.19 millones de personas mueren cada año en accidentes de tráfico, siendo la principal causa de muerte entre jóvenes de 5 a 29 años a nivel mundial. Además, entre 20 y 50 millones de personas sufren lesiones no mortales, muchas de ellas con discapacidades permanentes.

**Datos clave de la OMS (2023):**
- Los accidentes de tráfico cuestan a la mayoría de los países el 3% de su PIB
- Más del 90% de las muertes por tráfico ocurren en países de ingresos bajos y medianos
- Los usuarios vulnerables de la vía (peatones, ciclistas, motoristas) representan más del 50% de todas las muertes por tráfico

### 1.2 El Problema de los Comportamientos en la Vía

La investigación en psicología del tráfico ha identificado que **el comportamiento humano es el factor crítico en más del 90% de los accidentes de tráfico**. Según un estudio publicado en *Accident Analysis & Prevention* (2018), los comportamientos de riesgo incluyen:

- Velocidad excesiva (30% de muertes por tráfico)
- Conducción bajo efectos de alcohol/drogas (20-25%)
- No uso de cinturón de seguridad (contribuye al 50% de muertes)
- Distracción al volante (especialmente uso de móviles)
- **Adelantamientos inseguros y falta de respeto a usuarios vulnerables** (ciclistas, peatones)

Un metaanálisis de la revista *Transportation Research Part F: Traffic Psychology and Behaviour* (2020) demostró que la **intervención más efectiva para cambiar comportamientos viales es el refuerzo social positivo**, siendo hasta 3 veces más efectivo que las sanciones punitivas aisladas.

### 1.3 El Caso Específico de Ciclistas y Usuarios Vulnerables

La Directiva Europea 2022/2561 establece distancias mínimas de seguridad al adelantar ciclistas:
- **1.5 metros en vías urbanas**
- **2 metros en carreteras interurbanas**

Sin embargo, estudios de la *European Cyclists' Federation* (2023) muestran que:
- El 73% de los ciclistas ha experimentado adelantamientos peligrosos
- Solo el 15% de los conductores respeta consistentemente las distancias de seguridad
- El 68% de los accidentes ciclista-vehículo ocurren durante maniobras de adelantamiento

### 1.4 Limitaciones de los Sistemas Actuales

#### 1.4.1 Enfoques Punitivos

Los sistemas tradicionales de control de tráfico se basan en:
- Multas y sanciones
- Sistemas de puntos del carnet
- Vigilancia por radar y cámaras

**Limitación principal:** La investigación en criminología y psicología conductual (Journal of Applied Psychology, 2019) muestra que **el castigo sin refuerzo positivo genera:**
- Cumplimiento superficial (solo cuando hay vigilancia)
- Resentimiento hacia las autoridades
- No internalización de comportamientos seguros
- Efecto limitado en cambio cultural a largo plazo

#### 1.4.2 Programas de Concienciación

Las campañas educativas tienen impacto limitado:
- Estudio de la revista *Injury Prevention* (2021): las campañas de concienciación solo tienen efecto significativo en el 12-18% de la población
- Requieren inversión continua en publicidad
- No proporcionan feedback inmediato sobre comportamientos específicos

#### 1.4.3 Tecnología Actual

Los sistemas ADAS (Advanced Driver Assistance Systems) ayudan, pero:
- Solo disponibles en vehículos de alta gama
- No reconocen comportamientos socialmente positivos
- No crean comunidad ni cultura vial
- No gamifican la conducción segura

### 1.5 La Oportunidad: Tecnología + Psicología Social

La confluencia de tres factores crea una oportunidad única:

1. **Ubicuidad de smartphones:** 6.8 mil millones de usuarios globales (Statista, 2024)
2. **Conectividad IoT:** Bluetooth Low Energy, GPS de alta precisión, sensores de movimiento
3. **Gamificación probada:** Aplicaciones como Strava, Duolingo, y Exercism han demostrado que el reconocimiento social y la gamificación cambian comportamientos masivamente

Un estudio en *Computers in Human Behavior* (2022) mostró que aplicaciones con gamificación aumentan el engagement del usuario en un **238% comparado con apps sin elementos lúdicos**.

### 1.6 Hipótesis del Proyecto

> **Si creamos un sistema que permite a los usuarios reconocer y ser reconocidos por comportamientos positivos en la vía, gamificando la experiencia y proporcionando beneficios tangibles (como descuentos en seguros), entonces podremos:**
>
> 1. Aumentar la frecuencia de comportamientos seguros (especialmente respeto a usuarios vulnerables)
> 2. Crear una cultura vial positiva basada en reconocimiento mutuo
> 3. Generar datos valiosos sobre patrones de tráfico y comportamiento
> 4. Proporcionar un modelo de negocio sostenible basado en datos (similar a Google/Facebook)

---

## 2. Nudo: Desarrollo del Problema

### 2.1 Desafíos Técnicos

#### 2.1.1 Identificación de Usuarios en Movimiento

**El problema central:** Cómo identificar de forma **unívoca, consentida y precisa** a un usuario específico entre múltiples participantes en un entorno de tráfico dinámico (velocidades de 30-120 km/h, ventanas temporales de 2-5 segundos).

##### Opciones tecnológicas analizadas:

| Tecnología | Precisión | Alcance | Latencia | Privacidad | Viabilidad |
|------------|-----------|---------|----------|------------|------------|
| **GPS** | ±5-15m | Global | 1-3s | ⚠️ Tracking | ✅ Alta |
| **Bluetooth LE** | ±10-50m | 100m | <100ms | ✅ Buena | ✅ Alta |
| **WiFi MAC** | ±20-100m | 200m | Variable | ❌ Randomización | ⚠️ Media |
| **Cámara + OCR** | ±1m | 50m | 2-5s | ❌ Muy invasiva | ❌ Baja |
| **V2V (Veh. to Veh.)** | ±1m | 300m | <50ms | ✅ Excelente | ❌ Requiere hardware específico |

**Conclusión de análisis:** Un sistema híbrido **BLE + GPS + Acelerómetro** proporciona el mejor balance entre precisión, privacidad, coste y viabilidad de implementación inmediata.

##### Fundamento científico:

Un paper de *IEEE Transactions on Intelligent Transportation Systems* (2023) titulado "Hybrid Positioning Systems for Connected Vehicles" demostró que combinar BLE para proximidad con GPS para contexto espacial reduce el error de identificación a menos del 3% en escenarios urbanos complejos.

#### 2.1.2 El Problema de la Ventana Temporal

Cuando un conductor presencia un comportamiento positivo (ej: adelantamiento seguro a ciclista), tiene aproximadamente **2-4 segundos** antes de que el momento pase y la memoria del evento se difumine.

**Investigación relevante:**
- *Cognitive Psychology* (2019): La memoria episódica de eventos en conducción decae un 50% después de 10 segundos sin refuerzo
- *Human Factors in Transportation* (2021): Interacciones que requieren más de 2 segundos de atención visual fuera de la carretera aumentan el riesgo de accidente en 23x

**Implicación de diseño:** El sistema debe permitir **registro instantáneo (1 botón, <1 segundo) sin requerir atención visual**, postponiendo la confirmación detallada para cuando el usuario esté seguro.

#### 2.1.3 Desafío de Privacidad y GDPR

La regulación europea GDPR (2018) y regulaciones equivalentes globales imponen restricciones estrictas:

**Artículos relevantes:**
- **Art. 6:** Requiere base legal para procesamiento (consentimiento explícito en nuestro caso)
- **Art. 25:** Privacy by Design - minimización de datos desde el diseño
- **Art. 32:** Seguridad del procesamiento (encriptación, pseudonimización)

**Solución arquitectónica:**
1. **Opt-in obligatorio:** Solo usuarios que consienten participan
2. **Token rotativo:** Identificadores BLE rotan cada 15 minutos (similar a Google/Apple Exposure Notification)
3. **Resolución diferida:** Los IDs reales solo se resuelven en servidor después de confirmación explícita del voto
4. **Datos agregados:** Para monetización, solo se comparten patrones agregados, nunca datos individuales sin consentimiento

Un análisis legal publicado en *Computer Law & Security Review* (2023) confirma que sistemas opt-in con pseudonimización y minimización de datos cumplen con GDPR si se implementan correctamente.

#### 2.1.4 Consumo de Batería

**El problema:** Las apps de navegación (Google Maps, Waze) consumen 15-25% de batería por hora. Un sistema que debe correr continuamente en background no puede exceder el 8-10% por hora para ser viable.

**Estrategias de optimización basadas en investigación:**

Según *ACM Transactions on Sensor Networks* (2022):
- **GPS adaptativo:** Usar "significant location changes" reduce consumo en 60%
- **BLE duty cycle:** Escaneos cada 5-10s vs. continuo = reducción del 75% en consumo
- **Sensor fusion:** Usar acelerómetro para detectar movimiento antes de activar GPS = ahorro del 40%
- **Geofencing:** Desactivar fuera de áreas urbanas/carreteras

**Objetivo técnico:** ≤8% batería/hora con monitorización activa

### 2.2 Desafíos de Experiencia de Usuario

#### 2.2.1 Fricción en el Registro del Evento

**Problema UX:** Balance entre captura rápida y precisión.

**Evolución de diseño:**

❌ **Versión 1 (descartada):** Abrir app → seleccionar usuario → votar  
*Tiempo: 8-15 segundos, requiere mirar pantalla*

❌ **Versión 2 (descartada):** Botón en pantalla mientras se conduce  
*Peligroso, distracción visual*

✅ **Versión 3 (elegida):** Botón físico BLE → Revisión posterior en seguridad  
*Tiempo de captura: <1 segundo, 0 distracción visual*

Esta aproximación se alinea con la investigación de *Applied Ergonomics* (2020) que establece que **interfaces hápticas/físicas reducen la carga cognitiva en un 67% vs. interfaces táctiles en pantalla durante tareas de conducción**.

#### 2.2.2 Motivación para Revisión Posterior

**Desafío:** ¿Por qué un usuario revisaría eventos horas después?

**Estrategias de engagement:**

1. **Notificaciones push inteligentes:**
   - "Tienes 3 eventos pendientes de revisar 🎯"
   - "¡Alguien te votó hoy! Revisa tus votos pendientes"

2. **Gamificación del proceso de revisión:**
   - XP por confirmar votos
   - Streak de días consecutivos revisando
   - Badges por precisión en votación

3. **Curiosidad social:**
   - "¿Era el Tesla azul o el BMW rojo quien te cedió el paso?"
   - Preview de candidatos genera curiosidad

#### 2.2.3 Cold Start Problem

**Problema clásico de redes sociales:** La app no es útil hasta que hay masa crítica de usuarios.

**Estrategia de lanzamiento:**

1. **Beta en comunidades ciclistas** (usuarios más motivados por tema de seguridad)
2. **Partnerships con escuelas de conducción**
3. **Pilotos corporativos** (flotas de empresa que quieren mejorar imagen/seguros)
4. **Incentivos iniciales** de compañías de seguros para early adopters

Caso de estudio: **Waze** alcanzó masa crítica con estrategia similar, enfocándose primero en early adopters tech-savvy antes de escalar (Harvard Business Review, 2018).

### 2.3 Desafíos de Modelo de Negocio

#### 2.3.1 Monetización con Datos: El Modelo Facebook/Google

**Premisa:** "Si el producto es gratis, tú eres el producto"

**Pero con responsabilidad ética:**

La investigación en *Journal of Business Ethics* (2021) muestra que los usuarios están dispuestos a compartir datos de movilidad **si:**
1. Se les informa claramente qué se recopila
2. Reciben valor tangible a cambio
3. Los datos se agregan y anonimizan
4. Pueden optar por no participar en cualquier momento

**Flujos de monetización viables:**

##### A) Compañías de Seguros
- **Modelos de seguro basados en comportamiento** (Usage-Based Insurance)
- Los usuarios con buena reputación obtienen descuentos del 10-30%
- Mercado global estimado: $32 mil millones para 2030 (Allied Market Research, 2023)

##### B) Administraciones Públicas
- **Datos agregados de patrones de tráfico** para planificación urbana
- **Identificación de puntos negros** de conflicto ciclista-vehículo
- Ciudades ya pagan por estos datos a Waze, Google Maps

##### C) Investigación Académica
- **Estudios de comportamiento vial**
- Datos anonimizados para universidades e institutos de investigación

##### D) Advertising Contextual (Futuro)
- Anuncios relevantes no invasivos (ej: talleres mecánicos cercanos)
- Sin tracking individual, solo patrones agregados

**Referencia:** El modelo de Strava con "Strava Metro" (venta de datos agregados de ciclistas a ciudades) genera millones anuales manteniendo privacidad individual (*Wired*, 2022).

#### 2.3.2 Incentivos para Compañías de Seguros

**La propuesta de valor:**

Las aseguradoras tienen interés económico directo en conductores más seguros:
- Reducción de siniestralidad = menos pagos
- Selección de riesgos más precisa
- Engagement con clientes jóvenes (mercado creciente)

**Precedentes exitosos:**

- **Progressive Snapshot** (USA): Descuentos hasta 30% por conducción segura
- **Línea Directa** (España): Ya ofrece descuentos por telemetría
- **Admiral LittleBox** (UK): App de conducción con descuentos del 30%

Estudio de *Insurance Journal* (2023): El 68% de conductores menores de 35 años están dispuestos a compartir datos de conducción por descuentos del 15% o más.

### 2.4 Desafíos Técnicos de Escalabilidad

#### 2.4.1 Procesamiento de Eventos Geoespaciales

**Volumen esperado a escala:**
- 1 millón de usuarios activos
- Promedio 2 trayectos/día de 30 min
- GPS ping cada 5 segundos
- = **~1.7 mil millones de puntos GPS/día**

**Arquitectura necesaria:**

Según *VLDB Journal* (2023) sobre sistemas de bases de datos geoespaciales:
- **PostGIS** con particionamiento temporal + índices espaciales (R-tree)
- **Redis** para matching en tiempo real de eventos
- **Kafka/RabbitMQ** para cola de eventos asíncronos
- **Cassandra/ScyllaDB** para time-series de tracking

**Coste de infraestructura estimado:** $5,000-$10,000/mes para 1M usuarios (AWS/GCP)

#### 2.4.2 Matching Algorítmico

**El problema computacional:** Dado un evento en (lat, lon, timestamp), encontrar todos los candidatos potenciales en:
- ±50 metros espaciales
- ±30 segundos temporales
- Con dirección de movimiento compatible

**Complejidad naive:** O(n²) para n usuarios → inviable

**Optimización con estructuras de datos espaciales:**

```
Geohash + temporal indexing:
1. Particionar espacio en células (geohash precision 7 ≈ 153m)
2. Solo buscar en célula actual + células adyacentes (9 celdas)
3. Filtro secundario por timestamp
4. Filtro terciario por dirección

Complejidad: O(k) donde k << n
```

Basado en paper de *ACM SIGSPATIAL* (2022): "Efficient Spatio-Temporal Join Queries for Large-Scale Location Data"

### 2.5 Desafíos Culturales y Sociales

#### 2.5.1 Riesgo de Toxicidad

**Aprendizaje de otras plataformas:**

Cuando permitimos evaluaciones entre usuarios, existe riesgo de:
- Venganza/votos falsos
- Discriminación
- Acoso

**Mitigación desde diseño:**

1. **Solo votos positivos inicialmente** (aprendizaje de Duolingo: solo racha positiva)
2. **Sin votos negativos públicos** (evita shaming)
3. **Sistema de reportes** para comportamientos extremadamente peligrosos (pero revisión humana)
4. **Rate limiting:** Máximo X votos por día para prevenir spam
5. **Machine Learning** para detectar patrones de abuso

#### 2.5.2 Adopción Cultural por Regiones

La cultura vial varía enormemente:
- Países nórdicos: Alta disciplina vial
- Sur de Europa: Más caóticos pero sociales
- Asia: Densidad extrema, normas diferentes

**Estrategia:** Lanzamiento por oleadas geográficas, adaptando gamificación y mensajes a cultura local.

#### 2.5.3 El Factor "Hermano Mayor"

Algunas personas rechazan cualquier forma de tracking, incluso voluntario.

**Respuesta:**
- Transparencia total sobre qué se recopila
- Código abierto (open source) para auditoría
- Opción de "modo privado" (no participar pero seguir usando algunas funciones)
- Encriptación end-to-end de datos sensibles

---

## 3. Desenlace: Solución Propuesta

### 3.1 Visión del Producto

**DriveSkore** es una aplicación móvil que transforma la conducción en una experiencia social positiva, permitiendo a los usuarios reconocer y ser reconocidos por comportamientos seguros en la vía, especialmente el respeto a usuarios vulnerables como ciclistas y peatones.

#### 3.1.1 Propuesta de Valor

**Para Conductores/Ciclistas:**
- Reconocimiento social por conducción segura
- Descuentos en seguros (10-30%)
- Gamificación divertida del tráfico
- Sensación de contribuir a vías más seguras

**Para Compañías de Seguros:**
- Selección de riesgos más precisa
- Reducción de siniestralidad
- Engagement con clientes jóvenes
- Diferenciación competitiva

**Para Administraciones Públicas:**
- Datos de tráfico en tiempo real
- Identificación de puntos conflictivos
- Medición de impacto de infraestructura ciclista
- Evidencia para políticas de movilidad

**Para la Sociedad:**
- Reducción de accidentes con usuarios vulnerables
- Cambio cultural hacia conducción más empática
- Datos abiertos para investigación en seguridad vial

### 3.2 Arquitectura de la Solución: Enfoque Híbrido

#### 3.2.1 Componentes del Sistema

```
┌─────────────────────────────────────────────────────────┐
│                    USUARIO EN VEHÍCULO                   │
│                                                           │
│  ┌──────────────┐          ┌──────────────────────┐    │
│  │ Botón BLE    │◄────────►│  Smartphone con App  │    │
│  │ (Volante)    │ Bluetooth │  - GPS               │    │
│  │              │          │  - Acelerómetro       │    │
│  │ [  VOTO  ]   │          │  - BLE Scanner        │    │
│  └──────────────┘          │  - Background Service│    │
│                             └──────────────────────┘    │
└─────────────────────────────────────────────────────────┘
                              │
                              │ 4G/5G/WiFi (cuando disponible)
                              ▼
┌─────────────────────────────────────────────────────────┐
│                     BACKEND CLOUD                        │
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  API REST    │  │  Matching    │  │  Analytics   │  │
│  │  (Node.js)   │  │  Engine      │  │  BigQuery    │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
│          │                  │                  │         │
│          ▼                  ▼                  ▼         │
│  ┌──────────────────────────────────────────────────┐  │
│  │         PostgreSQL + PostGIS + Redis             │  │
│  │         (Usuarios, Eventos, Geolocation)         │  │
│  └──────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
                              │
                              │ APIs / Data Exports
                              ▼
┌─────────────────────────────────────────────────────────┐
│                    PARTNERS / CLIENTES                   │
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  Compañías   │  │ Ayuntamientos│  │ Investigación│  │
│  │  de Seguros  │  │  y Gobiernos │  │  Académica   │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
└─────────────────────────────────────────────────────────┘
```

#### 3.2.2 Flujo de Datos y Eventos

**Fase 1: Captura (Durante conducción)**

```
1. App en background monitorizando:
   ├─ GPS: cada 3-5 seg
   ├─ BLE: escaneo cada 5-10 seg
   └─ Acelerómetro: continuo (detección de movimiento)

2. Usuario presiona botón BLE
   ├─ App recibe señal vía Bluetooth
   ├─ Marca timestamp exacto
   ├─ Captura snapshot:
   │  ├─ Ubicación GPS actual
   │  ├─ Velocidad y dirección (del acelerómetro + GPS)
   │  ├─ Buffer de últimos 30s de usuarios BLE detectados
   │  └─ Contexto (tipo de vía, hora, condiciones)
   ├─ Guarda localmente en SQLite
   └─ Feedback háptico al usuario (vibración)

3. Si hay conexión → Sync a servidor (background)
   Si no hay conexión → Queue para sync posterior
```

**Fase 2: Matching (Backend)**

```
Evento llega al servidor:
├─ 1. Validación básica (timestamp coherente, ubicación válida)
├─ 2. Query geoespacial en PostGIS:
│     SELECT * FROM user_locations
│     WHERE ST_DWithin(
│         location::geography,
│         ST_SetSRID(ST_MakePoint($event_lon, $event_lat), 4326)::geography,
│         50  -- 50 metros
│     )
│     AND timestamp BETWEEN $event_time - 30s AND $event_time + 30s
│     AND user_id != $voter_id
│
├─ 3. Filtro por dirección de movimiento:
│     - Calcular bearing de cada candidato
│     - Descartar si diferencia > 45°
│
├─ 4. Score de probabilidad para cada candidato:
│     score = w1 * distance_score + 
│             w2 * time_score + 
│             w3 * direction_score +
│             w4 * blelue_detection_score
│
├─ 5. Ordenar candidatos por score
└─ 6. Devolver top 5 candidatos al votante
```

**Fase 3: Confirmación (Usuario en casa)**

```
Usuario abre app:
├─ Ve lista de "Eventos pendientes" (3)
├─ Para cada evento:
│  ├─ Muestra mapa con trayectoria
│  ├─ Lista candidatos con:
│  │  ├─ Foto del vehículo
│  │  ├─ Marca, modelo, color
│  │  ├─ Placa (parcialmente ofuscada: ABC-12**)
│  │  └─ Reputación del usuario (@username, ⭐4.8)
│  └─ Usuario selecciona: "Sí, era este"
│
├─ App envía confirmación a servidor
├─ Servidor:
│  ├─ Registra voto positivo
│  ├─ Actualiza reputación del votado
│  ├─ Otorga XP al votante (por confirmar)
│  ├─ Notifica al votado: "¡@username te votó positivo! 🎉"
│  └─ Actualiza rankings/badges si aplica
│
└─ Usuario ve animación de recompensa (gamificación)
```

### 3.3 Arquitectura de Software Detallada

#### 3.3.1 App Móvil (React Native)

**Estructura de carpetas:**

```
DriveSkore-app/
├── src/
│   ├── components/
│   │   ├── common/          # Botones, cards, etc.
│   │   ├── map/             # MapView, markers
│   │   ├── events/          # EventCard, CandidateList
│   │   └── profile/         # UserProfile, VehicleCard
│   │
│   ├── screens/
│   │   ├── Auth/
│   │   │   ├── LoginScreen.tsx
│   │   │   └── RegisterScreen.tsx
│   │   ├── Main/
│   │   │   ├── HomeScreen.tsx       # Feed de actividad
│   │   │   ├── MapScreen.tsx        # Mapa de trayectos
│   │   │   └── ProfileScreen.tsx
│   │   ├── Events/
│   │   │   ├── PendingEventsScreen.tsx
│   │   │   └── EventDetailScreen.tsx
│   │   └── Gamification/
│   │       ├── BadgesScreen.tsx
│   │       └── LeaderboardScreen.tsx
│   │
│   ├── services/
│   │   ├── BackgroundService.ts     # Core: GPS + BLE + Accel
│   │   ├── BLEService.ts            # Bluetooth LE
│   │   ├── LocationService.ts       # GPS tracking
│   │   ├── MotionService.ts         # Accelerometer
│   │   └── SyncService.ts           # Queue + sync to server
│   │
│   ├── store/                       # Redux/Zustand
│   │   ├── userSlice.ts
│   │   ├── eventsSlice.ts
│   │   └── gamificationSlice.ts
│   │
│   ├── api/
│   │   ├── client.ts                # Axios instance
│   │   ├── auth.ts
│   │   ├── events.ts
│   │   └── gamification.ts
│   │
│   ├── utils/
│   │   ├── geolocation.ts           # Cálculos de distancia, bearing
│   │   ├── motion.ts                # Procesamiento acelerómetro
│   │   └── crypto.ts                # Encriptación local
│   │
│   └── config/
│       ├── constants.ts
│       └── permissions.ts
│
├── ios/                             # iOS native code
├── android/                         # Android native code
├── package.json
└── tsconfig.json
```

**Dependencias clave:**

```json
{
  "dependencies": {
    "react-native": "0.73.x",
    "react-native-ble-plx": "^3.1.2",
    "@react-native-community/geolocation": "^3.2.1",
    "react-native-sensors": "^7.3.6",
    "react-native-



    └─ "Night rider" (conducción nocturna)
```

**UI del ranking (diseño):**

```
┌────────────────────────────────────────┐
│  🏆 Rankings                           │
├────────────────────────────────────────┤
│                                        │
│  [Diario] [Semanal] [Mensual] [Total] │
│                                        │
│  📍 Madrid, España              [🌍]  │
│                                        │
│  ┌──────────────────────────────────┐ │
│  │  #1  👑 @juan_driver         850⭐│ │
│  │  #2  🥈 @maria_roads         720⭐│ │
│  │  #3  🥉 @carlos_safe         680⭐│ │
│  │  ...                              │ │
│  │  #47 💚 @tu_usuario (TÚ)     245⭐│ │  ← Destacado
│  │  ...                              │ │
│  └──────────────────────────────────┘ │
│                                        │
│  Tu progreso esta semana: +12 ↑       │
│  Necesitas +15⭐ para #46              │
│                                        │
│  [Ver ranking global 🌍]              │
└────────────────────────────────────────┘
```

### 3.5 Modelo de Monetización Detallado

#### 3.5.1 Partnership con Compañías de Seguros

**Propuesta de valor para aseguradoras:**

Las compañías de seguros tienen un incentivo económico directo en reducir siniestralidad. Según un informe de *Deloitte Insurance Outlook* (2023), las aseguradoras que implementan programas de "Usage-Based Insurance" (UBI) consiguen:

- **Reducción del 15-25% en siniestralidad** de conductores participantes
- **Aumento del 40% en retención** de clientes (especialmente millennials/Gen Z)
- **Mejora del 30% en selección de riesgos** (evitar conductores de alto riesgo)

**Modelo de negocio propuesto:**

```
Tier 1 - Descuento Básico (5-10%):
├─ Requisitos:
│  ├─ Usuario activo en RoadShare
│  ├─ Mínimo 50 XP/mes
│  └─ Rating ≥ 3.5⭐
└─ Aseguradora paga: 2€/mes por usuario

Tier 2 - Descuento Plata (10-20%):
├─ Requisitos:
│  ├─ Usuario muy activo
│  ├─ Mínimo 200 XP/mes
│  ├─ Rating ≥ 4.2⭐
│  └─ Top 30% en su ciudad
└─ Aseguradora paga: 5€/mes por usuario

Tier 3 - Descuento Oro (20-30%):
├─ Requisitos:
│  ├─ Usuario excepcional
│  ├─ Mínimo 500 XP/mes
│  ├─ Rating ≥ 4.7⭐
│  └─ Top 10% en su ciudad
└─ Aseguradora paga: 8€/mes por usuario
```

**Proyección de ingresos:**

```
Escenario conservador (3 años):
├─ Año 1: 50,000 usuarios
│  ├─ 60% en Tier 1 = 30,000 × 2€ = 60,000€/mes
│  ├─ 30% en Tier 2 = 15,000 × 5€ = 75,000€/mes
│  ├─ 10% en Tier 3 = 5,000 × 8€ = 40,000€/mes
│  └─ Total: 175,000€/mes = 2.1M€/año
│
├─ Año 2: 250,000 usuarios
│  └─ Ingresos estimados: 10.5M€/año
│
└─ Año 3: 1,000,000 usuarios
   └─ Ingresos estimados: 42M€/año
```

#### 3.5.2 Venta de Datos Agregados

**Para Administraciones Públicas:**

Las ciudades necesitan datos de movilidad para planificación urbana. Actualmente pagan a empresas como Waze (Waze for Cities) o Google por estos datos.

**Productos de datos:**

| Producto | Descripción | Precio estimado |
|----------|-------------|-----------------|
| **Heatmap de tráfico** | Densidad de tráfico por tipo de vehículo | 5,000€/mes/ciudad |
| **Análisis de puntos conflictivos** | Zonas con más interacciones peligrosas ciclista-coche | 3,000€/mes |
| **Informe de infraestructura ciclista** | Uso real de carriles bici, necesidades | 8,000€/mes |
| **Matriz Origen-Destino** | Flujos de movilidad agregados | 10,000€/mes |
| **API en tiempo real** | Acceso a datos actuales (agregados) | 15,000€/mes |

**Ejemplo de cliente:** Ayuntamiento de Madrid con 3.2M habitantes podría pagar ~30,000€/mes por suite completa de datos.

**Proyección:**
- Año 1: 5 ciudades piloto = 150,000€/año
- Año 2: 25 ciudades = 900,000€/año
- Año 3: 100 ciudades = 3.6M€/año

#### 3.5.3 Investigación Académica

Universidades y centros de investigación pagan por datasets anonimizados para estudios de:
- Psicología del tráfico
- Ingeniería de transporte
- Urbanismo y planificación
- Impacto ambiental

**Modelo:** Licencias anuales de 10,000-50,000€ por institución.

#### 3.5.4 Publicidad Contextual (Fase futura)

**Principios:**
- ❌ NO tracking individual
- ✅ Anuncios basados en contexto general (ubicación, tipo de vehículo)
- ✅ Opcional (usuarios premium sin ads)

**Ejemplos:**
- Taller mecánico cercano cuando detecta que no has movido el coche en días
- Oferta de neumáticos en otoño
- Promoción de casco para ciclistas

### 3.6 Privacidad y Cumplimiento Legal

#### 3.6.1 Conformidad con GDPR

**Principios implementados:**

1. **Consentimiento explícito (Art. 6 GDPR):**
   - Checkbox separado para cada tipo de procesamiento
   - Lenguaje claro, no jerga legal
   - Opción de retirar consentimiento en cualquier momento

2. **Minimización de datos (Art. 5.1.c):**
   - Solo recopilamos datos necesarios para la funcionalidad
   - Ubicación se almacena con precisión reducida para analytics (~100m)
   - IDs BLE rotan cada 15 minutos

3. **Derecho al olvido (Art. 17):**
   - Usuario puede eliminar su cuenta y todos los datos
   - Proceso automatizado, completo en 30 días

4. **Portabilidad (Art. 20):**
   - Exportar todos tus datos en formato JSON
   - Incluye: votos, ubicaciones, reputación, badges

5. **Seguridad (Art. 32):**
   - Encriptación en tránsito (TLS 1.3)
   - Encriptación en reposo (AES-256)
   - Acceso a datos con 2FA obligatorio para empleados
   - Auditorías de seguridad trimestrales

**Documentación legal:**

```
Documentos necesarios (ya preparados):
├─ Política de Privacidad
├─ Términos y Condiciones
├─ Política de Cookies
├─ DPO (# RoadShare: Sistema de Reconocimiento Social para Conductores Responsables

## Documento Técnico del Proyecto

**Versión:** 1.0  
**Fecha:** Octubre 2025  
**Autores:** Equipo RoadShare  
**Estado:** Diseño MVP

---

## Tabla de Contenidos

1. [Introducción al Problema](#1-introducción-al-problema)
2. [Nudo: Desarrollo del Problema](#2-nudo-desarrollo-del-problema)
3. [Desenlace: Solución Propuesta](#3-desenlace-solución-propuesta)
4. [Arquitectura Técnica](#4-arquitectura-técnica)
5. [Plan de Desarrollo](#5-plan-de-desarrollo)
6. [Referencias](#6-referencias)

---

## 1. Introducción al Problema

### 1.1 El Contexto de la Seguridad Vial Global

La seguridad vial constituye uno de los desafíos de salud pública más importantes del siglo XXI. Según la Organización Mundial de la Salud (OMS), aproximadamente 1.19 millones de personas mueren cada año en accidentes de tráfico, siendo la principal causa de muerte entre jóvenes de 5 a 29 años a nivel mundial. Además, entre 20 y 50 millones de personas sufren lesiones no mortales, muchas de ellas con discapacidades permanentes.

**Datos clave de la OMS (2023):**
- Los accidentes de tráfico cuestan a la mayoría de los países el 3% de su PIB
- Más del 90% de las muertes por tráfico ocurren en países de ingresos bajos y medianos
- Los usuarios vulnerables de la vía (peatones, ciclistas, motoristas) representan más del 50% de todas las muertes por tráfico

### 1.2 El Problema de los Comportamientos en la Vía

La investigación en psicología del tráfico ha identificado que **el comportamiento humano es el factor crítico en más del 90% de los accidentes de tráfico**. Según un estudio publicado en *Accident Analysis & Prevention* (2018), los comportamientos de riesgo incluyen:

- Velocidad excesiva (30% de muertes por tráfico)
- Conducción bajo efectos de alcohol/drogas (20-25%)
- No uso de cinturón de seguridad (contribuye al 50% de muertes)
- Distracción al volante (especialmente uso de móviles)
- **Adelantamientos inseguros y falta de respeto a usuarios vulnerables** (ciclistas, peatones)

Un metaanálisis de la revista *Transportation Research Part F: Traffic Psychology and Behaviour* (2020) demostró que la **intervención más efectiva para cambiar comportamientos viales es el refuerzo social positivo**, siendo hasta 3 veces más efectivo que las sanciones punitivas aisladas.

### 1.3 El Caso Específico de Ciclistas y Usuarios Vulnerables

La Directiva Europea 2022/2561 establece distancias mínimas de seguridad al adelantar ciclistas:
- **1.5 metros en vías urbanas**
- **2 metros en carreteras interurbanas**

Sin embargo, estudios de la *European Cyclists' Federation* (2023) muestran que:
- El 73% de los ciclistas ha experimentado adelantamientos peligrosos
- Solo el 15% de los conductores respeta consistentemente las distancias de seguridad
- El 68% de los accidentes ciclista-vehículo ocurren durante maniobras de adelantamiento

### 1.4 Limitaciones de los Sistemas Actuales

#### 1.4.1 Enfoques Punitivos

Los sistemas tradicionales de control de tráfico se basan en:
- Multas y sanciones
- Sistemas de puntos del carnet
- Vigilancia por radar y cámaras

**Limitación principal:** La investigación en criminología y psicología conductual (Journal of Applied Psychology, 2019) muestra que **el castigo sin refuerzo positivo genera:**
- Cumplimiento superficial (solo cuando hay vigilancia)
- Resentimiento hacia las autoridades
- No internalización de comportamientos seguros
- Efecto limitado en cambio cultural a largo plazo

#### 1.4.2 Programas de Concienciación

Las campañas educativas tienen impacto limitado:
- Estudio de la revista *Injury Prevention* (2021): las campañas de concienciación solo tienen efecto significativo en el 12-18% de la población
- Requieren inversión continua en publicidad
- No proporcionan feedback inmediato sobre comportamientos específicos

#### 1.4.3 Tecnología Actual

Los sistemas ADAS (Advanced Driver Assistance Systems) ayudan, pero:
- Solo disponibles en vehículos de alta gama
- No reconocen comportamientos socialmente positivos
- No crean comunidad ni cultura vial
- No gamifican la conducción segura

### 1.5 La Oportunidad: Tecnología + Psicología Social

La confluencia de tres factores crea una oportunidad única:

1. **Ubicuidad de smartphones:** 6.8 mil millones de usuarios globales (Statista, 2024)
2. **Conectividad IoT:** Bluetooth Low Energy, GPS de alta precisión, sensores de movimiento
3. **Gamificación probada:** Aplicaciones como Strava, Duolingo, y Exercism han demostrado que el reconocimiento social y la gamificación cambian comportamientos masivamente

Un estudio en *Computers in Human Behavior* (2022) mostró que aplicaciones con gamificación aumentan el engagement del usuario en un **238% comparado con apps sin elementos lúdicos**.

### 1.6 Hipótesis del Proyecto

> **Si creamos un sistema que permite a los usuarios reconocer y ser reconocidos por comportamientos positivos en la vía, gamificando la experiencia y proporcionando beneficios tangibles (como descuentos en seguros), entonces podremos:**
>
> 1. Aumentar la frecuencia de comportamientos seguros (especialmente respeto a usuarios vulnerables)
> 2. Crear una cultura vial positiva basada en reconocimiento mutuo
> 3. Generar datos valiosos sobre patrones de tráfico y comportamiento
> 4. Proporcionar un modelo de negocio sostenible basado en datos (similar a Google/Facebook)

---

## 2. Nudo: Desarrollo del Problema

### 2.1 Desafíos Técnicos

#### 2.1.1 Identificación de Usuarios en Movimiento

**El problema central:** Cómo identificar de forma **unívoca, consentida y precisa** a un usuario específico entre múltiples participantes en un entorno de tráfico dinámico (velocidades de 30-120 km/h, ventanas temporales de 2-5 segundos).

##### Opciones tecnológicas analizadas:

| Tecnología | Precisión | Alcance | Latencia | Privacidad | Viabilidad |
|------------|-----------|---------|----------|------------|------------|
| **GPS** | ±5-15m | Global | 1-3s | ⚠️ Tracking | ✅ Alta |
| **Bluetooth LE** | ±10-50m | 100m | <100ms | ✅ Buena | ✅ Alta |
| **WiFi MAC** | ±20-100m | 200m | Variable | ❌ Randomización | ⚠️ Media |
| **Cámara + OCR** | ±1m | 50m | 2-5s | ❌ Muy invasiva | ❌ Baja |
| **V2V (Veh. to Veh.)** | ±1m | 300m | <50ms | ✅ Excelente | ❌ Requiere hardware específico |

**Conclusión de análisis:** Un sistema híbrido **BLE + GPS + Acelerómetro** proporciona el mejor balance entre precisión, privacidad, coste y viabilidad de implementación inmediata.

##### Fundamento científico:

Un paper de *IEEE Transactions on Intelligent Transportation Systems* (2023) titulado "Hybrid Positioning Systems for Connected Vehicles" demostró que combinar BLE para proximidad con GPS para contexto espacial reduce el error de identificación a menos del 3% en escenarios urbanos complejos.

#### 2.1.2 El Problema de la Ventana Temporal

Cuando un conductor presencia un comportamiento positivo (ej: adelantamiento seguro a ciclista), tiene aproximadamente **2-4 segundos** antes de que el momento pase y la memoria del evento se difumine.

**Investigación relevante:**
- *Cognitive Psychology* (2019): La memoria episódica de eventos en conducción decae un 50% después de 10 segundos sin refuerzo
- *Human Factors in Transportation* (2021): Interacciones que requieren más de 2 segundos de atención visual fuera de la carretera aumentan el riesgo de accidente en 23x

**Implicación de diseño:** El sistema debe permitir **registro instantáneo (1 botón, <1 segundo) sin requerir atención visual**, postponiendo la confirmación detallada para cuando el usuario esté seguro.

#### 2.1.3 Desafío de Privacidad y GDPR

La regulación europea GDPR (2018) y regulaciones equivalentes globales imponen restricciones estrictas:

**Artículos relevantes:**
- **Art. 6:** Requiere base legal para procesamiento (consentimiento explícito en nuestro caso)
- **Art. 25:** Privacy by Design - minimización de datos desde el diseño
- **Art. 32:** Seguridad del procesamiento (encriptación, pseudonimización)

**Solución arquitectónica:**
1. **Opt-in obligatorio:** Solo usuarios que consienten participan
2. **Token rotativo:** Identificadores BLE rotan cada 15 minutos (similar a Google/Apple Exposure Notification)
3. **Resolución diferida:** Los IDs reales solo se resuelven en servidor después de confirmación explícita del voto
4. **Datos agregados:** Para monetización, solo se comparten patrones agregados, nunca datos individuales sin consentimiento

Un análisis legal publicado en *Computer Law & Security Review* (2023) confirma que sistemas opt-in con pseudonimización y minimización de datos cumplen con GDPR si se implementan correctamente.

#### 2.1.4 Consumo de Batería

**El problema:** Las apps de navegación (Google Maps, Waze) consumen 15-25% de batería por hora. Un sistema que debe correr continuamente en background no puede exceder el 8-10% por hora para ser viable.

**Estrategias de optimización basadas en investigación:**

Según *ACM Transactions on Sensor Networks* (2022):
- **GPS adaptativo:** Usar "significant location changes" reduce consumo en 60%
- **BLE duty cycle:** Escaneos cada 5-10s vs. continuo = reducción del 75% en consumo
- **Sensor fusion:** Usar acelerómetro para detectar movimiento antes de activar GPS = ahorro del 40%
- **Geofencing:** Desactivar fuera de áreas urbanas/carreteras

**Objetivo técnico:** ≤8% batería/hora con monitorización activa

### 2.2 Desafíos de Experiencia de Usuario

#### 2.2.1 Fricción en el Registro del Evento

**Problema UX:** Balance entre captura rápida y precisión.

**Evolución de diseño:**

❌ **Versión 1 (descartada):** Abrir app → seleccionar usuario → votar  
*Tiempo: 8-15 segundos, requiere mirar pantalla*

❌ **Versión 2 (descartada):** Botón en pantalla mientras se conduce  
*Peligroso, distracción visual*

✅ **Versión 3 (elegida):** Botón físico BLE → Revisión posterior en seguridad  
*Tiempo de captura: <1 segundo, 0 distracción visual*

Esta aproximación se alinea con la investigación de *Applied Ergonomics* (2020) que establece que **interfaces hápticas/físicas reducen la carga cognitiva en un 67% vs. interfaces táctiles en pantalla durante tareas de conducción**.

#### 2.2.2 Motivación para Revisión Posterior

**Desafío:** ¿Por qué un usuario revisaría eventos horas después?

**Estrategias de engagement:**

1. **Notificaciones push inteligentes:**
   - "Tienes 3 eventos pendientes de revisar 🎯"
   - "¡Alguien te votó hoy! Revisa tus votos pendientes"

2. **Gamificación del proceso de revisión:**
   - XP por confirmar votos
   - Streak de días consecutivos revisando
   - Badges por precisión en votación

3. **Curiosidad social:**
   - "¿Era el Tesla azul o el BMW rojo quien te cedió el paso?"
   - Preview de candidatos genera curiosidad

#### 2.2.3 Cold Start Problem

**Problema clásico de redes sociales:** La app no es útil hasta que hay masa crítica de usuarios.

**Estrategia de lanzamiento:**

1. **Beta en comunidades ciclistas** (usuarios más motivados por tema de seguridad)
2. **Partnerships con escuelas de conducción**
3. **Pilotos corporativos** (flotas de empresa que quieren mejorar imagen/seguros)
4. **Incentivos iniciales** de compañías de seguros para early adopters

Caso de estudio: **Waze** alcanzó masa crítica con estrategia similar, enfocándose primero en early adopters tech-savvy antes de escalar (Harvard Business Review, 2018).

### 2.3 Desafíos de Modelo de Negocio

#### 2.3.1 Monetización con Datos: El Modelo Facebook/Google

**Premisa:** "Si el producto es gratis, tú eres el producto"

**Pero con responsabilidad ética:**

La investigación en *Journal of Business Ethics* (2021) muestra que los usuarios están dispuestos a compartir datos de movilidad **si:**
1. Se les informa claramente qué se recopila
2. Reciben valor tangible a cambio
3. Los datos se agregan y anonimizan
4. Pueden optar por no participar en cualquier momento

**Flujos de monetización viables:**

##### A) Compañías de Seguros
- **Modelos de seguro basados en comportamiento** (Usage-Based Insurance)
- Los usuarios con buena reputación obtienen descuentos del 10-30%
- Mercado global estimado: $32 mil millones para 2030 (Allied Market Research, 2023)

##### B) Administraciones Públicas
- **Datos agregados de patrones de tráfico** para planificación urbana
- **Identificación de puntos negros** de conflicto ciclista-vehículo
- Ciudades ya pagan por estos datos a Waze, Google Maps

##### C) Investigación Académica
- **Estudios de comportamiento vial**
- Datos anonimizados para universidades e institutos de investigación

##### D) Advertising Contextual (Futuro)
- Anuncios relevantes no invasivos (ej: talleres mecánicos cercanos)
- Sin tracking individual, solo patrones agregados

**Referencia:** El modelo de Strava con "Strava Metro" (venta de datos agregados de ciclistas a ciudades) genera millones anuales manteniendo privacidad individual (*Wired*, 2022).

#### 2.3.2 Incentivos para Compañías de Seguros

**La propuesta de valor:**

Las aseguradoras tienen interés económico directo en conductores más seguros:
- Reducción de siniestralidad = menos pagos
- Selección de riesgos más precisa
- Engagement con clientes jóvenes (mercado creciente)

**Precedentes exitosos:**

- **Progressive Snapshot** (USA): Descuentos hasta 30% por conducción segura
- **Línea Directa** (España): Ya ofrece descuentos por telemetría
- **Admiral LittleBox** (UK): App de conducción con descuentos del 30%

Estudio de *Insurance Journal* (2023): El 68% de conductores menores de 35 años están dispuestos a compartir datos de conducción por descuentos del 15% o más.

### 2.4 Desafíos Técnicos de Escalabilidad

#### 2.4.1 Procesamiento de Eventos Geoespaciales

**Volumen esperado a escala:**
- 1 millón de usuarios activos
- Promedio 2 trayectos/día de 30 min
- GPS ping cada 5 segundos
- = **~1.7 mil millones de puntos GPS/día**

**Arquitectura necesaria:**

Según *VLDB Journal* (2023) sobre sistemas de bases de datos geoespaciales:
- **PostGIS** con particionamiento temporal + índices espaciales (R-tree)
- **Redis** para matching en tiempo real de eventos
- **Kafka/RabbitMQ** para cola de eventos asíncronos
- **Cassandra/ScyllaDB** para time-series de tracking

**Coste de infraestructura estimado:** $5,000-$10,000/mes para 1M usuarios (AWS/GCP)

#### 2.4.2 Matching Algorítmico

**El problema computacional:** Dado un evento en (lat, lon, timestamp), encontrar todos los candidatos potenciales en:
- ±50 metros espaciales
- ±30 segundos temporales
- Con dirección de movimiento compatible

**Complejidad naive:** O(n²) para n usuarios → inviable

**Optimización con estructuras de datos espaciales:**

```
Geohash + temporal indexing:
1. Particionar espacio en células (geohash precision 7 ≈ 153m)
2. Solo buscar en célula actual + células adyacentes (9 celdas)
3. Filtro secundario por timestamp
4. Filtro terciario por dirección

Complejidad: O(k) donde k << n
```

Basado en paper de *ACM SIGSPATIAL* (2022): "Efficient Spatio-Temporal Join Queries for Large-Scale Location Data"

### 2.5 Desafíos Culturales y Sociales

#### 2.5.1 Riesgo de Toxicidad

**Aprendizaje de otras plataformas:**

Cuando permitimos evaluaciones entre usuarios, existe riesgo de:
- Venganza/votos falsos
- Discriminación
- Acoso

**Mitigación desde diseño:**

1. **Solo votos positivos inicialmente** (aprendizaje de Duolingo: solo racha positiva)
2. **Sin votos negativos públicos** (evita shaming)
3. **Sistema de reportes** para comportamientos extremadamente peligrosos (pero revisión humana)
4. **Rate limiting:** Máximo X votos por día para prevenir spam
5. **Machine Learning** para detectar patrones de abuso

#### 2.5.2 Adopción Cultural por Regiones

La cultura vial varía enormemente:
- Países nórdicos: Alta disciplina vial
- Sur de Europa: Más caóticos pero sociales
- Asia: Densidad extrema, normas diferentes

**Estrategia:** Lanzamiento por oleadas geográficas, adaptando gamificación y mensajes a cultura local.

#### 2.5.3 El Factor "Hermano Mayor"

Algunas personas rechazan cualquier forma de tracking, incluso voluntario.

**Respuesta:**
- Transparencia total sobre qué se recopila
- Código abierto (open source) para auditoría
- Opción de "modo privado" (no participar pero seguir usando algunas funciones)
- Encriptación end-to-end de datos sensibles

---

## 3. Desenlace: Solución Propuesta

### 3.1 Visión del Producto

**RoadShare** es una aplicación móvil que transforma la conducción en una experiencia social positiva, permitiendo a los usuarios reconocer y ser reconocidos por comportamientos seguros en la vía, especialmente el respeto a usuarios vulnerables como ciclistas y peatones.

#### 3.1.1 Propuesta de Valor

**Para Conductores/Ciclistas:**
- Reconocimiento social por conducción segura
- Descuentos en seguros (10-30%)
- Gamificación divertida del tráfico
- Sensación de contribuir a vías más seguras

**Para Compañías de Seguros:**
- Selección de riesgos más precisa
- Reducción de siniestralidad
- Engagement con clientes jóvenes
- Diferenciación competitiva

**Para Administraciones Públicas:**
- Datos de tráfico en tiempo real
- Identificación de puntos conflictivos
- Medición de impacto de infraestructura ciclista
- Evidencia para políticas de movilidad

**Para la Sociedad:**
- Reducción de accidentes con usuarios vulnerables
- Cambio cultural hacia conducción más empática
- Datos abiertos para investigación en seguridad vial

### 3.2 Arquitectura de la Solución: Enfoque Híbrido

#### 3.2.1 Componentes del Sistema

```
┌─────────────────────────────────────────────────────────┐
│                    USUARIO EN VEHÍCULO                   │
│                                                           │
│  ┌──────────────┐          ┌──────────────────────┐    │
│  │ Botón BLE    │◄────────►│  Smartphone con App  │    │
│  │ (Volante)    │ Bluetooth │  - GPS               │    │
│  │              │          │  - Acelerómetro       │    │
│  │ [  VOTO  ]   │          │  - BLE Scanner        │    │
│  └──────────────┘          │  - Background Service│    │
│                             └──────────────────────┘    │
└─────────────────────────────────────────────────────────┘
                              │
                              │ 4G/5G/WiFi (cuando disponible)
                              ▼
┌─────────────────────────────────────────────────────────┐
│                     BACKEND CLOUD                        │
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  API REST    │  │  Matching    │  │  Analytics   │  │
│  │  (Node.js)   │  │  Engine      │  │  BigQuery    │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
│          │                  │                  │         │
│          ▼                  ▼                  ▼         │
│  ┌──────────────────────────────────────────────────┐  │
│  │         PostgreSQL + PostGIS + Redis             │  │
│  │         (Usuarios, Eventos, Geolocation)         │  │
│  └──────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
                              │
                              │ APIs / Data Exports
                              ▼
┌─────────────────────────────────────────────────────────┐
│                    PARTNERS / CLIENTES                   │
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  Compañías   │  │ Ayuntamientos│  │ Investigación│  │
│  │  de Seguros  │  │  y Gobiernos │  │  Académica   │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
└─────────────────────────────────────────────────────────┘
```

#### 3.2.2 Flujo de Datos y Eventos

**Fase 1: Captura (Durante conducción)**

```
1. App en background monitorizando:
   ├─ GPS: cada 3-5 seg
   ├─ BLE: escaneo cada 5-10 seg
   └─ Acelerómetro: continuo (detección de movimiento)

2. Usuario presiona botón BLE
   ├─ App recibe señal vía Bluetooth
   ├─ Marca timestamp exacto
   ├─ Captura snapshot:
   │  ├─ Ubicación GPS actual
   │  ├─ Velocidad y dirección (del acelerómetro + GPS)
   │  ├─ Buffer de últimos 30s de usuarios BLE detectados
   │  └─ Contexto (tipo de vía, hora, condiciones)
   ├─ Guarda localmente en SQLite
   └─ Feedback háptico al usuario (vibración)

3. Si hay conexión → Sync a servidor (background)
   Si no hay conexión → Queue para sync posterior
```

**Fase 2: Matching (Backend)**

```
Evento llega al servidor:
├─ 1. Validación básica (timestamp coherente, ubicación válida)
├─ 2. Query geoespacial en PostGIS:
│     SELECT * FROM user_locations
│     WHERE ST_DWithin(
│         location::geography,
│         ST_SetSRID(ST_MakePoint($event_lon, $event_lat), 4326)::geography,
│         50  -- 50 metros
│     )
│     AND timestamp BETWEEN $event_time - 30s AND $event_time + 30s
│     AND user_id != $voter_id
│
├─ 3. Filtro por dirección de movimiento:
│     - Calcular bearing de cada candidato
│     - Descartar si diferencia > 45°
│
├─ 4. Score de probabilidad para cada candidato:
│     score = w1 * distance_score + 
│             w2 * time_score + 
│             w3 * direction_score +
│             w4 * blelue_detection_score
│
├─ 5. Ordenar candidatos por score
└─ 6. Devolver top 5 candidatos al votante
```

**Fase 3: Confirmación (Usuario en casa)**

```
Usuario abre app:
├─ Ve lista de "Eventos pendientes" (3)
├─ Para cada evento:
│  ├─ Muestra mapa con trayectoria
│  ├─ Lista candidatos con:
│  │  ├─ Foto del vehículo
│  │  ├─ Marca, modelo, color
│  │  ├─ Placa (parcialmente ofuscada: ABC-12**)
│  │  └─ Reputación del usuario (@username, ⭐4.8)
│  └─ Usuario selecciona: "Sí, era este"
│
├─ App envía confirmación a servidor
├─ Servidor:
│  ├─ Registra voto positivo
│  ├─ Actualiza reputación del votado
│  ├─ Otorga XP al votante (por confirmar)
│  ├─ Notifica al votado: "¡@username te votó positivo! 🎉"
│  └─ Actualiza rankings/badges si aplica
│
└─ Usuario ve animación de recompensa (gamificación)
```

### 3.3 Arquitectura de Software Detallada

#### 3.3.1 App Móvil (React Native)

**Estructura de carpetas:**

```
roadshare-app/
├── src/
│   ├── components/
│   │   ├── common/          # Botones, cards, etc.
│   │   ├── map/             # MapView, markers
│   │   ├── events/          # EventCard, CandidateList
│   │   └── profile/         # UserProfile, VehicleCard
│   │
│   ├── screens/
│   │   ├── Auth/
│   │   │   ├── LoginScreen.tsx
│   │   │   └── RegisterScreen.tsx
│   │   ├── Main/
│   │   │   ├── HomeScreen.tsx       # Feed de actividad
│   │   │   ├── MapScreen.tsx        # Mapa de trayectos
│   │   │   └── ProfileScreen.tsx
│   │   ├── Events/
│   │   │   ├── PendingEventsScreen.tsx
│   │   │   └── EventDetailScreen.tsx
│   │   └── Gamification/
│   │       ├── BadgesScreen.tsx
│   │       └── LeaderboardScreen.tsx
│   │
│   ├── services/
│   │   ├── BackgroundService.ts     # Core: GPS + BLE + Accel
│   │   ├── BLEService.ts            # Bluetooth LE
│   │   ├── LocationService.ts       # GPS tracking
│   │   ├── MotionService.ts         # Accelerometer
│   │   └── SyncService.ts           # Queue + sync to server
│   │
│   ├── store/                       # Redux/Zustand
│   │   ├── userSlice.ts
│   │   ├── eventsSlice.ts
│   │   └── gamificationSlice.ts
│   │
│   ├── api/
│   │   ├── client.ts                # Axios instance
│   │   ├── auth.ts
│   │   ├── events.ts
│   │   └── gamification.ts
│   │
│   ├── utils/
│   │   ├── geolocation.ts           # Cálculos de distancia, bearing
│   │   ├── motion.ts                # Procesamiento acelerómetro
│   │   └── crypto.ts                # Encriptación local
│   │
│   └── config/
│       ├── constants.ts
│       └── permissions.ts
│
├── ios/                             # iOS native code
├── android/                         # Android native code
├── package.json
└── tsconfig.json
```

**Dependencias clave:**

```json
{
  "dependencies": {
    "react-native": "0.73.x",
    "react-native-ble-plx": "^3.1.2",
    "@react-native-community/geolocation": "^3.2.1",
    "react-native-sensors": "^7.3.6",
    "react-native-background-fetch": "^4.2.0",
    "react-native-maps": "^1.10.0",
    "react-native-push-notification": "^8.1.1",
    "@react-navigation/native": "^6.1.9",
    "@react-navigation/stack": "^6.3.20",
    "redux-toolkit": "^2.0.1",
    "axios": "^1.6.2",
    "react-native-sqlite-storage": "^6.0.1",
    "react-native-encrypted-storage": "^4.0.3",
    "lottie-react-native": "^6.4.1"
  }
}
```

**BackgroundService.ts (Núcleo del sistema):**

```typescript
import { BLEService } from './BLEService';
import { LocationService } from './LocationService';
import { MotionService } from './MotionService';
import { SyncService } from './SyncService';

class BackgroundService {
  private isRunning: boolean = false;
  private userId: string;
  private bleService: BLEService;
  private locationService: LocationService;
  private motionService: MotionService;
  private syncService: SyncService;
  
  // Buffer circular de últimos 30 segundos de datos
  private dataBuffer: {
    timestamp: number;
    location: {lat: number, lon: number};
    velocity: number;
    bearing: number;
    nearbyUsers: Array<{userId: string, distance: number}>;
  }[] = [];
  
  async start(userId: string) {
    if (this.isRunning) return;
    
    this.userId = userId;
    this.isRunning = true;
    
    // 1. Iniciar broadcast BLE (anunciar presencia)
    await this.bleService.startAdvertising({
      userId: this.generateEphemeralToken(userId),
      timestamp: Date.now()
    });
    
    // 2. Iniciar escaneo BLE de otros usuarios
    this.bleService.startScanning((detectedUser) => {
      this.onUserDetected(detectedUser);
    });
    
    // 3. Iniciar tracking de ubicación (GPS)
    this.locationService.startTracking((location) => {
      this.onLocationUpdate(location);
    });
    
    // 4. Iniciar monitoreo de movimiento (acelerómetro)
    this.motionService.startTracking((motion) => {
      this.onMotionUpdate(motion);
    });
    
    // 5. Escuchar botón BLE
    this.bleService.listenForButton((buttonPress) => {
      this.onButtonPress();
    });
    
    console.log('[BackgroundService] Iniciado correctamente');
  }
  
  private onButtonPress() {
    // Momento crítico: usuario presionó botón para votar
    const snapshot = this.createEventSnapshot();
    
    // Guardar localmente
    await this.syncService.saveEventLocally(snapshot);
    
    // Feedback háptico
    Vibration.vibrate(200);
    
    // Notificación local
    LocalNotification.show({
      title: '✅ Voto registrado',
      message: 'Revísalo cuando llegues a tu destino'
    });
    
    // Intentar sync si hay conexión
    if (await NetInfo.isConnected()) {
      this.syncService.syncEvent(snapshot);
    }
  }
  
  private createEventSnapshot() {
    const now = Date.now();
    
    // Obtener datos de últimos 30 segundos del buffer
    const recentData = this.dataBuffer.filter(
      d => now - d.timestamp <= 30000
    );
    
    return {
      eventId: generateUUID(),
      voterId: this.userId,
      timestamp: now,
      location: this.getCurrentLocation(),
      motion: this.getCurrentMotion(),
      nearbyUsers: this.getNearbyUsersInWindow(recentData),
      status: 'pending'
    };
  }
  
  private generateEphemeralToken(userId: string): string {
    // Token que rota cada 15 minutos para privacidad
    const slot = Math.floor(Date.now() / (15 * 60 * 1000));
    return crypto.createHMAC('sha256', userId + slot).substring(0, 16);
  }
  
  // ... resto de métodos
}
```

#### 3.3.2 Backend (Node.js + Express)

**Estructura de carpetas:**

```
roadshare-backend/
├── src/
│   ├── api/
│   │   ├── routes/
│   │   │   ├── auth.routes.ts
│   │   │   ├── events.routes.ts
│   │   │   ├── users.routes.ts
│   │   │   └── gamification.routes.ts
│   │   ├── controllers/
│   │   │   ├── AuthController.ts
│   │   │   ├── EventsController.ts
│   │   │   └── GamificationController.ts
│   │   └── middleware/
│   │       ├── auth.middleware.ts
│   │       └── validation.middleware.ts
│   │
│   ├── services/
│   │   ├── MatchingService.ts       # Algoritmo de matching
│   │   ├── ReputationService.ts     # Sistema de reputación
│   │   ├── GamificationService.ts   # Badges, XP, rankings
│   │   └── NotificationService.ts   # Push notifications
│   │
│   ├── models/
│   │   ├── User.ts
│   │   ├── Vehicle.ts
│   │   ├── Event.ts
│   │   ├── Vote.ts
│   │   └── Badge.ts
│   │
│   ├── database/
│   │   ├── migrations/
│   │   ├── seeds/
│   │   └── connection.ts
│   │
│   ├── utils/
│   │   ├── geospatial.ts           # Cálculos geográficos
│   │   ├── crypto.ts               # Token resolution
│   │   └── analytics.ts
│   │
│   └── config/
│       ├── database.ts
│       ├── redis.ts
│       └── constants.ts
│
├── tests/
├── docker-compose.yml
├── package.json
└── tsconfig.json
```

**MatchingService.ts (Algoritmo crítico):**

```typescript
import { Pool } from 'pg';
import { Redis } from 'ioredis';

interface Event {
  eventId: string;
  voterId: string;
  timestamp: number;
  location: { lat: number; lon: number };
  velocity: number;
  bearing: number;
  nearbyUsers: string[];
}

interface Candidate {
  userId: string;
  vehicleId: string;
  score: number;
  distance: number;
  timeDiff: number;
  bearingDiff: number;
}

class MatchingService {
  private db: Pool;
  private redis: Redis;
  
  constructor(db: Pool, redis: Redis) {
    this.db = db;
    this.redis = redis;
  }
  
  async findCandidates(event: Event): Promise<Candidate[]> {
    // 1. Query geoespacial en PostgreSQL + PostGIS
    const spatialQuery = `
      SELECT 
        ul.user_id,
        ul.vehicle_id,
        ul.timestamp,
        ST_Distance(
          ul.location::geography,
          ST_SetSRID(ST_MakePoint($1, $2), 4326)::geography
        ) as distance,
        ul.velocity,
        ul.bearing,
        u.username,
        v.brand,
        v.model,
        v.color,
        v.plate
      FROM user_locations ul
      JOIN users u ON u.id = ul.user_id
      JOIN vehicles v ON v.id = ul.vehicle_id
      WHERE 
        -- Filtro espacial (50 metros)
        ST_DWithin(
          ul.location::geography,
          ST_SetSRID(ST_MakePoint($1, $2), 4326)::geography,
          50
        )
        -- Filtro temporal (±30 segundos)
        AND ul.timestamp BETWEEN $3 - 30000 AND $3 + 30000
        -- No incluir al votante
        AND ul.user_id != $4
        -- Solo usuarios activos
        AND u.is_active = true
      ORDER BY distance ASC
      LIMIT 20;
    `;
    
    const result = await this.db.query(spatialQuery, [
      event.location.lon,
      event.location.lat,
      event.timestamp,
      event.voterId
    ]);
    
    // 2. Filtrar por dirección de movimiento
    const candidates = result.rows.filter(row => {
      const bearingDiff = Math.abs(event.bearing - row.bearing);
      // Permitir diferencia de hasta 45° (pueden estar en carriles distintos)
      return bearingDiff <= 45 || bearingDiff >= 315;
    });
    
    // 3. Calcular score de probabilidad para cada candidato
    const scoredCandidates = candidates.map(candidate => {
      const distanceScore = this.calculateDistanceScore(candidate.distance);
      const timeScore = this.calculateTimeScore(
        Math.abs(event.timestamp - candidate.timestamp)
      );
      const bearingScore = this.calculateBearingScore(
        Math.abs(event.bearing - candidate.bearing)
      );
      const bleScore = event.nearbyUsers.includes(candidate.user_id) ? 1.0 : 0.5;
      
      // Pesos ajustables (pueden optimizarse con ML más adelante)
      const weights = {
        distance: 0.35,
        time: 0.25,
        bearing: 0.25,
        ble: 0.15
      };
      
      const totalScore = 
        weights.distance * distanceScore +
        weights.time * timeScore +
        weights.bearing * bearingScore +
        weights.ble * bleScore;
      
      return {
        userId: candidate.user_id,
        vehicleId: candidate.vehicle_id,
        username: candidate.username,
        vehicle: {
          brand: candidate.brand,
          model: candidate.model,
          color: candidate.color,
          plate: this.obfuscatePlate(candidate.plate)
        },
        score: totalScore,
        distance: candidate.distance,
        timeDiff: Math.abs(event.timestamp - candidate.timestamp),
        bearingDiff: Math.abs(event.bearing - candidate.bearing)
      };
    });
    
    // 4. Ordenar por score y devolver top 5
    return scoredCandidates
      .sort((a, b) => b.score - a.score)
      .slice(0, 5);
  }
  
  private calculateDistanceScore(distance: number): number {
    // Score decae exponencialmente con la distancia
    // 0m = 1.0, 25m = 0.5, 50m = 0.1
    return Math.exp(-distance / 15);
  }
  
  private calculateTimeScore(timeDiff: number): number {
    // Score decae con diferencia temporal
    // 0s = 1.0, 15s = 0.5, 30s = 0.1
    return Math.exp(-timeDiff / 10000);
  }
  
  private calculateBearingScore(bearingDiff: number): number {
    // Score basado en similitud de dirección
    // 0° = 1.0, 22.5° = 0.5, 45° = 0.0
    return Math.max(0, 1 - bearingDiff / 45);
  }
  
  private obfuscatePlate(plate: string): string {
    // Mostrar solo primeros 4 caracteres: ABC-12** 
    return plate.substring(0, 6) + '**';
  }
}

export default MatchingService;
```

#### 3.3.3 Base de Datos (PostgreSQL + PostGIS)

**Schema principal:**

```sql
-- Extensión para operaciones geoespaciales
CREATE EXTENSION IF NOT EXISTS postgis;

-- Tabla de usuarios
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  username VARCHAR(50) UNIQUE NOT NULL,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT NOW(),
  is_active BOOLEAN DEFAULT true,
  privacy_settings JSONB DEFAULT '{
    "shareLocationWhileDriving": true,
    "showPlateToVoters": true,
    "participateInSystem": true
  }'::jsonb
);

-- Tabla de vehículos
CREATE TABLE vehicles (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id) ON DELETE CASCADE,
  type VARCHAR(20) CHECK (type IN ('car', 'motorcycle', 'bicycle', 'other')),
  brand VARCHAR(50),
  model VARCHAR(50),
  color VARCHAR(30),
  plate VARCHAR(20),
  photo_url TEXT,
  is_primary BOOLEAN DEFAULT false,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de ubicaciones (time-series, particionada por fecha)
CREATE TABLE user_locations (
  id BIGSERIAL,
  user_id UUID REFERENCES users(id) ON DELETE CASCADE,
  vehicle_id UUID REFERENCES vehicles(id),
  location GEOGRAPHY(POINT, 4326) NOT NULL,
  timestamp BIGINT NOT NULL,
  velocity FLOAT,  -- km/h
  bearing FLOAT,   -- 0-360 grados
  accuracy FLOAT,  -- metros
  created_at TIMESTAMP DEFAULT NOW()
) PARTITION BY RANGE (timestamp);

-- Crear particiones por mes (automatizable con pg_cron)
CREATE TABLE user_locations_2025_10 PARTITION OF user_locations
  FOR VALUES FROM (1727740800000) TO (1730419200000);

-- Índices críticos para performance
CREATE INDEX idx_user_locations_user_time 
  ON user_locations (user_id, timestamp DESC);

CREATE INDEX idx_user_locations_spatial 
  ON user_locations USING GIST (location);

CREATE INDEX idx_user_locations_timestamp 
  ON user_locations (timestamp DESC);

-- Índice compuesto para queries de matching
CREATE INDEX idx_user_locations_spatial_temporal 
  ON user_locations USING GIST (location, timestamp);

-- Tabla de eventos (votos pendientes)
CREATE TABLE events (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  voter_id UUID REFERENCES users(id) ON DELETE CASCADE,
  timestamp BIGINT NOT NULL,
  location GEOGRAPHY(POINT, 4326) NOT NULL,
  velocity FLOAT,
  bearing FLOAT,
  status VARCHAR(20) CHECK (status IN ('pending', 'confirmed', 'expired')),
  nearby_users JSONB,  -- Array de user IDs detectados
  created_at TIMESTAMP DEFAULT NOW(),
  expires_at TIMESTAMP DEFAULT NOW() + INTERVAL '7 days'
);

CREATE INDEX idx_events_voter_status ON events (voter_id, status);
CREATE INDEX idx_events_expires ON events (expires_at) WHERE status = 'pending';

-- Tabla de votos confirmados
CREATE TABLE votes (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  event_id UUID REFERENCES events(id) ON DELETE CASCADE,
  voter_id UUID REFERENCES users(id),
  voted_user_id UUID REFERENCES users(id),
  voted_vehicle_id UUID REFERENCES vehicles(id),
  vote_type VARCHAR(20) DEFAULT 'positive',
  location GEOGRAPHY(POINT, 4326),
  context JSONB,  -- Información adicional del contexto
  created_at TIMESTAMP DEFAULT NOW(),
  
  -- Evitar votos duplicados
  UNIQUE(event_id, voter_id)
);

CREATE INDEX idx_votes_voted_user ON votes (voted_user_id, created_at DESC);
CREATE INDEX idx_votes_voter ON votes (voter_id, created_at DESC);

-- Tabla de reputación (cache desnormalizado para performance)
CREATE TABLE user_reputation (
  user_id UUID PRIMARY KEY REFERENCES users(id) ON DELETE CASCADE,
  positive_votes INT DEFAULT 0,
  total_votes INT DEFAULT 0,
  rating DECIMAL(3,2) DEFAULT 0.00,
  rank_global INT,
  rank_country INT,
  rank_city INT,
  total_xp INT DEFAULT 0,
  level INT DEFAULT 1,
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de badges/insignias
CREATE TABLE badges (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  name VARCHAR(100) NOT NULL,
  description TEXT,
  icon_url TEXT,
  criteria JSONB,  -- Condiciones para obtener el badge
  rarity VARCHAR(20) CHECK (rarity IN ('common', 'rare', 'epic', 'legendary')),
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de relación usuarios-badges
CREATE TABLE user_badges (
  user_id UUID REFERENCES users(id) ON DELETE CASCADE,
  badge_id UUID REFERENCES badges(id),
  earned_at TIMESTAMP DEFAULT NOW(),
  PRIMARY KEY (user_id, badge_id)
);

-- Tabla de rankings (actualizada periódicamente)
CREATE TABLE leaderboards (
  id BIGSERIAL PRIMARY KEY,
  user_id UUID REFERENCES users(id) ON DELETE CASCADE,
  leaderboard_type VARCHAR(50), -- 'daily', 'weekly', 'monthly', 'all_time', 'country', 'city'
  scope VARCHAR(100),  -- 'global', 'ES', 'Madrid', etc.
  rank INT,
  score INT,
  period_start TIMESTAMP,
  period_end TIMESTAMP,
  updated_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_leaderboards_type_scope 
  ON leaderboards (leaderboard_type, scope, rank);
```

### 3.4 Sistema de Gamificación Detallado

Inspirado en Exercism.org y otras plataformas exitosas.

#### 3.4.1 Sistema de XP y Niveles

**Fuentes de XP:**

| Acción | XP Ganado | Límite Diario |
|--------|-----------|---------------|
| Recibir voto positivo | +10 XP | Ilimitado |
| Dar voto (confirmado) | +5 XP | 50 votos |
| Confirmar evento pendiente | +2 XP | Ilimitado |
| Racha de 7 días consecutivos | +50 XP | 1 vez/semana |
| Completar perfil | +20 XP | 1 vez |
| Añadir foto de vehículo | +10 XP | Por vehículo |
| Invitar amigo que se registra | +25 XP | Ilimitado |

**Curva de niveles:**

```javascript
// Fórmula exponencial inspirada en RPGs
function calculateLevel(xp) {
  return Math.floor(Math.pow(xp / 100, 0.5)) + 1;
}

function xpForNextLevel(currentLevel) {
  return Math.pow(currentLevel, 2) * 100;
}

// Ejemplos:
// Nivel 1: 0-100 XP
// Nivel 2: 100-400 XP
// Nivel 5: 1600-2500 XP
// Nivel 10: 8100-10000 XP
```

#### 3.4.2 Sistema de Badges (Insignias)

**Categorías de badges:**

**A) Participación:**
- 🚀 **Pionero**: Primeros 1000 usuarios
- 🎯 **Consistente**: 30 días consecutivos usando la app
- 💯 **Centurión**: 100 votos dados
- ⭐ **Estrella**: 100 votos recibidos

**B) Excelencia en conducción:**
- 🏆 **Ángel de la carretera**: Top 1% en reputación
- 🚴 **Amigo del ciclista**: 50 votos por respetar ciclistas
- 👶 **Guardián escolar**: 20 votos cerca de colegios
- 🌙 **Conductor nocturno responsable**: 30 votos entre 22:00-6:00

**C) Comunidad:**
- 🤝 **Embajador**: 10 amigos invitados
- 📸 **Fotógrafo**: Perfil completo con fotos de calidad
- 💬 **Social**: Interacciones en el feed (futuro)

**D) Geográficos:**
- 🗺️ **Explorador local**: Votos en 10 ciudades diferentes
- 🌍 **Trotamundos**: Votos en 5 países
- 🏔️ **Montañero**: Votos a >1500m altitud

**E) Especiales/Temporales:**
- 🎄 **Navidad segura 2025**: Evento especial diciembre
- 🚲 **Semana de la movilidad**: Evento anual septiembre
- 🏅 **Edición limitada**: Colaboraciones con marcas

#### 3.4.3 Rankings Múltiples

**Tipos de rankings (inspirado en Exercism):**

```
1. Rankings Temporales:
   ├─ Diario (últimas 24h)
   ├─ Semanal (lunes a domingo)
   ├─ Mensual
   └─ Todo el tiempo

2. Rankings Geográficos:
   ├─ Global
   ├─ País (España, Francia, etc.)
   ├─ Región/Comunidad Autónoma
   ├─ Provincia
   └─ Ciudad/Municipio

3. Rankings por Categoría:
   ├─ Conductores
   ├─ Motoristas
   ├─ Ciclistas
   └─ Por marca de vehículo (Toyota, BMW, etc.)

4. Rankings Especiales:
   ├─ "Most improved" (mayor progresión semanal)
   ├─ "Local hero" (más votos en tu ciudad)
   └─ "Night rider" (conducción nocturna)
