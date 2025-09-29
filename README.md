# Portafolio Web - Yomar Echavarría (YAEC)

Este es un portafolio web personal, diseñado como una **Single Page Application (SPA)** moderna y responsiva. El proyecto muestra información profesional, habilidades y proyectos destacados a través de una interfaz interactiva y fluida que no requiere recargar la página para navegar entre secciones.

## ✨ Características Principales

- **Diseño Responsivo**: La interfaz se adapta perfectamente a dispositivos de escritorio, tabletas y móviles.
- **Tema Dual (Claro/Oscuro)**: Permite al usuario elegir entre un tema claro y uno oscuro, guardando su preferencia para futuras visitas.
- **Navegación Avanzada**: Navegación entre secciones mediante:
  - Clics en el menú lateral.
  - Botones de navegación (arriba/abajo).
  - Scroll de la rueda del ratón al llegar al límite de una sección.
- **Progressive Web App (PWA)**: El sitio puede ser "instalado" en la pantalla de inicio de un dispositivo y tiene capacidad para funcionar sin conexión gracias a un Service Worker.
- **Generación de Código QR**: Genera dinámicamente un código QR con la URL actual para compartir fácilmente.
- **API de Compartir Nativa**: Utiliza la Web Share API para una experiencia de compartición fluida en dispositivos compatibles.
- **Pantalla de Carga Animada**: Mejora la experiencia de usuario inicial con un loader interactivo.

## 🚀 Tecnologías Utilizadas

Este proyecto fue construido utilizando tecnologías web estándar y un conjunto de librerías modernas para lograr una alta interactividad y un diseño profesional.

### Frameworks y Librerías Principales

- **[Bootstrap 5.3.3](https://getbootstrap.com/)**: Framework principal para el diseño de la interfaz, el sistema de rejilla, los componentes (Navbar, Cards, Offcanvas) y las clases de utilidad.
- **[Bootstrap Icons 1.11.3](https://icons.getbootstrap.com/)**: Librería de iconos SVG utilizada en toda la aplicación.
- **[qrcode.js](https://github.com/davidshimjs/qrcodejs)**: Librería de JavaScript para generar los códigos QR de forma dinámica en el cliente.

### Lenguajes y Estándares

- **HTML5**: Para la estructura semántica del contenido.
- **CSS3**: Para la personalización de estilos, incluyendo:
  - **Variables CSS (Custom Properties)** para una tematización flexible (`--resaltador`, `--app-border`).
  - **Flexbox** para la maquetación principal.
  - **Selectores de Atributo** (`[data-bs-theme]`) para gestionar los estilos de los temas.
- **JavaScript (ES6+)**: Para toda la lógica de interactividad, manejo de eventos y manipulación del DOM.

## 🏛️ Arquitectura y Conceptos Clave

### 1. Single Page Application (SPA)
La aplicación carga un único archivo `index.html` y el contenido de las diferentes secciones (`Sobre mí`, `Proyectos`, etc.) se muestra u oculta dinámicamente con JavaScript, sin necesidad de solicitar nuevas páginas al servidor.

### 2. Sistema de Navegación por Pestañas (Tabs)
La navegación se basa en el componente **Tab de Bootstrap**. El contenido de cada sección está encapsulado en un `tab-pane`. La lógica de JavaScript personalizada extiende esta funcionalidad para permitir la navegación mediante botones y el scroll del ratón.

### 3. Diseño Responsivo Adaptativo
La arquitectura del layout cambia según el tamaño de la pantalla:
- **Desktop**: Un diseño de tres columnas con barras laterales fijas para un acceso rápido a la información y la navegación.
- **Móvil**: Las barras laterales se ocultan y se convierten en menús deslizables **(Offcanvas)** para optimizar el espacio. Se añaden botones flotantes (FABs) para un acceso rápido a la navegación.

### 4. Interactividad Personalizada con JavaScript
- **Navegación por Scroll**: Un script detecta si el usuario ha llegado al final o al principio del contenido de una tarjeta. Si el usuario continúa haciendo scroll, se activa la transición a la siguiente o anterior pestaña, creando una experiencia inmersiva.
- **Gestor de Temas**: Un script gestiona el cambio entre los modos claro y oscuro, aplicando el atributo `data-bs-theme` al `<html>` y guardando la preferencia del usuario en `localStorage`.
- **Integración de APIs Web**: Se utilizan APIs modernas del navegador como:
  - **Web Share API (`navigator.share`)**: Para invocar el diálogo de compartir nativo del sistema operativo.
  - **Clipboard API (`navigator.clipboard`)**: Como alternativa para copiar la URL si la Web Share API no está disponible.

### 5. Progressive Web App (PWA)
La inclusión de un **`manifest.json`** y el registro de un **Service Worker (`sw.js`)** le otorgan capacidades de PWA, lo que permite que el sitio sea instalable y ofrezca una experiencia más similar a la de una aplicación nativa.

## 🛠️ Instalación y Uso Local

Este es un proyecto web estático, por lo que no requiere un proceso de compilación ni dependencias complejas.

1.  **Clona o descarga el repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/tu-repositorio.git](https://github.com/tu-usuario/tu-repositorio.git)
    cd tu-repositorio
    ```

2.  **Abre el proyecto:**
    - **Opción A: Directamente en el navegador**
      Puedes abrir el archivo `index.html` directamente en tu navegador web.
    - **Opción B: Usando un servidor local (Recomendado)**
      Para un funcionamiento óptimo (especialmente para el Service Worker), es mejor servir los archivos a través de un servidor local. Si tienes Python instalado, puedes usar este comando en la carpeta del proyecto:
      ```bash
      # Para Python 3
      python -m http.server
      ```
      Luego, abre tu navegador y ve a `http://localhost:8000`.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
