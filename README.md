# SGAF - Sistema de Gestión y Autogestión Fronteriza 

Este repositorio contiene el prototipo funcional frontend del **Sistema de Gestión y Autogestión Fronteriza (SGAF)**, desarrollado para agilizar y digitalizar los procesos de control en el Paso Los Libertadores (Aduanas, PDI, SAG).

##  Descripción del Proyecto

El prototipo consiste en un Formulario Digital Previo de Ingreso que permite a los viajeros registrar sus datos, los de sus acompañantes y su vehículo antes de llegar al paso fronterizo. El sistema valida la información y genera un **Pase de Frontera QR** para optimizar los tiempos de aforo.

##  Stack Tecnológico

Al tratarse de un prototipo de alta fidelidad orientado al rendimiento y la accesibilidad, se utilizó el siguiente stack sin dependencias pesadas de servidor:
* **HTML5 Semántico:** Estructuración de datos y formularios.
* **Tailwind CSS:** Maquetación ágil, diseño responsivo y cumplimiento de la normativa gráfica institucional (colores Aduanas de Chile).
* **JavaScript (Vanilla):** Lógica de negocio, validaciones matemáticas y manipulación del DOM.
* **QRCode.js:** Librería ligera para la renderización del código QR del pase fronterizo.

##  Funcionalidades y Reglas de Negocio (RF)

* **Validación de Identidad:** Verificación matemática del RUT chileno (Módulo 11) en tiempo real.
* **Control de Edad:** Restricción normativa que impide a menores de 18 años ser titulares de la declaración jurada.
* **Simulación de Interoperabilidad:** * Alerta de bloqueo por restricciones de tránsito (PDI) simulada con el RUT de prueba `1-9`.
    * Alerta de control fitosanitario obligatorio (SAG) al declarar mascotas.
* **Generación de Pase QR:** Emisión descargable con la data del viajero para lectura láser rápida.

##  Calidad de Software y Accesibilidad (ISO 25000 / 9126)

Este desarrollo aplicó estándares de calidad de software enfocados en la **Usabilidad** y **Fiabilidad**:
* **Accesibilidad Universal (WCAG):** Implementación de atributos `aria-live`, `aria-hidden` y vinculación programática de etiquetas (`<label for="...">`) para compatibilidad total con lectores de pantalla.
* **Modo Oscuro (Dark Mode):** Interfaz adaptable para reducir la fatiga visual, manteniendo el contraste institucional y asegurando que el contenedor del código QR mantenga fondo blanco para evitar fallas en los escáneres láser.

##  Estrategia de Control de Versiones (Git Flow)

El ciclo de vida de este prototipo siguió una estrategia de ramificación iterativa:
* `main`: Rama principal con versiones estables y liberadas (v0.1.0 hasta v1.0.0).
* `release/dev`: Rama paralela para el desarrollo continuo de nuevas funcionalidades (accesibilidad, validaciones matemáticas).
* `hotfix-filtros`: Rama de emergencia utilizada para aislar y corregir un error crítico de renderizado (solapamiento en el Canvas del QR), integrada rápidamente a `main` para asegurar la estabilidad del sistema.

---
*Desarrollado para la Evaluación Parcial 3 - Prototipo funcional y prueba estándar de calidad.*
