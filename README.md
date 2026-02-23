# Angular Webcam Capture

Este proyecto es una aplicación de Angular (versión 8) diseñada para capturar imágenes desde la cámara web del dispositivo.

## Funcionalidades principales

*   **Acceso a la cámara:** Utiliza la API `navigator.mediaDevices.getUserMedia` para solicitar acceso a la cámara del dispositivo.
*   **Visualización en tiempo real:** Muestra el flujo de video de la cámara en un elemento `<video>`.
*   **Captura de fotos:** Permite al usuario capturar el cuadro actual del video y visualizarlo en un elemento `<canvas>` al presionar el botón "Capture Image".

## Instrucciones para ejecutar el proyecto

Para ejecutar este proyecto localmente, sigue estos pasos:

1.  Instala las dependencias:
    ```bash
    npm install
    ```
2.  Inicia el servidor de desarrollo:
    Si utilizas una versión reciente de Node.js (v17 o superior), es posible que necesites establecer la siguiente variable de entorno para evitar errores de OpenSSL:
    ```bash
    export NODE_OPTIONS=--openssl-legacy-provider
    npm start
    ```
3.  Abre tu navegador en `http://localhost:4200/`.

## Problemas conocidos y observaciones técnicas

Durante el análisis del proyecto se identificaron los siguientes puntos que requieren atención:

*   **Dependencias faltantes:** El archivo `app.component.html` utiliza la directiva `mat-raised-button` de Angular Material, pero `@angular/material` no está instalado ni configurado en el proyecto. Esto causará que el botón no tenga el estilo esperado o genere errores de consola.
*   **Pruebas desactualizadas:** El archivo de pruebas `src/app/app.component.spec.ts` contiene pruebas generadas automáticamente que no reflejan el contenido actual de `app.component.html`, por lo que fallarán al ejecutarse.
*   **Compatibilidad de Node.js:** Debido a que utiliza una versión antigua de Angular y Webpack, el proyecto presenta problemas de compatibilidad con versiones modernas de Node.js, requiriendo el uso de `--openssl-legacy-provider`.
