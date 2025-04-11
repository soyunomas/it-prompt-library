# 📚 IT Prompt Library

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Demo - Ver Librería](https://img.shields.io/badge/Demo-Ver_Librería-brightgreen)](https://soyunomas.github.io/it-prompt-library/index.html)

Una colección curada de System Prompts diseñados para ayudar a profesionales de TI en diversas tareas y roles. 🤖

## 📝 Descripción Breve

Este proyecto proporciona una interfaz web sencilla para explorar, visualizar y copiar rápidamente prompts de sistema optimizados para diferentes roles (Desarrollo Frontend, Backend, DevOps, etc.) y habilidades (Python, SQL, React, etc.) dentro del sector IT. El objetivo es tener un acceso centralizado y fácil a prompts efectivos para interactuar con modelos de IA.

## 🖼️ Captura de Pantalla / Demo

![Captura de Pantalla del Proyecto](screenshot.png) <!-- Reemplaza con tu captura -->

Puedes probar la demo en vivo aquí:

*   **[Demo - Ver Librería](https://soyunomas.github.io/it-prompt-library/index.html)**

## ✨ Características Principales

*   **🗂️ Categorización Clara:** Prompts organizados por "Roles" y "Habilidades" para una fácil navegación.
*   **🔍 Búsqueda Integrada:** Filtra rápidamente las tarjetas buscando texto en los títulos *o dentro* del contenido de los prompts.
*   **🖱️ Interfaz Intuitiva:** Tarjetas clicables con un diseño limpio basado en Bootstrap.
*   **👁️ Visualización Detallada:** Al hacer clic, se muestra el prompt completo en un modal claro y legible (con formato de código).
*   **📋 Copiado Fácil:** Botón "Copiar Prompt" en cada modal para usar el texto inmediatamente.
*   **📱 Diseño Responsivo:** Interfaz adaptable a diferentes tamaños de pantalla (escritorio, tablet, móvil).
*   **🎨 Tema Oscuro:** Estilo visual moderno y agradable a la vista.
*   **🧩 Código Autónomo:** Todo en un solo archivo HTML con CSS y JavaScript incrustados para simplicidad.
*   **🔧 Fácilmente Extensible:** Añadir nuevos prompts es tan simple como editar el objeto JavaScript y añadir una tarjeta HTML.

## 🛠️ Tecnologías Utilizadas

*   **HTML5:** Estructura semántica del contenido.
*   **CSS3:** Estilos personalizados para tarjetas, modal y tema oscuro.
*   **Bootstrap 5.3.x:** Framework CSS/JS utilizado para layout responsivo, componentes (modal, grid, formularios) y utilidades.
*   **Bootstrap Icons:** Para iconografía (ej., icono de copiar).
*   **JavaScript (ES6+):** Lógica de la aplicación, manipulación del DOM, gestión de eventos (clics, búsqueda), funcionalidad de copiado al portapapeles (`navigator.clipboard`).
*   **CDNs:** Bootstrap (CSS y JS) se carga desde CDNs para simplificar.

## 🚀 Instalación / Visualización Local

Este proyecto es una aplicación web estática del lado del cliente. Para ejecutarla localmente:

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/soyunomas/it-prompt-library.git
    ```
2.  **Navega al directorio del proyecto:**
    ```bash
    cd it-prompt-library
    ```
3.  **Abre el archivo HTML principal:**
    *   Abre el archivo `index.html` (o como lo hayas llamado) directamente en tu navegador web preferido (Chrome, Firefox, Edge, etc.).
4.  **🌐 Conexión a Internet:** Es necesaria para cargar Bootstrap (CSS y JS) y Bootstrap Icons desde sus respectivos CDNs.
5.  **(Sin Dependencias Adicionales):** No se requiere instalación de software adicional, servidores locales ni configuraciones complejas.

## 🕹️ Cómo Usar

1.  **Explorar:** Navega visualmente por las tarjetas organizadas en las secciones "Basado en Roles" y "Basado en Habilidades".
2.  **Buscar:** Utiliza la barra de búsqueda en la parte superior para filtrar las tarjetas. Escribe palabras clave que puedan estar en el título del rol/habilidad o dentro del texto del prompt mismo. Las tarjetas que no coincidan se ocultarán dinámicamente.
3.  **Seleccionar:** Haz clic en la tarjeta del rol o habilidad cuyo prompt te interese.
4.  **Visualizar:** Se abrirá una ventana modal mostrando el título y el texto completo del System Prompt seleccionado, formateado para facilitar la lectura.
5.  **Copiar:** Dentro del modal, haz clic en el botón "<i class="bi bi-clipboard"></i> Copiar Prompt". El texto completo del prompt se copiará a tu portapapeles, listo para pegarlo donde lo necesites. Recibirás una confirmación visual en el botón ("¡Copiado!").
6.  **Cerrar:** Cierra el modal haciendo clic en el botón "Cerrar" o en la 'X' de la esquina superior derecha.

## ✏️ Cómo Añadir un Nuevo Prompt

Añadir un nuevo prompt a la librería es un proceso sencillo que requiere modificar dos partes del archivo `index.html` (o como lo hayas llamado):

1.  **Añadir los Datos del Prompt al Objeto JavaScript:**
    *   Localiza el objeto `systemPrompts` dentro de la etiqueta `<script>` al final del archivo HTML.
    *   Añade una nueva entrada clave-valor a este objeto. La **clave** será el identificador único del prompt (usa minúsculas y guiones, ej., `nuevo-rol-id`). El **valor** será otro objeto con dos propiedades:
        *   `title`: El texto que aparecerá en la tarjeta (ej., `"Título del Nuevo Prompt"`).
        *   `prompt`: El texto completo del System Prompt. Usa backticks (\`) si tu prompt ocupa varias líneas para facilitar la lectura y mantener el formato.

    *   **Ejemplo de nueva entrada:**
        ```javascript
        // Dentro del objeto systemPrompts...
        "nuevo-rol-id": {
            title: "Título del Nuevo Prompt",
            prompt: `Este es el texto completo
        del nuevo system prompt que quiero añadir.

        Puede tener múltiples párrafos y **formato markdown básico** si lo deseas,
        aunque se mostrará como texto plano en el modal <pre>.`
        },
        // Asegúrate de añadir una coma después del objeto anterior si no es el último
        ```

2.  **Añadir la Tarjeta HTML Correspondiente:**
    *   Decide en qué sección quieres que aparezca la tarjeta ("Basado en Roles" o "Basado en Habilidades").
    *   Localiza el `div.row` dentro de la `<section>` elegida.
    *   Añade un nuevo elemento `div.col` que contenga un `div.prompt-card`.
    *   Dentro del `div.prompt-card`, asegúrate de:
        *   Establecer el atributo `data-prompt-id` para que coincida **exactamente** con la clave que usaste en el objeto JavaScript (ej., `data-prompt-id="nuevo-rol-id"`).
        *   Incluir los atributos `data-bs-toggle="modal"` y `data-bs-target="#promptModal"` para que la tarjeta abra el modal.
        *   Poner el título visible dentro de una etiqueta `<h5>` (ej., `<h5>Título del Nuevo Prompt</h5>`).

    *   **Ejemplo de nueva tarjeta HTML:**
        ```html
        <!-- Dentro del div.row de la sección deseada -->
        <div class="col">
            <div class="prompt-card" data-prompt-id="nuevo-rol-id" data-bs-toggle="modal" data-bs-target="#promptModal">
                <h5>Título del Nuevo Prompt</h5>
            </div>
        </div>
        ```

3.  **Guardar y Probar:** Guarda el archivo HTML y actualiza la página en tu navegador. La nueva tarjeta debería aparecer en la sección correcta y, al hacer clic, mostrar el prompt que añadiste en el objeto JavaScript. La funcionalidad de búsqueda y copia debería funcionar automáticamente para el nuevo prompt.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT.
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🧑‍💻 Contacto

Creado por **soyunomas** ([@soyunomas en GitHub](https://github.com/soyunomas))

---
