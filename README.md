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

## 5. Tabla de versiones de herramientas
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

## 6. Versión 1: Android nativo con Views (XML)
Aplicación nativa basada en un esquema tradicional de separación de responsabilidades, utilizando un `ConstraintLayout` y múltiples componentes `TextView` para estructurar la interfaz visual.
### Ejecución de la Versión 1 (XML + Kotlin)
1. Abrir Android Studio y seleccionar **New Project** -> **Empty Views Activity**.
2. Asignar el nombre del proyecto, verificar que el lenguaje seleccionado sea **Kotlin** y hacer clic en **Finish**.
3. Navegar al archivo de diseño ubicado en `app/src/main/res/layout/activity_main.xml`.
4. Cambiar a la vista de código (**Code**) y estructurar los elementos visuales utilizando un `ConstraintLayout` con los `TextView` requeridos.
5. Seleccionar el emulador configurado en la barra superior y hacer clic en el botón **Run 'app'** (ícono de reproducción verde).
<img width="1917" height="1138" alt="Captura de pantalla 2026-09-03 104008" src="https://github.com/user-attachments/assets/87b45eaa-ad54-47aa-a431-3a5811274858" />

## 7. Versión 2: Android nativo con Jetpack Compose
Aplicación nativa basada en un paradigma declarativo, empleando funciones `@Composable` y modificadores de estilo directamente en código Kotlin para renderizar los elementos visuales.
### Ejecución de la Versión 2 (Jetpack Compose)
1. En Android Studio, crear un nuevo proyecto seleccionando **File > New > New Project** -> **Empty Activity** (con el logotipo de Jetpack Compose).
2. Abrir el archivo `app/src/main/java/.../MainActivity.kt`.
3. Implementar una función con la anotación `@Composable` que organice los componentes `Text` dentro de un contenedor `Column`, aplicando modificadores de diseño (`padding`, tipografía y color).
4. Validar el diseño en tiempo de diseño utilizando la anotación `@Preview`.
5. Ejecutar la aplicación en el emulador mediante el botón **Run** del IDE.
<img width="1732" height="1081" alt="image" src="https://github.com/user-attachments/assets/7e48263a-397b-48ef-9980-47f86bb9a54a" />

## 8. Versión 3: Flutter
Aplicación multiplataforma estructurada mediante un árbol de widgets nativos (`MaterialApp`, `Scaffold`, `Column` y `Text`) ejecutándose sobre el motor de renderizado de Flutter.
### Ejecución de la Versión 3 (Flutter)
1. Abrir la terminal del sistema (o la integrada en Android Studio) y generar el proyecto ejecutando:
   ```bash
   flutter create hola_mundo_flutter
   cd hola_mundo_flutter
2. Abrir el archivo lib/main.dart en un editor de código, eliminar el contenido predeterminado e implementar el árbol de widgets utilizando MaterialApp, Scaffold, Column y Text.
3. Asegurar que el emulador de Android se encuentre activo y en ejecución.
4. Compilar y desplegar la aplicación ejecutando en la terminal: flutter run
<img width="1917" height="1135" alt="image" src="https://github.com/user-attachments/assets/a31cb269-cc66-406d-8b8f-e91f4d365324" />

## 8. Conclusiones y hallazgos
El desarrollo de esta práctica permitió contrastar de manera directa tres enfoques tecnológicos fundamentales en la ingeniería de software móvil actual.

En primer lugar, el modelo tradicional de Android Views con XML evidencia el paradigma imperativo clásico, donde el código de la interfaz gráfica y la lógica de control se encuentran estrictamente desacoplados en archivos separados. Si bien ofrece un control preciso sobre la jerarquía de vistas mediante contenedores como ConstraintLayout, su gestión resulta más verbosa para interfaces sencillas.

Por otro lado, Jetpack Compose representa un cambio radical hacia el paradigma declarativo en el ecosistema nativo de Android. Al prescindir de los archivos XML y concentrar la estructura visual en funciones de orden superior (@Composable), se reduce drásticamente la cantidad de código necesario y se simplifica la aplicación de estilos mediante modificadores encadenados, mejorando la legibilidad y la productividad del desarrollador.

Finalmente, el enfoque multiplataforma con Flutter demuestra la versatilidad de utilizar un único código fuente basado en un árbol de widgets homogéneo para desplegar aplicaciones consistentes. A diferencia del desarrollo nativo, la abstracción que provee Dart desacopla la interfaz del sistema operativo subyacente, aunque esto introduce una mayor complejidad inicial en la configuración del entorno de compilación, gestión de dependencias nativas (como el SDK y el NDK) y configuración de emuladores.

En conclusión, la elección entre estos enfoques depende de los requerimientos del proyecto: el desarrollo nativo con Compose optimiza el rendimiento y la integración profunda con el sistema operativo, mientras que Flutter prioriza la portabilidad y la unificación del ciclo de desarrollo multiplataforma.
