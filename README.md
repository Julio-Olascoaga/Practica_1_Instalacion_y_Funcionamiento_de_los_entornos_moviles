# Practica_1_Instalacion_y_Funcionamiento_de_los_entornos_moviles

**Alumno:** Julio Cesar Reyes Olascoaga
**Boleta:** 2024630433
**Grupo:** 7CV4


---

## 1. Descripción de Herramientas Instaladas

Para la construcción de aplicaciones móviles nativas y multiplataforma, se configuró el siguiente entorno:
*   **Android Studio:** IDE oficial para el desarrollo en Android. Proporciona el emulador (AVD) y las SDK tools necesarias.
*   **Java Development Kit (JDK):** Distribución Amazon Corretto (OpenJDK) necesaria para compilar y ejecutar código Java.
*   **Maven:** Herramienta para la automatización de la construcción y gestión de dependencias en proyectos.
*   **Git y GitHub:** Sistema de control de versiones y plataforma de alojamiento para gestionar el código fuente del proyecto.
*   **Flutter:** SDK de Google para crear aplicaciones multiplataforma (iOS y Android) desde una sola base de código.
*   **Node.js:** Entorno de ejecución de JavaScript del lado del servidor.
*   **Docker:** Plataforma para desarrollar y ejecutar aplicaciones dentro de contenedores aislados.

---

## 2. Instrucciones del Proceso de Instalación

El proceso en el sistema operativo Windows se llevó a cabo siguiendo estos pasos:
1.  **Instalación base:** Se instalaron mediante ejecutables `.exe` y `.msi` las herramientas Android Studio, Java (Corretto), Git, Node.js y Docker Desktop. 
2.  **Configuración de Variables de Entorno (PATH):** Se descargaron los binarios de Maven y el SDK de Flutter. Para que el sistema los reconociera, se agregaron las rutas exactas de sus respectivas carpetas `\bin` a la variable de entorno `Path` de Windows.
3.  **Configuración de Android Toolchain:** Desde el *SDK Manager* de Android Studio se instaló el paquete *Android SDK Command-line Tools* para permitir la comunicación con Flutter.
4.  **Aceptación de Licencias:** Se ejecutó el comando `flutter doctor --android-licenses` en la terminal para aceptar los términos de desarrollo de Android.

---

## 3. Dificultades Encontradas y Soluciones

Durante el proceso de instalación surgieron dos complicaciones principales con las variables de entorno y las herramientas de línea de comandos:

*   **Problema con el reconocimiento de Maven:** La terminal arrojaba el error `'mvn' is not recognized as an internal or external command`. 
    *   *Solución:* Se verificó que la ruta agregada a las Variables de Entorno apuntara exactamente a la subcarpeta `bin` de la instalación de Maven. Fue necesario cerrar todas las ventanas de la terminal y abrir una nueva sesión para que el sistema actualizara los cambios en el PATH.
*   **Problema con las licencias de Android en Flutter:** Al ejecutar `flutter doctor`, el sistema marcaba `Android license status unknown` y no permitía aceptar las licencias debido a que Flutter no reconocía la estructura de carpetas de la última versión de las *Command-line Tools* de Android.
    *   *Solución:* Se ingresó al *SDK Manager* en Android Studio (marcando *Show Package Details*) para instalar una versión anterior de las herramientas (versión 8.0). Posteriormente, en el explorador de archivos, se eliminó la carpeta `latest` y se renombró la carpeta `8.0` como `latest` dentro de `AppData\Local\Android\Sdk\cmdline-tools`. Esto forzó a Flutter a leer la estructura compatible, permitiendo aceptar las licencias exitosamente.

---

## 4. Evidencias de Instalación (Capturas de Pantalla)

### Verificación de Versiones en Terminal
<img width="1291" height="587" alt="Captura de pantalla 2026-09-03 074341" src="https://github.com/user-attachments/assets/692818c1-067c-4082-8d5b-8372a5a79149" />

### Diagnóstico de Flutter (Flutter Doctor)
<img width="1917" height="382" alt="Captura de pantalla 2026-09-03 074424" src="https://github.com/user-attachments/assets/ee047a93-5e5a-4fae-880f-4bb1b9ace98a" />

### Emulador "Hello Android"
<img width="1917" height="1137" alt="Captura de pantalla 2026-09-03 074542" src="https://github.com/user-attachments/assets/eb6ada34-0fc2-48cd-b36c-72be0c2c49b0" />
| Herramienta | Versión Instalada | Sistema Operativo |
| :--- | :--- | :--- |
| **Sistema Operativo Base** | Windows 11 (25H2) | N/A |
| **Java (JDK)** | Amazon Corretto 25.0.4.1 | Windows 11 |
| **Maven** | Apache Maven 3.9.16 | Windows 11 |
| **Git** | 2.55.0.windows.5 | Windows 11 |
| **Flutter** | 3.47.2 (Channel stable) | Windows 11 |
| **Android SDK** | 37.0.0 | Windows 11 |
| **Node.js** | 24.20.0 | Windows 11 |
| **Docker** | 29.7.2 | Windows 11 |
