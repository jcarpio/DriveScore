# INFORME 01 - Desarrollo del MVP Inicial
## Proyecto DriveSkore: Plataforma de Evaluación de Comportamiento en la Conducción

**Autor:** Gamaliel  
**Tutor:** José  
**Fecha del informe:** 22 de octubre de 2025  
**Período cubierto:** 6-20 de octubre de 2025  
**Versión:** 1.0

---

## RESUMEN EJECUTIVO

Durante las dos primeras semanas de desarrollo (6-20 de octubre), se ha construido un Producto Mínimo Viable (MVP) funcional de DriveSkore, una plataforma diseñada para evaluar y mejorar el comportamiento de los conductores mediante un sistema de votación comunitaria. El MVP incluye reconocimiento automático de matrículas mediante OCR, sistema de votación y evaluación, y una aplicación híbrida (móvil y web) desplegada en producción.

Tras la reunión de supervisión del 20 de octubre con el tutor José, se identificaron limitaciones críticas en el enfoque inicial (especialmente el control por voz) y se definió una nueva dirección técnica basada en botones Bluetooth físicos y sistemas de identificación multifactorial (GPS, Bluetooth, acelerómetros) para resolver casos de uso complejos como la evaluación desde bicicletas.

**Estado actual:** MVP funcional desplegado con necesidad de pivote en la interacción usuario-sistema para garantizar usabilidad real y seguridad vial.

---

## 1. INTRODUCCIÓN

### 1.1 Contexto del Proyecto

DriveSkore nace como respuesta a la necesidad de mejorar el comportamiento en la conducción mediante un sistema de reconocimiento social positivo. A diferencia de sistemas punitivos tradicionales, DriveSkore se centra en premiar las buenas prácticas de conducción, creando una comunidad de conductores comprometidos con la seguridad vial.

### 1.2 Objetivos del Proyecto

#### Objetivo General
Desarrollar una plataforma tecnológica que permita a los usuarios evaluar el comportamiento de otros conductores de manera segura, sencilla y efectiva, fomentando conductas responsables en la vía.

#### Objetivos Específicos
1. Implementar un sistema de reconocimiento automático de matrículas (OCR)
2. Crear una interfaz de usuario intuitiva para evaluación rápida
3. Desarrollar un sistema de gamificación que incentive el uso continuado
4. Garantizar la seguridad del usuario durante la conducción
5. Construir una arquitectura escalable y mantenible

### 1.3 Alcance del MVP (Fase 1)

El MVP inicial se enfoca en:
- ✅ Captura y reconocimiento de matrículas españolas
- ✅ Sistema básico de votación (positivo/negativo)
- ✅ Aplicación móvil híbrida (iOS/Android)
- ✅ Panel web para visualización de datos
- ✅ Base de datos con perfiles de conductores
- ✅ Despliegue en producción (Vercel + Supabase)

---

## 2. ESTADO DEL ARTE Y ANÁLISIS PREVIO

### 2.1 Aplicaciones Similares

Se realizó un análisis de aplicaciones existentes en el mercado:

| Aplicación | Enfoque | Limitaciones Identificadas |
|------------|---------|---------------------------|
| **Waze** | Reportes de tráfico e incidentes | No evalúa conductores individuales |
| **Google Maps** | Navegación con reportes | Sistema de reportes genérico |
| **iOnRoad** | Seguridad mediante cámara | Enfocado en alertas, no en comunidad |
| **Rate Driver** | Evaluación de conductores | Baja adopción, interfaz compleja |

**Conclusión:** Existe una brecha en el mercado para una aplicación centrada específicamente en la evaluación comunitaria de conductores con un enfoque gamificado y de reconocimiento positivo.

### 2.2 Tecnologías Evaluadas

#### Reconocimiento de Matrículas (OCR)
Se evaluaron tres alternativas:

1. **Tesseract.js** (Cliente)
   - ❌ Precisión insuficiente para matrículas españolas (40-60%)
   - ❌ Alto consumo de recursos en móvil
   - ✅ Gratuito y offline

2. **OCR.space API** (Servidor)
   - ✅ Precisión 85-95% con optimización
   - ✅ Motor especializado en texto estructurado
   - ✅ API gratuita con límites razonables
   - ⚠️ Requiere conexión a internet

3. **Google Cloud Vision API**
   - ✅ Máxima precisión (~98%)
   - ❌ Coste elevado para MVP
   - ❌ Excesivo para el caso de uso

**Decisión:** OCR.space por balance óptimo entre precisión, coste y facilidad de implementación.

#### Stack Tecnológico Seleccionado

```
Frontend Mobile:
├── React Native (Expo)
├── TypeScript
├── Expo Camera
└── React Navigation

Backend:
├── Supabase (PostgreSQL + Auth + Storage)
└── OCR.space API

Deployment:
├── Vercel (Web)
└── Expo EAS (Mobile)

Desarrollo:
├── Git + GitHub
└── Claude AI (asistencia desarrollo)
```

---

## 3. DESARROLLO DEL MVP

### 3.1 Arquitectura del Sistema

#### 3.1.1 Diagrama de Componentes

```
┌─────────────────────────────────────────────────────────┐
│                    APLICACIÓN MÓVIL                      │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │   Camera     │  │   Capture    │  │   Rating     │  │
│  │   Module     │→ │   Screen     │→ │   Screen     │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
│         │                  │                  │          │
│         └──────────────────┼──────────────────┘          │
│                            ↓                             │
└────────────────────────────┼─────────────────────────────┘
                             │
                             ↓
┌────────────────────────────┼─────────────────────────────┐
│                       OCR SERVICE                         │
│                    (OCR.space API)                        │
│         Imagen → Procesamiento → Matrícula                │
└────────────────────────────┼─────────────────────────────┘
                             │
                             ↓
┌────────────────────────────┼─────────────────────────────┐
│                      SUPABASE BACKEND                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │  Auth    │  │ Database │  │ Storage  │  │   API   │ │
│  │ (Users)  │  │(Profiles)│  │ (Images) │  │  (RPC)  │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
└───────────────────────────────────────────────────────────┘
                             │
                             ↓
┌────────────────────────────┼─────────────────────────────┐
│                      WEB DASHBOARD                        │
│         Visualización y análisis de datos                 │
└───────────────────────────────────────────────────────────┘
```

#### 3.1.2 Modelo de Datos

```sql
-- Tabla de perfiles de conductores
CREATE TABLE profiles (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  plate VARCHAR(10) UNIQUE NOT NULL,
  user_id UUID REFERENCES auth.users(id),
  total_ratings INTEGER DEFAULT 0,
  average_score DECIMAL(3,2) DEFAULT 0.00,
  positive_votes INTEGER DEFAULT 0,
  negative_votes INTEGER DEFAULT 0,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de evaluaciones individuales
CREATE TABLE ratings (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  profile_id UUID REFERENCES profiles(id),
  rated_by UUID REFERENCES auth.users(id),
  score INTEGER CHECK (score IN (-1, 1)),
  attributes JSONB, -- almacena atributos específicos de la evaluación
  location GEOGRAPHY(POINT),
  timestamp TIMESTAMP DEFAULT NOW(),
  image_url TEXT
);

-- Índices para optimización
CREATE INDEX idx_profiles_plate ON profiles(plate);
CREATE INDEX idx_ratings_profile ON ratings(profile_id);
CREATE INDEX idx_ratings_timestamp ON ratings(timestamp DESC);
```

### 3.2 Implementación del Reconocimiento de Matrículas

#### 3.2.1 Proceso de Captura y Reconocimiento

El flujo implementado consta de las siguientes etapas:

1. **Captura de Imagen**
   ```typescript
   const capturePhoto = async () => {
     const photo = await cameraRef.current?.takePictureAsync({
       quality: 0.8,
       base64: true,
       skipProcessing: false
     });
     return photo;
   };
   ```

2. **Preprocesamiento**
   - Compresión de imagen (calidad 0.8)
   - Conversión a base64
   - Validación de formato

3. **Envío a OCR.space**
   ```typescript
   const recognizePlate = async (imageBase64: string) => {
     const formData = new FormData();
     formData.append('base64Image', `data:image/jpeg;base64,${imageBase64}`);
     formData.append('apikey', OCR_API_KEY);
     formData.append('language', 'eng');
     formData.append('isOverlayRequired', 'false');
     
     const response = await fetch('https://api.ocr.space/parse/image', {
       method: 'POST',
       body: formData
     });
     
     return await response.json();
   };
   ```

4. **Validación y Normalización**
   ```typescript
   const validateSpanishPlate = (text: string): string | null => {
     // Formatos soportados:
     // - 1234 ABC (estándar actual)
     // - AB-1234-CD (antiguo)
     // - M-1234 (vehículos oficiales)
     
     const patterns = [
       /^[0-9]{4}\s?[A-Z]{3}$/,           // 1234ABC o 1234 ABC
       /^[A-Z]{1,2}-[0-9]{4}-[A-Z]{2}$/, // AB-1234-CD
       /^[A-Z]-[0-9]{4}$/                 // M-1234
     ];
     
     const cleaned = text.toUpperCase().replace(/[^A-Z0-9-\s]/g, '');
     
     for (const pattern of patterns) {
       if (pattern.test(cleaned)) {
         return cleaned.replace(/\s+/g, ' ').trim();
       }
     }
     
     return null;
   };
   ```

#### 3.2.2 Optimizaciones Implementadas

Para mejorar la precisión del reconocimiento, se implementaron:

1. **Guías visuales en la cámara**
   - Rectángulo de enfoque
   - Indicador de distancia óptima
   - Feedback visual en tiempo real

2. **Detección de condiciones**
   - Verificación de iluminación adecuada
   - Detección de desenfoque
   - Validación de ángulo de captura

3. **Reintentos inteligentes**
   - Hasta 3 intentos automáticos
   - Ajuste de parámetros entre intentos
   - Feedback al usuario sobre calidad de imagen

**Resultados obtenidos:**
- Precisión: 85-95% en condiciones óptimas
- Tiempo de reconocimiento: 2-4 segundos
- Tasa de falsos positivos: <5%

### 3.3 Sistema de Evaluación y Votación

#### 3.3.1 Interfaz de Usuario

La pantalla de evaluación implementada incluye:

```typescript
interface RatingScreen {
  // Información del conductor
  plateDisplay: string;
  currentRating: number;
  totalVotes: number;
  
  // Opciones de votación
  voteOptions: {
    positive: {
      icon: '👍',
      attributes: ['Cortés', 'Prudente', 'Respeta distancia']
    },
    negative: {
      icon: '👎',
      attributes: ['Agresivo', 'Imprudente', 'No respeta señales']
    }
  };
  
  // Acciones
  submitVote: (score: number, attributes: string[]) => Promise<void>;
  cancel: () => void;
}
```

#### 3.3.2 Lógica de Negocio

```typescript
const submitRating = async (
  plate: string, 
  score: number, 
  attributes: string[]
) => {
  try {
    // 1. Buscar o crear perfil del conductor
    let profile = await supabase
      .from('profiles')
      .select('*')
      .eq('plate', plate)
      .single();
    
    if (!profile.data) {
      profile = await supabase
        .from('profiles')
        .insert({ plate })
        .select()
        .single();
    }
    
    // 2. Insertar valoración
    await supabase
      .from('ratings')
      .insert({
        profile_id: profile.data.id,
        rated_by: currentUser.id,
        score,
        attributes,
        location: currentLocation,
        timestamp: new Date().toISOString()
      });
    
    // 3. Actualizar estadísticas del perfil
    await supabase.rpc('update_profile_stats', {
      p_profile_id: profile.data.id
    });
    
    // 4. Notificar éxito
    showSuccessToast('¡Evaluación enviada!');
    
  } catch (error) {
    console.error('Error submitting rating:', error);
    showErrorToast('Error al enviar la evaluación');
  }
};
```

#### 3.3.3 Función de Actualización de Estadísticas (PostgreSQL)

```sql
CREATE OR REPLACE FUNCTION update_profile_stats(p_profile_id UUID)
RETURNS void AS $$
BEGIN
  UPDATE profiles
  SET 
    total_ratings = (
      SELECT COUNT(*) 
      FROM ratings 
      WHERE profile_id = p_profile_id
    ),
    positive_votes = (
      SELECT COUNT(*) 
      FROM ratings 
      WHERE profile_id = p_profile_id AND score = 1
    ),
    negative_votes = (
      SELECT COUNT(*) 
      FROM ratings 
      WHERE profile_id = p_profile_id AND score = -1
    ),
    average_score = (
      SELECT AVG(score)::DECIMAL(3,2)
      FROM ratings 
      WHERE profile_id = p_profile_id
    ),
    updated_at = NOW()
  WHERE id = p_profile_id;
END;
$$ LANGUAGE plpgsql;
```

### 3.4 Despliegue y Producción

#### 3.4.1 Aplicación Móvil

**Configuración de Expo EAS Build:**

```json
// eas.json
{
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      }
    },
    "production": {
      "android": {
        "buildType": "app-bundle"
      },
      "ios": {
        "bundleIdentifier": "com.driveskore.app"
      }
    }
  }
}
```

**Proceso de generación de APK:**
```bash
# Instalar EAS CLI
npm install -g eas-cli

# Login en Expo
eas login

# Configurar proyecto
eas build:configure

# Generar APK de preview
eas build --platform android --profile preview

# Generar bundle de producción
eas build --platform android --profile production
```

**Estado actual:**
- ✅ APK de desarrollo generado
- ✅ Instalación exitosa en dispositivos de prueba
- ⏳ APK de producción pendiente (tras implementación de nuevas features)

#### 3.4.2 Panel Web

**Despliegue en Vercel:**

```bash
# Conectar repositorio con Vercel
vercel link

# Variables de entorno configuradas:
NEXT_PUBLIC_SUPABASE_URL=https://[proyecto].supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=[clave-anonima]

# Deploy automático en cada push a main
git push origin main
```

**URL de producción:** [Pendiente de configurar dominio personalizado]

---

## 4. EXPLORACIÓN DE CONTROL POR VOZ (DESCARTADO)

### 4.1 Motivación Inicial

Se intentó implementar un sistema de control por voz para permitir la evaluación de conductores sin necesidad de manipular el dispositivo móvil durante la conducción, con el objetivo de maximizar la seguridad vial.

### 4.2 Implementación Realizada

#### 4.2.1 Librería Utilizada

**expo-speech-recognition**

Razones de la elección:
- Integración nativa con Expo
- Soporte multiplataforma (iOS/Android)
- API relativamente simple
- Documentación disponible

#### 4.2.2 Sistema de Comandos

Se implementó un sistema multiidioma (español/inglés) con los siguientes comandos:

```typescript
const VOICE_COMMANDS = {
  'es-ES': {
    evaluate: ['evaluar', 'valorar'],
    photo: ['foto', 'capturar', 'captura'],
    confirm: ['sí', 'vale', 'confirmar'],
    cancel: ['no', 'cancelar'],
    send: ['enviar'],
    exit: ['salir']
  },
  'en-US': {
    evaluate: ['evaluate', 'rate'],
    photo: ['photo', 'capture'],
    confirm: ['yes', 'okay', 'confirm'],
    cancel: ['no', 'cancel'],
    send: ['send'],
    exit: ['exit']
  }
};
```

#### 4.2.3 Arquitectura del Modo Conducción

```typescript
interface DrivingMode {
  isActive: boolean;
  isListening: boolean;
  recognizedCommand: string | null;
  currentStep: 'idle' | 'waiting_photo' | 'confirming' | 'rating';
  
  // Funciones principales
  startListening: () => Promise<void>;
  stopListening: () => void;
  processCommand: (command: string) => void;
  provideFeedback: (type: 'audio' | 'visual', message: string) => void;
}
```

### 4.3 Problemas Encontrados

#### 4.3.1 Problemas Técnicos

1. **Timeout de reconocimiento**
   - El servicio de reconocimiento se detenía a los ~5 segundos
   - Error: `no-speech` detectado prematuramente
   - Imposible mantener escucha continua

2. **Precisión insuficiente**
   - Fallos en reconocimiento en entornos ruidosos
   - Confusión entre comandos similares
   - Problemas con acentos y variaciones dialectales

3. **Latencia**
   - 2-3 segundos de delay entre comando y acción
   - Inaceptable para contexto de conducción

4. **Consumo de batería**
   - Escucha continua drenaba batería rápidamente
   - No viable para sesiones de conducción prolongadas

#### 4.3.2 Comparación con Aplicaciones de Referencia

**Observación crítica del tutor José:**

"Ni Google Maps ni Waze implementan control por voz para funciones críticas durante la conducción. Si ellos, con todos sus recursos, no lo hacen, hay una razón técnica y de experiencia de usuario."

Análisis realizado:
- Google Maps: Solo comandos de voz para navegación, no para reportes
- Waze: Botones grandes en pantalla + comandos de voz limitados
- Ninguna permite fotografía por voz

**Conclusión:** Si las aplicaciones líderes del mercado evitan esta funcionalidad, es un indicador fuerte de problemas fundamentales de fiabilidad y seguridad.

### 4.4 Decisión Final

**El control por voz fue DESCARTADO** por las siguientes razones:

1. ❌ **Fiabilidad insuficiente** - Sistema que falla genera desconfianza
2. ❌ **Seguridad vial comprometida** - Usuario debe prestar atención al sistema en lugar de la conducción
3. ❌ **Experiencia de usuario frustrante** - Timeouts, errores de reconocimiento
4. ❌ **No resuelve casos de uso críticos** - Especialmente ciclistas o motoristas
5. ❌ **Consumo excesivo de recursos** - Batería y procesamiento

**Lección aprendida:** No enamorarse de una solución técnica sin validar su viabilidad real en el contexto de uso.

---

## 5. REUNIÓN DE SUPERVISIÓN (20 DE OCTUBRE)

### 5.1 Asistentes
- Gamaliel (estudiante)
- José (tutor del TFM)

### 5.2 Puntos Clave Discutidos

#### 5.2.1 El Caso de Uso Crítico: El Ciclista / Motorista

**Situación planteada:**

> Un ciclista va con ambas manos en el manillar y observa a un conductor que lo adelanta con la precaución adecuada (1.5m de distancia, velocidad reducida). El ciclista quiere reconocer este buen comportamiento con una valoración positiva.

**Problema identificado:**
- No puede soltar las manos del manillar (peligro de caída)
- No puede sacar el móvil del bolsillo
- No puede hacer una foto
- El móvil está ocupado (GPS, música)
- La acción debe ser inmediata (el conductor ya se alejó)

**Insight fundamental:**
Este caso de uso revela las limitaciones de cualquier solución basada en manipulación del smartphone durante la conducción/ciclismo.

#### 5.2.2 El Síndrome del Informático

**Advertencia del tutor:**

> "El mayor riesgo es perderse en la complejidad técnica y olvidar el objetivo principal: crear un producto que realmente sirva a las personas."

**Analogía del iPhone:**
Steve Jobs mostró el primer iPhone con múltiples gestos táctiles complejos. El equipo de ingeniería estaba orgulloso. Jobs lo rechazó diciendo: "Esto es demasiado complicado. La gente quiere algo que simplemente funcione."

**Aplicación al proyecto:**
- No se trata de demostrar habilidades técnicas avanzadas
- Se trata de resolver un problema real de forma efectiva
- La simplicidad es más valiosa que la complejidad

#### 5.2.3 Cambio de Filosofía: Del Prototipo al Producto

**Mentalidad INCORRECTA:**
"Tengo que terminar el proyecto en X semanas → Necesito código funcionando → Implemento lo que sea rápido"

**Mentalidad CORRECTA:**
"Quiero hacer un producto que realmente sirva → Investigo alternativas → Documento el proceso → Elijo la mejor solución"

**Implicaciones para el TFM:**
- El valor NO está en tener código funcionando
- El valor está en demostrar un proceso riguroso de investigación
- Documentar por qué algo NO funciona es tan valioso como lo que funciona
- La honestidad técnica es más importante que impresionar

### 5.3 Soluciones Propuestas por el Tutor

#### 5.3.1 Botón Bluetooth Físico

**Propuesta:**
Utilizar un botón Bluetooth simple (disponible por ~2€) que el usuario puede pulsar sin mirar.

**Ventajas:**
- ✅ No requiere manipular el móvil
- ✅ No requiere mirar la pantalla
- ✅ Funciona incluso con guantes
- ✅ Instalable en manillar de bicicleta o salpicadero de coche
- ✅ Extremadamente fiable (botón físico vs. voz)
- ✅ Bajo coste
- ✅ Batería duradera (meses con pila de botón)

**Funcionamiento propuesto:**

```
Usuario en bicicleta → Observa buena conducta → Pulsa botón
                                ↓
                    App captura contexto:
                    - Timestamp exacto
                    - Ubicación GPS
                    - Velocidad y dirección
                    - Dispositivos BT cercanos
                                ↓
              Votación queda en "cola pendiente"
                                ↓
    Usuario llega a destino → Abre app → Revisa pendientes
                                ↓
                    Confirma o descarta votaciones
```

**Dispositivos compatibles:**
- AB Shutter (control remoto BT para selfies)
- Botones Bluetooth genéricos (Amazon, AliExpress)
- Mandos de gamepad BT reciclados
- Incluso auriculares BT (botón de play/pause)

#### 5.3.2 Registro Diferido

**Concepto:**
Separar el momento de la observación del momento de la valoración.

**Flujo propuesto:**

1. **Durante la conducción (acción mínima):**
   - Usuario pulsa botón BT
   - App registra: GPS + timestamp + velocidad + BT scan
   - NO requiere interacción adicional
   - Usuario continúa conduciendo con total seguridad

2. **Después de la conducción (acción deliberada):**
   - Usuario abre app en lugar seguro
   - Ve lista de "votaciones pendientes"
   - Para cada una:
     - Ve ubicación en mapa
     - Ve hora y contexto
     - Identifica al conductor (ver sección 5.3.3)
     - Asigna puntuación y atributos
     - Confirma o descarta

**Ventajas de este enfoque:**
- ✅ Seguridad máxima durante conducción
- ✅ Usuario decide en momento tranquilo
- ✅ Puede recordar y contextualizar cada situación
- ✅ Reduce votaciones impulsivas/incorrectas

**Desafíos identificados:**
- Usuario debe recordar revisar pendientes
- Almacenamiento temporal de datos
- Asociar correctamente cada evento con el conductor

#### 5.3.3 Identificación Multifactorial

**Problema:**
Sin fotografía en tiempo real, ¿cómo identificar al conductor?

**Solución propuesta: Triangulación de datos**

```
IDENTIFICACIÓN DEL CONDUCTOR = f(GPS, Bluetooth, Velocidad, Dirección, Tiempo)
```

**Factores combinados:**

1. **GPS de alta precisión:**
   - Ubicación del evaluador
   - Ubicación de posibles conductores en la zona
   - Radio de búsqueda: 20-100 metros

2. **Escaneo Bluetooth:**
   - Identificar dispositivos BT únicos cercanos
   - Cada smartphone tiene MAC address BT única
   - Asociar MAC address con usuario registrado

3. **Acelerómetros y giroscopio:**
   - Velocidad de desplazamiento
   - Dirección de movimiento
   - Diferenciar vehículos que van en misma dirección vs. contraria

4. **Proximidad temporal:**
   - Ventana de tiempo: ±30 segundos
   - Filtrar usuarios que estaban en el lugar en ese momento

5. **Patrón de movimiento:**
   - Trayectoria de ambos usuarios
   - Convergencia y divergencia de rutas
   - Adelantamiento detectado


#### 5.3.4 Evolución Futura: Dispositivos Wearables

**Visión a medio plazo:**

El tutor menciona la próxima generación de dispositivos como **Meta Ray-Ban** (gafas inteligentes):

**Capacidades:**
- Cámara integrada en las gafas
- Captura de imagen con gesto simple o comando de voz
- Procesamiento de imagen en tiempo real
- Escaneo 3D del entorno

**Aplicación a DriveSkore:**
- Usuario dice "evaluar" mientras mira al vehículo
- Gafas capturan imagen de matrícula automáticamente
- OCR procesa en tiempo real
- Votación se genera sin manipular dispositivos

**Timeline:**
- Corto plazo (2025): Botón BT + identificación multifactorial
- Medio plazo (2026-2027): Integración con wearables
- Largo plazo (2028+): AR/VR integrado en la experiencia

### 5.4 Principios de Diseño Establecidos

El tutor enfatizó cuatro principios fundamentales:

#### 1. Fiabilidad Alemana
> "El sistema debe funcionar impecablemente, especialmente en las primeras versiones. Un sistema que falla genera desconfianza, y la confianza perdida es difícil de recuperar."

- Primera impresión es crítica
- Mejor hacer menos cosas pero que funcionen perfectamente
- No lanzar features hasta estar seguros de su fiabilidad

#### 2. Mínima Intrusión
> "No debe interferir con la conducción ni crear situaciones peligrosas. Si el usuario tiene que pensar en la app mientras conduce, hemos fracasado."

- Interacción durante conducción: <1 segundo
- No requiere mirar la pantalla
- No requiere manipulación compleja
- No distrae del entorno vial

#### 3. Facilidad Extrema
> "Debe ser tan simple que funcione incluso en las condiciones más restrictivas, como en bicicleta con las dos manos en el manillar."

- Si funciona para el ciclista, funciona para todos
- Un solo gesto/acción
- No requiere configuración previa
- Curva de aprendizaje: <30 segundos

#### 4. Eficiencia de Recursos
> "No puede drenar la batería del dispositivo. El usuario debe poder usar la app todo el día sin preocuparse."

- Consumo de batería: <5% por hora de uso
- Uso eficiente de GPS (actualización adaptativa)
- Bluetooth de baja energía (BLE)
- Procesamiento en background optimizado

---

## 6. DOCUMENTACIÓN: LA PIEDRA ANGULAR DEL TFM

### 6.1 La Importancia de Documentar

**Mensaje clave del tutor:**

> "Sin documentación, no hay proyecto. Puedes tener el código más impresionante del mundo, pero si no documentas el proceso, el análisis, las decisiones y los aprendizajes, tu TFM no vale nada."


### 6.2 Transparencia y Honestidad

**Principio fundamental:**

> "Es más valioso documentar por qué algo NO funcionó que solo mostrar lo que funcionó. La honestidad técnica demuestra madurez profesional."

**En este proyecto:**
- ✅ Documentar intento de control por voz y su fracaso
- ✅ Documentar alternativas evaluadas para OCR
- ✅ Documentar razones del pivot a botón BT
- ✅ Documentar limitaciones actuales del sistema

**Beneficios en la defensa:**
- Muestra proceso de pensamiento crítico
- Demuestra capacidad de adaptación
- Evidencia aprendizaje real
- Genera confianza en el tribunal

---

## 7. PLAN DE TRABAJO REVISADO

### 7.1 Cronograma Actualizado

**Fecha límite de entrega:** 24 de noviembre de 2025  
**Tiempo restante:** ~5 semanas

#### Semana 1 (20-26 octubre): Investigación y Diseño
- [x] Reunión con tutor (20 oct)
- [x] Generar informe 01 (este documento)
- [ ] Investigar botones Bluetooth disponibles
- [ ] Diseñar arquitectura de identificación multifactorial
- [ ] Crear mockups de nuevas pantallas (cola de pendientes)
- [ ] Documentar decisiones de diseño

#### Semana 2 (27 oct - 2 nov): Implementación Core
- [ ] Integrar biblioteca Bluetooth (react-native-ble-manager)
- [ ] Implementar captura de evento (botón press)
- [ ] Desarrollar sistema de almacenamiento temporal
- [ ] Crear pantalla de "Votaciones Pendientes"
- [ ] Generar informe 02

#### Semana 3 (3-9 nov): Sistema de Identificación
- [ ] Implementar lógica de escaneo GPS/BT
- [ ] Desarrollar algoritmo de matching
- [ ] Crear función de sugerencia de candidatos
- [ ] Pruebas de precisión del matching
- [ ] Generar informe 03

#### Semana 4 (10-16 nov): Pruebas y Refinamiento
- [ ] Pruebas de campo con ciclistas
- [ ] Pruebas de campo con conductores
- [ ] Ajustes basados en feedback
- [ ] Optimización de batería
- [ ] Generar informe 04

#### Semana 5 (17-24 nov): Finalización
- [ ] Generar APK de producción
- [ ] Documentación final del código
- [ ] Consolidar informes en documento TFM
- [ ] Preparar presentación
- [ ] Entrega del proyecto

### 7.2 Criterios de Éxito

**Para considerar el MVP exitoso:**

1. **Funcionalidad Core:**
   - ✅ Sistema de captura por botón BT funcional
   - ✅ Almacenamiento de eventos pendientes
   - ✅ Identificación de conductores con >70% precisión
   - ✅ Interfaz de confirmación de votaciones

2. **Seguridad:**
   - ✅ Cero manipulación del móvil durante conducción
   - ✅ Interacción <1 segundo
   - ✅ Cumplimiento normativa de seguridad vial

3. **Usabilidad:**
   - ✅ Funciona en bicicleta (caso más restrictivo)
   - ✅ Funciona con guantes
   - ✅ No requiere mirar pantalla

4. **Rendimiento:**
   - ✅ Consumo batería <5% por hora
   - ✅ Latencia botón→registro <500ms
   - ✅ Precisión identificación >70%

5. **Documentación:**
   - ✅ Mínimo 8 informes incrementales
   - ✅ Código comentado y estructurado
   - ✅ Diagramas de arquitectura
   - ✅ Documento TFM preliminar

### 7.3 Próximas Reuniones

**Frecuencia:** Lunes y Viernes
**Formato:** Virtual + informe previo
**Duración:** 1 Hora

**Agenda típica:**
1. Revisión del informe enviado previamente
2. Demo del progreso realizado
3. Discusión de bloqueos o problemas
4. Definición de objetivos para siguiente sesión
5. Confirmación de comprensión

---

## 8. ASPECTOS DE PRODUCTO Y GAMIFICACIÓN

### 8.1 Filosofía del Producto

**Principio fundamental:**
> "La gente no usa productos solo por dinero. La gente quiere formar parte de algo positivo, quiere ser reconocida por hacer las cosas bien."

### 8.2 Sistema de Votación

**Decisión inicial: Solo votos positivos**

**Razones:**
1. Evitar que se convierta en herramienta punitiva
2. Fomentar ambiente positivo y constructivo
3. Enfocarse en reconocimiento vs. castigo
4. Reducir riesgo de uso malintencionado

**Posible evolución:**
- Fase 1: Solo votos positivos
- Fase 2: Introducir votos negativos con moderación
- Fase 3: Sistema de reportes para infracciones graves

### 8.3 Elementos de Gamificación

Ya explorados en conversaciones previas, se reafirma:

**Sistema de Puntos y Niveles:**
- XP por cada voto recibido
- Niveles del 1 al 50
- Desbloqueo de insignias y avatares

**Ligas Mensuales:**
- Bronce → Plata → Oro → Platino → Diamante
- Ranking público
- Premios para top performers

**Logros y Medallas:**
- "Primera semana perfecta"
- "100 votos positivos"
- "Guardián de ciclistas"
- "Maestro de la cortesía"

### 8.4 Incentivos Externos

**Potenciales alianzas:**

1. **Compañías de seguros:**
   - Descuentos del 10-30% en prima
   - Basado en puntuación DriveSkore
   - Beneficio mutuo: mejores conductores = menos siniestros

2. **Gasolineras:**
   - Puntos canjeables por combustible
   - Descuentos en lavados
   - Programa de fidelización

3. **Talleres mecánicos:**
   - Descuentos en revisiones
   - Servicios premium para top users

4. **Gobierno/DGT:**
   - Reducción de puntos perdidos
   - Créditos para renovación de licencia
   - Reconocimiento oficial

### 8.5 Construcción de Comunidad

**Inspiración: Airbnb / Couchsurfing**

> "La gente participa en Airbnb y Couchsurfing no solo por ahorrarse dinero. Participan porque quieren formar parte de un movimiento, de una comunidad que comparte valores."

**Aplicación a DriveSkore:**
- Comunidad de "Buenos Conductores"
- Valores compartidos: respeto, seguridad, cortesía
- Reconocimiento social y orgullo de pertenencia
- Impacto positivo medible en la sociedad

**Features comunitarios:**
- Perfil público con estadísticas
- Tabla de líderes local/nacional
- Sistema de "siguiendo" a otros conductores
- Feed de actividad reciente
- Historias de buenos actos compartidas

---

## 9. LIMITACIONES Y RIESGOS IDENTIFICADOS

### 9.1 Limitaciones Técnicas

#### 9.1.1 Precisión de Identificación

**Escenario problemático:**
Múltiples conductores en un radio de 50m (atasco, semáforo).

**Riesgo:**
- Falsos positivos en matching
- Usuario evalúa al conductor incorrecto

**Mitigación:**
- Mostrar siempre lista de candidatos con probabilidad
- Permitir selección manual
- Aprender de confirmaciones del usuario
- En caso de ambigüedad alta, marcar como "no concluyente"

#### 9.1.2 Cobertura GPS

**Escenario problemático:**
Túneles, garajes subterráneos, zonas urbanas densas.

**Riesgo:**
- Pérdida de señal GPS
- Eventos sin geolocalización precisa

**Mitigación:**
- Usar última ubicación conocida + dirección de movimiento
- Marcador de "baja precisión" en el evento
- Permitir al usuario añadir contexto manualmente

#### 9.1.3 Privacidad y Bluetooth

**Preocupación:**
Escanear direcciones MAC de dispositivos Bluetooth puede considerarse invasivo.

**Consideraciones:**
- Solo almacenar hashes de MAC addresses
- No vincular MAC con datos personales
- Política de privacidad clara
- Cumplimiento RGPD

#### 9.1.4 Adopción del Hardware

**Riesgo:**
Usuarios no quieren comprar/configurar botón Bluetooth adicional.

**Mitigación:**
- App funciona SIN botón (método tradicional)
- Botón es opcional pero recomendado
- Incluir botón gratuito con promoción inicial
- Tutorial de configuración muy simple

### 9.2 Riesgos de Producto

#### 9.2.1 Votaciones Maliciosas

**Riesgo:**
Usuarios crean votaciones negativas falsas por venganza.

**Mitigación (Fase 1):**
- Solo votos positivos habilitados
- Restricción temporal: máximo X votos por hora
- Detección de patrones sospechosos
- Sistema de reportes para abuso

#### 9.2.2 Baja Adopción

**Riesgo:**
No hay suficientes usuarios para generar red de efectos.

**Mitigación:**
- Campaña de lanzamiento enfocada (ciclistas primero)
- Alianzas con asociaciones de ciclistas
- Gamificación agresiva inicial
- Programa de referidos

#### 9.2.3 Problemas Legales

**Riesgo:**
Grabación/almacenamiento de matrículas puede tener implicaciones legales.

**Mitigación:**
- Consulta legal antes de lanzamiento
- Política de privacidad robusta
- Consentimiento explícito del usuario
- Posibilidad de solicitar eliminación de datos

### 9.3 Riesgos de Desarrollo

#### 9.3.1 Tiempo Insuficiente

**Riesgo:**
5 semanas es ajustado para implementar sistema completo.

**Mitigación:**
- Priorizar features core
- MVP sin funcionalidades secundarias
- Documentar lo no implementado como "trabajo futuro"
- Enfocarse en demostración de concepto

#### 9.3.2 Complejidad del Algoritmo de Matching

**Riesgo:**
Algoritmo de identificación multifactorial puede ser muy complejo.

**Mitigación:**
- Empezar con versión simplificada (solo GPS)
- Iterar añadiendo factores gradualmente
- Documentar precisión de cada versión
- Aceptar precisión >70% como suficiente para MVP

---

## 10. LECCIONES APRENDIDAS

### 10.1 Técnicas

1. **No enamorarse de la solución técnica**
   - Aprendizaje: El control por voz era elegante pero no práctico
   - Acción futura: Validar viabilidad antes de implementar

2. **La simplicidad gana**
   - Aprendizaje: Botón físico > comandos de voz complejos
   - Acción futura: Siempre buscar la solución más simple que funcione

3. **Benchmarking es esencial**
   - Aprendizaje: Si Google Maps no lo hace, hay una razón
   - Acción futura: Estudiar qué hacen (y no hacen) los líderes del mercado

4. **OCR es difícil pero no imposible**
   - Aprendizaje: Tesseract fallaba, pero OCR.space funciona bien
   - Acción futura: Probar múltiples alternativas antes de descartar una aproximación

### 10.2 De Proceso

1. **Documentar en tiempo real**
   - Aprendizaje: Es mucho más fácil documentar mientras se hace
   - Acción futura: Informe cada 2-3 días, no al final

2. **Reuniones frecuentes con tutor**
   - Aprendizaje: Reunión del 20 oct evitó semanas de trabajo en dirección errónea
   - Acción futura: Mantener 2 reuniones semanales


### 10.3 De Producto

1. **El caso de uso crítico define todo**
   - Aprendizaje: Caso del ciclista reveló limitaciones fundamentales
   - Acción futura: Identificar y diseñar para el caso más restrictivo primero

2. **Seguridad vial > features cool**
   - Aprendizaje: Una feature que distrae durante conducción es inaceptable
   - Acción futura: Principio de "cero manipulación" como regla absoluta

3. **La confianza es frágil**
   - Aprendizaje: Un sistema que falla genera desconfianza duradera
   - Acción futura: Mejor hacer menos pero con máxima fiabilidad

4. **La gamificación importa**
   - Aprendizaje: Usuarios necesitan incentivos para adopción
   - Acción futura: Diseñar sistema de recompensas desde el inicio

---

## 11. PRÓXIMOS PASOS INMEDIATOS

### 11.1 Acciones Críticas (Esta Semana)

1. ✅ **Completar este informe** (HECHO)
2. ⏳ **Subir a GitHub**
   - Crear repositorio `DriveSkore-TFM`
   - Estructurar carpetas según propuesta
   - Commit inicial con código actual + este informe

3. ⏳ **Investigar botones Bluetooth**
   - Comprar AB Shutter (Amazon/AliExpress)
   - Probar compatibilidad con dispositivos propios
   - Documentar proceso de pairing

4. ⏳ **Diseñar mockups de nuevas pantallas**
   - Pantalla "Configurar Botón BT"
   - Pantalla "Votaciones Pendientes"
   - Pantalla "Confirmar Votación"
   - Usar Figma o similar

5. ⏳ **Reunión de seguimiento con José**
   - Presentar este informe
   - Validar plan de implementación
   - Resolver dudas sobre arquitectura

---

## 12. CONCLUSIONES PRELIMINARES

### 12.1 Situación Actual del Proyecto

Después de dos semanas de desarrollo intenso, DriveSkore cuenta con:

**✅ Logros:**
- MVP funcional con reconocimiento de matrículas (85-95% precisión)
- Aplicación híbrida desplegada en producción
- Base de datos operativa con gestión de perfiles y evaluaciones
- APK de desarrollo generado y probado
- Arquitectura escalable implementada

**❌ Problemas identificados:**
- Control por voz descartado por falta de fiabilidad
- Caso de uso del ciclista no resuelto con aproximación actual
- Interacción durante conducción no es suficientemente segura
- Falta de sistema de documentación estructurado

**🔄 Pivote estratégico:**
- De control por voz → Botón Bluetooth físico
- De votación inmediata → Registro diferido
- De identificación por foto → Identificación multifactorial

### 12.2 Viabilidad del Proyecto

**Evaluación:** ALTA

El pivot propuesto por el tutor es técnicamente viable y resuelve las limitaciones identificadas:

- Botones BT están disponibles, son económicos y funcionan de manera fiable
- Identificación multifactorial es implementable con tecnologías existentes
- Tiempo restante (5 semanas) es ajustado pero suficiente para MVP
- Caso de uso del ciclista quedaría resuelto satisfactoriamente

### 12.3 Valor del TFM

Más allá del producto final, este proyecto demuestra:

1. **Proceso de investigación riguroso**
   - Evaluación de múltiples alternativas técnicas
   - Análisis de viabilidad de cada opción
   - Benchmarking contra aplicaciones establecidas

2. **Capacidad de adaptación**
   - Reconocimiento temprano de problemas
   - Disposición a descartar trabajo previo cuando es necesario
   - Pivot inteligente basado en feedback de experto

3. **Pensamiento crítico**
   - Cuestionamiento de decisiones propias
   - Análisis de trade-offs (complejidad vs. funcionalidad)
   - Priorización de seguridad sobre innovación

4. **Metodología profesional**
   - Desarrollo iterativo
   - Documentación continua
   - Control de versiones
   - Colaboración con tutor

---

*Fecha: 22 de octubre de 2025*