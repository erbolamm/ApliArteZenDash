# 🗺️ Plan de Mejoras: ApliArte ZenDash

Hoja de ruta detallada para escalar el proyecto de un script HTA personal a una herramienta Open Source profesional y dinámica.

## 📍 Fase 1: El Optimizador Dinámico (Actual - Prioridad Máxima)
*Objetivo: Que el "Modo Streaming" reconozca el entorno en tiempo real y sea 100% interactivo.*
- **Escaneo Inteligente en Vivo:** Reemplazar la lista fija de procesos por un escaneo en tiempo real (usando `Get-Process` encapsulado) que detecte aplicaciones de terceros activas.
- **Interfaz de Selección Dinámica:** Generar dinámicamente una vista dentro del HTA con casillas de verificación (checkboxes) para que el usuario pueda marcar/desmarcar qué procesos cerrar en ese momento.
- **Pre-selección Inteligente:** Marcar por defecto las apps conocidas por consumir recursos de red o RAM (Dropbox, navegadores sin sesión activa, etc.) y proteger servicios elementales u OBS.
- **Acción Diferida:** Un botón final de "Cerrar seleccionados" que aplique la magia y recálculo de RAM.

## 📍 Fase 2: Seguridad y Profilaxis Open Source (Corto Plazo)
*Objetivo: Asegurar que el código sea seguro para publicarse y no contenga rastros personales de prueba.*
- **Rutas y Variables Dinámicas:** Asegurar que los scripts no apunten a cuentas de usuario hardcodeadas, sino a constructos universales (`%USERPROFILE%`, `%TEMP%`).
- **Limpieza de Repositorio:** Retirar iteraciones previas como `contexto.txt` o la plantilla web de `docs` sin uso para que el repositorio quede impoluto (`/src`, `/docs`, `README.md`).
- **Separar Contexto Local de Público:** Extraer información específica del setup personal para usarlo como ejemplo teórico en la documentación.

## 📍 Fase 3: Feedback y Experiencia de Usuario UX (Medio Plazo)
*Objetivo: Elevar un script útil a una herramienta de la que los usuarios se enamoren.*
- **Ventanas Modales o Vistas Deslizantes:** En vez de un solo panel, crear sub-vistas fluidas para las confirmaciones de limpieza de DNS y cierre selectivo.
- **Indicadores de Carga In-App:** Al lanzar los comandos PowerShell (que a veces tardan décimas de segundo o segundos), presentar animaciones de "Escaneando entorno..." o spinners.
- **Logs y Reportes Visuales:** Al acabar, en lugar del texto fijo inferior, mostrar una ventanita de qué se cerró y exactamente cuánta RAM se liberó en esa ejecución.

## 📍 Fase 4: Persistencia y Settings de Usuario (Largo Plazo)
*Objetivo: Que el software se adapte y aprenda de su dueño de forma silenciosa.*
- **Almacenamiento Local de Preferencias:** Crear un archivo `zendash_config.json` adyacente para recordar el estado "marcado/desmarcado" de los procesos del usuario que hace streaming a menudo. Todo será a capricho en base a su última elección.
- **Modos Agrupados:** Permitir añadir nuevos perfiles (no solo Streaming/Gaming, sino "Ofimática Extrema", etc.).
- **Regeneración de Memoria Automática (`[GC]::Collect()` programado):** Ejecutar mini-procesos programados por detrás cada X horas.

## 📍 Fase 5: Transparencia y Salto Tecnológico (Futuro)
*Objetivo: Superar las estrictas limitaciones técnicas del motor MSHTML de los HTA convencionales.*
- **Migración Arquitectónica:** Cuando el proyecto gane estrellas en GitHub, portar la lógica a capas modernas como *Tauri* (que pesa poquísimos MB) o *Electron/C# WinForms*. 
- **Ventajas:** Esto dará acceso a una interactividad del 2026 nativa, renderizado con motor WebKit/Blink (permitiendo transiciones de hardware fluidas) y total compatibilidad libre de la temida alerta eventual de Windows Defender al ejecutar macros HTA no firmadas.
