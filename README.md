# 🌿 EcorutasApp

**EcorutasApp** es una aplicación Android desarrollada con **Jetpack Compose** cuyo objetivo es gestionar rutas ecológicas y de senderismo de forma sencilla, rápida y visual.  
Está diseñada para demostrar buenas prácticas de arquitectura moderna en Android, con un enfoque limpio, modular y accesible.

---

## 🧭 Descripción general

La aplicación permite:
- Ver una **lista de rutas** con búsqueda en tiempo real y filtro de favoritas.  
- Crear y editar rutas mediante un **formulario validado**.  
- Configurar **modo oscuro** y **tamaño de fuente** desde la pantalla de Ajustes.  
- Mostrar **mensajes de feedback** mediante *Snackbars* (éxito, error o validaciones).  
- Guardar preferencias de usuario de forma persistente con **DataStore**.  
- Presentar una UI moderna basada en **Material 3** con **ConstraintLayout** y accesibilidad básica.  
- (Opcional) Integrar un mapa con coordenadas o ubicación real.

---

## 🏗️ Arquitectura

El proyecto sigue una estructura modular basada en **MVVM (Model-View-ViewModel)** y **StateFlow**:

app/
├─ data/ → Modelos y DataStore (persistencia)
├─ nav/ → Rutas de navegación Compose
├─ ui/screens/ → Pantallas (Lista, Detalle, Ajustes)
├─ ui/theme/ → Tema Material 3 y tipografía
├─ vm/ → ViewModels de negocio
└─ assets/ → Datos de ejemplo (JSON)

markdown
Copiar código

---

## ⚙️ Tecnologías utilizadas

| Categoría | Librerías / Frameworks |
|------------|------------------------|
| **UI** | Jetpack Compose, Material 3, ConstraintLayout |
| **Navegación** | Navigation Compose |
| **Estado** | ViewModel, Kotlin StateFlow |
| **Persistencia** | DataStore Preferences |
| **Asincronía** | Kotlin Coroutines |
| **Arquitectura** | MVVM con separación clara de capas |
| **Compatibilidad** | Min SDK 24 - Target SDK 35 |
| **Idioma** | Kotlin (100%) |

---

## 🖥️ Funcionalidades principales

### 🗺️ Lista de rutas
- Visualización con `LazyColumn` y `RouteCard`.  
- Filtro de búsqueda instantáneo por nombre.  
- Pestañas: “Todas” / “Favoritas”.  
- Estado vacío con acción **“Crear ruta”**.  

### 🧾 Formulario de detalle
- Campos: **Nombre**, **Distancia**, **Dificultad**, **Apta para niños**, **Favorita**.  
- Validaciones en línea:
  - Nombre mínimo de 3 caracteres.  
  - Distancia > 0 y ≤ 100 km.  
- Botón de **Guardar** deshabilitado si hay errores.  
- Snackbar con mensajes:
  - ✅ “Ruta guardada”.
  - ⚠️ “Revisa los campos”.
  - 🚫 “Distancia demasiado grande”.

### ⚙️ Ajustes
- **Modo oscuro** activable con `Switch`.  
- **Tamaño de fuente** ajustable (S / M / L).  
- Preferencias persistentes con `DataStore`.

### 💬 Accesibilidad y UX
- Iconos con `contentDescription`.  
- Contraste AA y foco visible.  
- Diseño Material 3 limpio, sin sombras pesadas.  
- `ConstraintLayout` en la pantalla de Detalle para un layout preciso.

---

## 🧩 Extras incluidos
- **Splash screen** inicial con transición suave.  
- **Datos de ejemplo** (`sample_routes.json`).  
- **Código totalmente compilable** con Android Studio Giraffe+ (Gradle 8.6 / Kotlin 2.0.20).  
- Preparado para futura integración de:
  - Google Maps Compose.
  - Exportación/Importación de rutas (JSON/CSV).
  - Test unitarios o UI Tests con Compose Testing.

---

## 🚀 Cómo ejecutar el proyecto

1. **Descarga o clona** este repositorio:
   ```bash
   git clone https://github.com/tuusuario/EcorutasApp.git
Abre la carpeta raíz en Android Studio.

Espera a que se sincronicen las dependencias de Gradle.

Ejecuta el proyecto (Shift + F10 o ▶️).

Selecciona un emulador o dispositivo físico con Android 7.0 (API 24) o superior.

🧠 Futuras mejoras
Integración de Google Maps Compose (requiere API key).

Sistema de autenticación de usuario.

Exportación e importación de rutas.

Almacenamiento en base de datos local con Room.

Animaciones avanzadas con MotionLayout.

Tests de UI automáticos con Espresso y Compose Test Framework.

🪪 Licencia
Este proyecto se distribuye bajo la licencia MIT.
Puedes usarlo, modificarlo o distribuirlo libremente, siempre que incluyas el aviso de copyright original.

© 2025 — EcorutasApp
Desarrollado con ❤️ en Kotlin y Jetpack Compose.
