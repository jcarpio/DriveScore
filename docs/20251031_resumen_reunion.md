# Resumen de la Reunión - Proyecto DriveSkore

## Contexto del Proyecto

DriveSkore es una aplicación móvil desarrollada por Gamaliel como proyecto de fin de Máster, bajo la supervisión del Dr. José Carpio de la Universidad de Huelva. El proyecto busca mejorar el comportamiento vial mediante el concepto de "aldea global", eliminando el anonimato de los conductores y creando un sistema de valoración entre usuarios de la vía pública.

## Estado Actual del Desarrollo

### Funcionalidades Implementadas

La aplicación cuenta actualmente con las siguientes características operativas:

**Sistema de Captura de Eventos:**
- Captura automática de matrículas mediante OCR (Reconocimiento Óptico de Caracteres)
- Registro de posición GPS, velocidad y datos de ubicación
- Sistema de evaluación pendiente que permite revisar capturas posteriormente
- Integración con sensores Bluetooth para detección de proximidad

**Gestión de Usuarios y Vehículos:**
- Sistema de login con verificación por correo electrónico
- Perfiles de usuario con sistema de reputación
- Posibilidad de asociar múltiples vehículos a un usuario (coche, moto, bicicleta, patinete)
- Sistema de vehículo activo para identificar correctamente al conductor

**Sistema de Valoración:**
- Algoritmo de puntuación basado en distancia, velocidad y posición
- Ventana temporal de 2-3 minutos para identificar conductores cercanos
- Sistema de comentarios y valoraciones por estrellas
- Insignias conseguidas mostradas en el perfil

**Protección de Datos:**
- Solo se pueden valorar usuarios registrados en la aplicación (consentimiento implícito)
- Restricciones en el escaneo de dispositivos Bluetooth
- Sistema de vehículo activo para evitar valoraciones incorrectas

## Principales Puntos Discutidos

### 1. Cambio de Enfoque: De Matrículas a Personas

El Dr. Carpio enfatizó repetidamente que el sistema debe centrarse en valorar **personas**, no matrículas. Este es un cambio fundamental en la filosofía de la aplicación por varias razones:

- Una persona puede utilizar múltiples vehículos (coche, moto, bicicleta)
- Las matrículas resultan impersonales y no generan engagement
- El concepto de "aldea global" requiere identidades personales visibles
- Las valoraciones deben seguir a la persona independientemente del vehículo utilizado

### 2. Protección de Datos y Consentimiento

Se acordó que solo se podrán valorar usuarios registrados en la aplicación, garantizando así el consentimiento para la toma de datos. Esto resuelve problemas legales importantes relacionados con:

- Captura de imágenes y datos de personas sin consentimiento
- Escaneo de dispositivos Bluetooth
- Almacenamiento de información personal

### 3. Resolución de Conflictos

Se identificó la necesidad de implementar un sistema para resolver situaciones donde:

- Múltiples conductores comparten un vehículo (padre e hijo)
- Una valoración negativa se asigna incorrectamente
- El usuario puede demostrar que no estaba en el lugar del incidente

El sistema actual ya contempla parcialmente esto mediante el "vehículo activo", pero se requieren mecanismos adicionales de verificación cruzada con GPS y Bluetooth del usuario valorado.

### 4. Interfaz de Usuario y Usabilidad

**Modo Conducción:**
- La aplicación debe poder ejecutarse en segundo plano
- Permitir el uso simultáneo de otras aplicaciones (Google Maps)
- Captura de eventos sin interrumpir la navegación

**Botón de Captura:**
Gamaliel está intentando implementar un botón Bluetooth físico, pero el Dr. Carpio sugirió alternativas más accesibles:

- **Opción preferida:** Botón flotante en pantalla (similar a la burbuja de Google Maps)
- **Alternativa 1:** Mapeo de botones físicos del móvil (volumen, encendido)
- **Última opción:** Botón Bluetooth como característica opcional

La preferencia por el botón flotante se debe a que no requiere hardware adicional y facilita la adopción masiva de la aplicación.

### 5. Información de Vehículos

Se acordó ampliar significativamente los datos de vehículos para mejorar la identificación:

**Datos obligatorios:**
- Foto del vehículo (vista frontal y lateral)
- Marca y modelo
- Año de fabricación
- Color
- Matrícula (cuando aplique)

**Datos adicionales para vehículos sin matrícula:**
- Para bicicletas: número de serie (útil para verificar robos en bases de datos europeas)
- Para patinetes: identificación única (especialmente relevante dado que pronto será obligatoria la matriculación)

### 6. Gamificación y Sistema de Incentivos

Inspirándose en BlaBlaCar, se discutió la importancia de:

**Sistema de Insignias:**
- Mostrar insignias conseguidas destacadamente
- Visualizar insignias pendientes de conseguir (en gris/sombreado)
- Crear categorías como "Super Driver", "Embajador", etc.

**Beneficios Potenciales:**
- Descuentos en seguros de automóvil basados en reputación
- Bonificaciones en servicios relacionados con movilidad
- Reconocimiento social mediante elementos visuales (coronas, marcos especiales en fotos de perfil)

El Dr. Carpio destacó el valor psicológico de este sistema: "El simple hecho de que te voten hace que la gente se comporte mejor".

## Análisis de Viabilidad y Próximos Pasos

### Plan de Lanzamiento Piloto

Con fecha límite de entrega el 24 de noviembre (quedan solo 3 semanas), se definió una estrategia de lanzamiento urgente:

**Público Objetivo Inicial:**
- Alumnos de la Universidad de Huelva
- Enfoque en el Campus del Carmen (zona geográfica concentrada)
- Contacto con delegados de curso para distribución viral

**Estrategia de Incentivos:**
- Sorteo de premios para participantes (Meta Quest 3, iPhone)
- Periodo de prueba de una semana
- Recopilación intensiva de feedback

**Ventaja del Campus Universitario:**
- Alta densidad de usuarios potenciales en área reducida
- Movimientos predecibles y repetitivos (clases, cafetería, biblioteca)
- Mayor probabilidad de interacciones entre usuarios registrados
- Comunidad receptiva a aplicaciones tecnológicas

### Funcionalidades Críticas Pre-Lanzamiento

**Prioridad Máxima (para el 6 de noviembre):**

1. **Rediseño del Sistema de Perfiles:**
   - Cambiar toda la UI para mostrar nombres de personas en lugar de matrículas
   - Implementar gestión completa de múltiples vehículos por usuario
   - Añadir campos de foto, marca, modelo, año y color para cada vehículo

2. **Botón de Captura:**
   - Implementar botón flotante en pantalla (opción preferida)
   - Si no es viable, mapear botón físico del dispositivo
   - Como último recurso, mantener solo el botón Bluetooth como opcional

3. **Modo Conducción:**
   - Ejecutar aplicación en segundo plano
   - Permitir uso simultáneo de navegadores GPS
   - Activación sencilla al inicio del viaje

4. **Sistema de Feedback:**
   - Pestaña de "Ayuda" o "Feedback" en menú principal
   - Formulario para reportar problemas y sugerencias
   - Recopilación automática de métricas de uso

**Prioridad Alta (deseable para lanzamiento):**

5. **Detección Automática de Conducción:**
   - Usar acelerómetro para detectar movimiento vehicular
   - Ventana emergente preguntando qué vehículo se está usando
   - Activación automática del modo conducción

6. **Sistema de Verificación de Perfil:**
   - Verificación mediante correo electrónico (ya implementado)
   - Badge visual de "Perfil Verificado"
   - Consideración de verificación adicional en futuro (DNI, carnet de conducir)

7. **Resolución de Conflictos:**
   - Sistema de apelación de valoraciones negativas
   - Verificación cruzada con datos GPS del usuario valorado
   - Posibilidad de aportar pruebas (ubicación alternativa)

### Funcionalidades Pospuestas (Post-Lanzamiento)

**Análisis y Métricas:**
- Estadísticas de uso de la aplicación
- Tiempos de ejecución y latencia
- Consumo de batería
- Análisis de patrones de uso

**Optimizaciones:**
- Mejora del algoritmo de emparejamiento
- Reducción del consumo de recursos
- Optimización de la base de datos

**Características Avanzadas:**
- Integración con compañías de seguros
- Sistema de recompensas más complejo
- Versión iOS (actualmente solo Android)

## Consideraciones Técnicas Importantes

### Arquitectura Actual

La aplicación está desarrollada con las siguientes características técnicas:

**Backend:**
- Base de datos para almacenamiento de usuarios, vehículos y valoraciones
- Sistema de autenticación y gestión de sesiones
- API para comunicación con dispositivos móviles

**Frontend Mobile (Android):**
- Desarrollo nativo Android
- Integración con sensores del dispositivo (GPS, acelerómetro, cámara)
- OCR para reconocimiento de matrículas
- Escaneo Bluetooth

**Versión Web:**
- Existe una versión web funcional pero limitada (sin acceso a sensores)
- Principalmente para visualización y gestión de perfil

### Desafíos Técnicos Identificados

1. **Generación de APK:**
   - Gamaliel ha tenido problemas al generar APKs de producción
   - El OCR fallaba en versiones compiladas
   - Pendiente de verificar si el problema persiste con las nuevas funcionalidades

2. **Emparejamiento Bluetooth:**
   - Dificultades para conectar el botón Bluetooth desde la aplicación
   - Funciona si se empareja desde ajustes del sistema, pero no desde la app
   - Requiere investigación adicional

3. **Ejecución en Segundo Plano:**
   - Android tiene restricciones estrictas para aplicaciones en background
   - Necesario implementar servicios de foreground con notificación persistente
   - Gestión cuidadosa del consumo de batería

4. **Ventana Temporal de Coincidencias:**
   - Actualmente fijada en 2-3 minutos
   - Requiere ajuste fino basado en datos reales de uso
   - Balance entre precisión y falsos positivos

## Lecciones Aprendidas y Mejores Prácticas

### Comparación con Otros Asistentes IA

Durante la conversación, Gamaliel mencionó su experiencia con diferentes asistentes IA para el desarrollo:

- **Claude:** Funciona excepcionalmente bien, especialmente para depuración
- **Gemini:** Buen rendimiento para procesamiento de imágenes
- **ChatGPT:** Rendimiento decepcionante, especialmente para consultas específicas

Esta observación es relevante para futuros desarrolladores que trabajen en proyectos similares.

### Inspiración en Casos de Éxito

El análisis del sistema de valoraciones de BlaBlaCar proporcionó insights valiosos:

- Importancia de mostrar valoraciones como personas reales con fotos
- Sistema de comentarios textuales complementa las estrellas
- Insignias y badges generan engagement y competición sana
- La transparencia genera confianza y mejora el comportamiento

### Filosofía del Proyecto

El Dr. Carpio enfatizó repetidamente el concepto de "aldea global":

> "Ya no es anónima, ya no es un ser anónimo, sino que tú eres una persona que está ahí, que ya no estás oculto detrás de un coche, sino que eres una persona pública en todo. La gente te puede conocer, te puede votar, y ese simple hecho ya hace que la gente se comporte mejor."

Este concepto psicológico es fundamental para el éxito del proyecto y debe guiar todas las decisiones de diseño.

## Conclusiones y Recomendaciones

### Priorización Crítica

Con solo tres semanas hasta la entrega, es fundamental:

1. **Enfocarse en funcionalidad básica operativa** antes que en características avanzadas
2. **Simplificar donde sea posible** (botón flotante vs. Bluetooth, por ejemplo)
3. **Priorizar la experiencia de usuario** sobre la perfección técnica
4. **Generar datos reales de uso** mediante el programa piloto en el campus

### Factores Críticos de Éxito

Para que el lanzamiento piloto sea exitoso, se requiere:

1. **Masa crítica de usuarios:** Mínimo 40-50 usuarios activos en el Campus del Carmen
2. **Funcionalidad estable:** La aplicación debe funcionar sin crashes críticos
3. **Facilidad de uso:** Instalación y configuración deben ser triviales
4. **Incentivos claros:** Los sorteos y premios son fundamentales para la adopción inicial
5. **Feedback loop:** Sistema robusto para recopilar opiniones y sugerencias

### Viabilidad del Proyecto

El proyecto DriveSkore es técnicamente viable y conceptualmente sólido, pero enfrenta dos desafíos principales:

**Desafío del Huevo y la Gallina:**
- La aplicación solo tiene valor con múltiples usuarios registrados
- Los usuarios solo se registrarán si ven valor inmediato
- Solución: Lanzamiento concentrado geográficamente (campus) con incentivos

**Desafío Temporal:**
- Tres semanas es un plazo muy ajustado
- Requiere priorización despiadada de funcionalidades
- Necesario aceptar que algunas características quedarán para futuras versiones

### Potencial a Largo Plazo

Si el piloto demuestra tracción, DriveSkore tiene potencial significativo:

1. **Monetización via seguros:** Las aseguradoras pagarían por acceso a datos de reputación
2. **Expansión a otras universidades y ciudades**
3. **Integración con otras plataformas de movilidad**
4. **Datos valiosos sobre patrones de conducción y movilidad urbana**

## Cronograma de Tareas

### Semana 1 (28 octubre - 3 noviembre)

**Lunes 28 - Martes 29:**
- Consultar a Claude sobre implementación de botón flotante
- Rediseñar base de datos para priorizar usuarios sobre matrículas
- Comenzar refactorización de UI

**Miércoles 30 - Jueves 31:**
- Implementar sistema de múltiples vehículos por usuario
- Añadir campos de foto, marca, modelo, año y color
- Actualizar formularios de registro de vehículos

**Viernes 1 - Domingo 3:**
- Implementar botón flotante (o alternativa de botón físico)
- Añadir pestaña de Feedback/Ayuda
- Testing intensivo de funcionalidades críticas

### Semana 2 (4 - 10 noviembre)

**Lunes 4 - Martes 5:**
- Implementar modo conducción en segundo plano
- Optimizar consumo de batería
- Probar integración con Google Maps

**Miércoles 6 (FECHA LÍMITE VERSIÓN BETA):**
- Generar APK de producción funcional
- Testing exhaustivo en múltiples dispositivos
- Preparar materiales de distribución

**Jueves 7 - Viernes 8:**
- Contactar con delegados de curso
- Preparar campaña de lanzamiento
- Crear materiales promocionales (carteles, posts redes sociales)

**Sábado 9 - Domingo 10:**
- Lanzamiento oficial del piloto
- Monitorización activa de instalaciones
- Soporte técnico a primeros usuarios

### Semana 3 (11 - 17 noviembre)

**Lunes 11 - Viernes 15:**
- Recopilación de feedback de usuarios
- Corrección de bugs críticos
- Ajustes basados en uso real

**Sábado 16 - Domingo 17:**
- Análisis de datos recopilados
- Preparación de estadísticas para documentación
- Cierre del periodo de pruebas

### Semana 4 (18 - 24 noviembre)

**Lunes 18 - Miércoles 20:**
- Redacción de documentación final del proyecto
- Inclusión de resultados del piloto
- Preparación de análisis estadísticos

**Jueves 21 - Domingo 24:**
- Preparación de presentación
- Revisión final de documentación
- Envío de proyecto (24 noviembre)

---

## Lista de Issues para GitHub

### Milestone 1: Versión Beta Operativa (Deadline: 6 noviembre 2024)

#### Issue #1: Rediseño del Sistema de Perfiles (Prioridad: CRÍTICA)
**Labels:** `enhancement`, `breaking-change`, `ui/ux`

**Descripción:**
Refactorizar toda la aplicación para centrar el sistema en PERSONAS en lugar de MATRÍCULAS.

**Tareas:**
- [ ] Modificar esquema de base de datos: Usuario -> 1:N Vehículos
- [ ] Actualizar todas las vistas para mostrar nombres/fotos de usuarios en lugar de matrículas
- [ ] Cambiar "Conductores más valorados" para mostrar personas, no vehículos
- [ ] Actualizar algoritmo de coincidencias para buscar usuarios, no matrículas
- [ ] Migrar datos existentes al nuevo esquema
- [ ] Actualizar documentación de API

**Criterios de Aceptación:**
- Al valorar a alguien, se muestra nombre y foto del usuario
- La matrícula aparece solo como dato secundario del vehículo
- El perfil público muestra al usuario con todos sus vehículos

---

#### Issue #2: Gestión Completa de Vehículos (Prioridad: CRÍTICA)
**Labels:** `enhancement`, `feature`

**Descripción:**
Implementar sistema robusto para que usuarios puedan gestionar múltiples vehículos.

**Tareas:**
- [ ] Añadir campo de foto de vehículo (obligatorio)
- [ ] Añadir campos: marca, modelo, año, color (obligatorios)
- [ ] Añadir campo matrícula (opcional, para bicicletas/patinetes)
- [ ] Añadir campo número de serie para bicicletas
- [ ] Crear interfaz para añadir/editar/eliminar vehículos
- [ ] Implementar selector de "vehículo activo"
- [ ] Añadir validación de fotos (tamaño, formato)
- [ ] Implementar compresión de imágenes para optimizar almacenamiento

**Criterios de Aceptación:**
- Usuario puede tener mínimo 1 vehículo, máximo ilimitado
- Cada vehículo tiene foto visible de al menos 2 ángulos
- Sistema identifica correctamente el vehículo activo al valorar
- Fotos se comprimen automáticamente sin pérdida notable de calidad

---

#### Issue #3: Implementar Botón Flotante de Captura (Prioridad: CRÍTICA)
**Labels:** `enhancement`, `feature`, `ui/ux`

**Descripción:**
Crear un botón flotante persistente que permita capturar eventos sin salir de otras aplicaciones.

**Tareas:**
- [ ] Investigar permisos necesarios para overlay en Android
- [ ] Implementar servicio de foreground para botón flotante
- [ ] Diseñar UI del botón (pequeño, discreto, accesible)
- [ ] Añadir animaciones de feedback al pulsar
- [ ] Implementar lógica de captura desde segundo plano
- [ ] Permitir posicionar el botón en pantalla (drag & drop)
- [ ] Añadir configuración para mostrar/ocultar botón
- [ ] Testing en diferentes versiones de Android (8.0+)

**Alternativa si no es viable:**
- [ ] Mapear botón de volumen para captura rápida
- [ ] Implementar gestos (shake) como alternativa

**Criterios de Aceptación:**
- Botón visible sobre todas las aplicaciones (incluyendo Google Maps)
- Respuesta inmediata al toque (<100ms)
- No interfiere con controles de otras apps
- Consumo mínimo de batería (<1% por hora)

---

#### Issue #4: Modo Conducción y Ejecución en Segundo Plano (Prioridad: CRÍTICA)
**Labels:** `enhancement`, `feature`, `performance`

**Descripción:**
Implementar modo que permite a la app funcionar en background mientras se usan otras aplicaciones.

**Tareas:**
- [ ] Crear servicio de foreground con notificación persistente
- [ ] Implementar recolección continua de GPS en background
- [ ] Optimizar frecuencia de muestreo de GPS (balance precisión/batería)
- [ ] Implementar escaneo periódico de dispositivos Bluetooth cercanos
- [ ] Añadir botón de "Iniciar Modo Conducción" en pantalla principal
- [ ] Guardar datos localmente y sincronizar cuando hay conexión
- [ ] Implementar wake locks apropiados para mantener sensores activos
- [ ] Añadir gestión de batería baja (pausar tracking automáticamente)

**Criterios de Aceptación:**
- App funciona correctamente en background durante >1 hora
- Consumo de batería <5% por hora de uso
- Datos de GPS precisos (margen error <10 metros)
- App sobrevive a cambios de configuración (rotación, multitarea)

---

#### Issue #5: Sistema de Feedback de Usuarios (Prioridad: ALTA)
**Labels:** `enhancement`, `feature`

**Descripción:**
Añadir canal de comunicación directa para que usuarios reporten problemas y sugerencias.

**Tareas:**
- [ ] Crear nueva pestaña "Ayuda/Feedback" en navegación principal
- [ ] Diseñar formulario de feedback (categorías: bug, sugerencia, otro)
- [ ] Implementar captura automática de logs del dispositivo
- [ ] Añadir opción de adjuntar capturas de pantalla
- [ ] Crear endpoint backend para recibir feedback
- [ ] Implementar sistema de tickets o integración con email
- [ ] Añadir campo de respuesta opcional del usuario
- [ ] Crear panel admin para gestionar feedback recibido

**Criterios de Aceptación:**
- Formulario accesible desde cualquier pantalla
- Email de confirmación enviado al reportar
- Logs técnicos adjuntados automáticamente
- Respuesta automática agradeciendo el feedback

---

#### Issue #6: Generar APK de Producción Funcional (Prioridad: CRÍTICA)
**Labels:** `build`, `deployment`

**Descripción:**
Resolver problemas de compilación y generar APK distribuible.

**Tareas:**
- [ ] Configurar correctamente ProGuard/R8 para no ofuscar clases críticas
- [ ] Verificar que OCR funciona en build de release
- [ ] Configurar signing keys para producción
- [ ] Optimizar tamaño del APK (remover recursos no utilizados)
- [ ] Testing exhaustivo en dispositivos físicos (no emulador)
- [ ] Crear variantes de build: debug, beta, production
- [ ] Documentar proceso de compilación para futuras versiones
- [ ] Configurar versionado semántico (vX.Y.Z)

**Criterios de Aceptación:**
- APK instala correctamente en dispositivos Android 8.0+
- OCR funciona correctamente en build de producción
- Tamaño APK <50MB
- No crashes al iniciar en modo release

---

### Milestone 2: Lanzamiento Piloto Campus (Deadline: 10 noviembre 2024)

#### Issue #7: Materiales de Marketing y Distribución (Prioridad: ALTA)
**Labels:** `documentation`, `marketing`

**Descripción:**
Crear materiales promocionales para el lanzamiento en el campus universitario.

**Tareas:**
- [ ] Diseñar cartel informativo con QR de descarga
- [ ] Crear post para redes sociales (Instagram, Twitter)
- [ ] Preparar email para delegados de curso
- [ ] Crear guía rápida de uso (1 página, muy visual)
- [ ] Diseñar FAQ respondiendo dudas comunes
- [ ] Preparar video demo de 60 segundos
- [ ] Crear landing page con información del piloto
- [ ] Diseñar banner digital para pantallas del campus

**Criterios de Aceptación:**
- Materiales aprobados por supervisor
- QR code generado y testeado
- Video demo subido a YouTube/Vimeo
- Landing page responsive y accesible

---

#### Issue #8: Campaña de Incentivos y Sorteo (Prioridad: ALTA)
**Labels:** `marketing`, `gamification`

**Descripción:**
Organizar sorteo de premios para incentivar participación en el piloto.

**Tareas:**
- [ ] Definir premios del sorteo (Meta Quest, iPhone, etc.)
- [ ] Establecer mecánica del sorteo (transparente y justa)
- [ ] Crear términos y condiciones legales del sorteo
- [ ] Implementar sistema de registro de participantes
- [ ] Diseñar comunicación del sorteo en materiales
- [ ] Programar fecha y método de anuncio de ganadores
- [ ] Preparar sistema de verificación de ganadores
- [ ] Documentar proceso para cumplir normativa de sorteos

**Criterios de Aceptación:**
- Términos legales revisados por asesor
- Sistema de registro automático al usar app >7 días
- Comunicación clara de fechas y premios
- Proceso de sorteo verificable y transparente

---

#### Issue #9: Sistema de Métricas de Uso (Prioridad: MEDIA)
**Labels:** `feature`, `analytics`

**Descripción:**
Implementar recopilación de métricas para analizar uso durante el piloto.

**Tareas:**
- [ ] Integrar sistema de analytics (Firebase, Mixpanel, o custom)
- [ ] Trackear eventos clave: instalación, registro, primera valoración
- [ ] Medir tiempo de sesión y frecuencia de uso
- [ ] Registrar errores y crashes automáticamente
- [ ] Medir consumo de batería promedio
- [ ] Trackear latencia en operaciones críticas (OCR, GPS)
- [ ] Recopilar datos de hardware (versión Android, modelo dispositivo)
- [ ] Crear dashboard para visualizar métricas en tiempo real

**Criterios de Aceptación:**
- Datos anonimizados respetando GDPR
- Dashboard accesible para supervisor
- Métricas actualizadas cada hora
- Alertas automáticas para errores críticos

---

### Milestone 3: Funcionalidades Avanzadas (Deadline: 17 noviembre 2024)

#### Issue #10: Detección Automática de Conducción (Prioridad: MEDIA)
**Labels:** `enhancement`, `feature`, `ai/ml`

**Descripción:**
Usar acelerómetro y giroscopio para detectar automáticamente cuándo el usuario está conduciendo.

**Tareas:**
- [ ] Investigar patrones de aceleración típicos de vehículos
- [ ] Implementar algoritmo de detección (umbral de velocidad + tiempo)
- [ ] Diferenciar entre caminar, bicicleta, coche (si es posible)
- [ ] Mostrar notificación preguntando qué vehículo se usa
- [ ] Permitir confirmación/negación de detección
- [ ] Activar modo conducción automáticamente tras confirmación
- [ ] Añadir configuración para habilitar/deshabilitar auto-detección
- [ ] Testing en diferentes escenarios de movilidad

**Criterios de Aceptación:**
- Detección correcta en >80% de casos
- Sin falsos positivos al caminar o estar en transporte público
- Notificación discreta y no intrusiva
- Usuario puede cancelar la detección fácilmente

---

#### Issue #11: Sistema de Insignias y Gamificación (Prioridad: MEDIA)
**Labels:** `enhancement`, `gamification`, `ui/ux`

**Descripción:**
Mejorar sistema de insignias para aumentar engagement de usuarios.

**Tareas:**
- [ ] Diseñar insignias atractivas visualmente
- [ ] Definir criterios para obtener cada insignia
- [ ] Implementar visualización de insignias en perfil
- [ ] Mostrar insignias no conseguidas en gris/sombreado
- [ ] Añadir marco especial para foto de perfil según reputación
- [ ] Implementar notificaciones al conseguir insignia nueva
- [ ] Crear ranking de usuarios por insignias/reputación
- [ ] Añadir iconos especiales (corona, estrella) para usuarios destacados

**Ejemplos de Insignias:**
- Super Driver: >100 valoraciones positivas
- Madrugador: >50 viajes antes de las 8:00
- Embajador: >10 usuarios referidos
- Ciclista Urbano: >100km en bicicleta
- Conductor Seguro: 0 valoraciones negativas en 3 meses

**Criterios de Aceptación:**
- Mínimo 10 insignias diferentes implementadas
- Visualización clara en perfil
- Sistema escalable para añadir nuevas insignias
- Insignias compartibles en redes sociales

---

#### Issue #12: Sistema de Resolución de Conflictos (Prioridad: MEDIA)
**Labels:** `enhancement`, `feature`, `legal`

**Descripción:**
Implementar mecanismo para apelar valoraciones incorrectas.

**Tareas:**
- [ ] Crear botón "Reportar valoración incorrecta" en cada valoración
- [ ] Formulario para explicar por qué la valoración es incorrecta
- [ ] Verificación automática: comparar GPS del valorado vs valorador
- [ ] Opción de adjuntar pruebas (captura de otra ubicación, etc.)
- [ ] Sistema de mediación (manual, por administrador)
- [ ] Notificación al valorador sobre la disputa
- [ ] Implementar límite de apelaciones (prevenir abuso)
- [ ] Log de todas las apelaciones para análisis

**Criterios de Aceptación:**
- Proceso de apelación simple (<3 pasos)
- Verificación automática cuando hay datos GPS contradictorios
- Resolución en <48 horas para casos claros
- Sistema de prevención de apelaciones frívolas (límite 3/mes)

---

#### Issue #13: Optimización de Rendimiento (Prioridad: MEDIA)
**Labels:** `performance`, `bug`, `optimization`

**Descripción:**
Optimizar consumo de recursos y velocidad de la aplicación.

**Tareas:**
- [ ] Perfilar la app con Android Profiler
- [ ] Optimizar consultas a base de datos (índices, lazy loading)
- [ ] Implementar caché de imágenes
- [ ] Reducir frecuencia de escaneo GPS (adaptativa según movimiento)
- [ ] Optimizar procesamiento de OCR (reducir resolución si es posible)
- [ ] Implementar paginación en listas largas
- [ ] Lazy loading de perfiles de usuario
- [ ] Comprimir imágenes antes de subir al servidor

**Métricas Objetivo:**
- Tiempo de inicio de app <2 segundos
- Consumo de RAM <150MB
- Consumo de batería <3% por hora en modo conducción
- Tamaño de caché <50MB

**Criterios de Aceptación:**
- App funciona fluidamente en dispositivos de gama media (2018+)
- No se perciben lags al navegar entre pantallas
- Carga de imágenes instantánea con conexión 4G

---

### Milestone 4: Documentación y Análisis (Deadline: 24 noviembre 2024)

#### Issue #14: Documentación Técnica Completa (Prioridad: ALTA)
**Labels:** `documentation`

**Descripción:**
Crear documentación técnica exhaustiva del proyecto.

**Tareas:**
- [ ] Documento de arquitectura del sistema
- [ ] Diagrama de base de datos con relaciones
- [ ] Documentación de API (endpoints, parámetros, respuestas)
- [ ] Diagramas de flujo de funcionalidades principales
- [ ] Manual de instalación y configuración de entorno desarrollo
- [ ] Guía de contribución para futuros desarrolladores
- [ ] Documentación de decisiones de diseño (ADRs)
- [ ] Comentarios en código (JavaDoc/KDoc)

**Criterios de Aceptación:**
- Documentación suficiente para que otro desarrollador entienda el proyecto
- Diagramas claros y profesionales
- Sin secciones incompletas o TODOs

---

#### Issue #15: Memoria del Proyecto (Prioridad: CRÍTICA)
**Labels:** `documentation`, `academic`

**Descripción:**
Redactar memoria completa del proyecto fin de máster.

**Tareas:**
- [ ] Introducción y contexto del proyecto
- [ ] Estado del arte y análisis de soluciones existentes
- [ ] Objetivos y alcance del proyecto
- [ ] Metodología de desarrollo utilizada
- [ ] Diseño del sistema (arquitectura, base de datos, UI/UX)
- [ ] Implementación y tecnologías utilizadas
- [ ] Resultados del piloto (estadísticas, feedback usuarios)
- [ ] Conclusiones y trabajo futuro
- [ ] Bibliografía y referencias
- [ ] Anexos (capturas de pantalla, código relevante)

**Criterios de Aceptación:**
- Memoria cumple requisitos formales de la universidad
- Extensión mínima 60 páginas (sin anexos)
- Incluye resultados reales del piloto
- Revisada por supervisor

---

#### Issue #16: Análisis de Resultados del Piloto (Prioridad: ALTA)
**Labels:** `documentation`, `analytics`, `academic`

**Descripción:**
Procesar y analizar datos recopilados durante el piloto en el campus.

**Tareas:**
- [ ] Exportar todos los datos del periodo de prueba
- [ ] Limpiar y anonimizar datos para análisis
- [ ] Calcular estadísticas clave:
  - [ ] Número total de usuarios registrados
  - [ ] Usuarios activos (>1 valoración)
  - [ ] Número total de valoraciones realizadas
  - [ ] Distribución de valoraciones (positivas vs negativas)
  - [ ] Tiempo promedio de uso por sesión
  - [ ] Zonas del campus con más actividad
  - [ ] Dispositivos y versiones de Android más usadas
- [ ] Analizar feedback cualitativo de usuarios
- [ ] Crear visualizaciones (gráficos, mapas de calor)
- [ ] Identificar patrones de uso interesantes
- [ ] Redactar conclusiones del experimento

**Criterios de Aceptación:**
- Análisis estadístico riguroso con significancia clara
- Visualizaciones profesionales y comprensibles
- Insights accionables para mejoras futuras
- Comparación con hipótesis iniciales del proyecto

---

#### Issue #17: Presentación del Proyecto (Prioridad: ALTA)
**Labels:** `documentation`, `academic`

**Descripción:**
Crear presentación para defensa del proyecto.

**Tareas:**
- [ ] Diseñar diapositivas (15-20 slides)
- [ ] Introducción: problema y motivación
- [ ] Solución propuesta y valor diferencial
- [ ] Demo en vivo de la aplicación
- [ ] Arquitectura técnica (simplificada)
- [ ] Resultados del piloto (con gráficos impactantes)
- [ ] Aprendizajes y desafíos superados
- [ ] Trabajo futuro y escalabilidad
- [ ] Preparar respuestas a preguntas frecuentes
- [ ] Ensayar presentación (duración objetivo: 20 minutos)

**Criterios de Aceptación:**
- Presentación visualmente atractiva y profesional
- Demo funciona sin fallos
- Ensayada al menos 3 veces completa
- Duración ajustada a límites de tiempo

---

### Issues Adicionales (Backlog - Post-Entrega)

#### Issue #18: Integración con Compañías de Seguros
**Labels:** `enhancement`, `feature`, `business`

**Descripción:**
Crear API para que aseguradoras puedan consultar reputación de usuarios (con consentimiento).

---

#### Issue #19: Versión iOS
**Labels:** `enhancement`, `platform`

**Descripción:**
Portar la aplicación a iOS usando Swift/SwiftUI o React Native.

---

#### Issue #20: Sistema de Recompensas por Reputación
**Labels:** `enhancement`, `gamification`, `business`

**Descripción:**
Implementar marketplace donde usuarios con alta reputación obtienen descuentos reales.

---

## Notas Finales

Este resumen captura la esencia de una reunión crítica en el desarrollo del proyecto DriveSkore. El cambio filosófico de valorar matrículas a valorar personas es fundamental y requiere refactorización significativa del código existente.

La ventana temporal de 3 semanas es extremadamente ajustada, por lo que la priorización es absolutamente crítica. El éxito del proyecto dependerá más de tener una versión funcional y estable con funcionalidades básicas que una versión perfecta con todas las características deseadas.

El lanzamiento piloto en el Campus del Carmen de la Universidad de Huelva es una estrategia inteligente que maximiza las probabilidades de interacciones entre usuarios registrados. El uso de incentivos (sorteos) es esencial para generar la masa crítica necesaria.

El proyecto tiene potencial real más allá del contexto académico, especialmente considerando posibles integraciones con compañías de seguros y el valor de los datos de movilidad urbana que podría generar.
