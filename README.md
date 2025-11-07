# Proyecto Coterena — Menú Dinámico (Prueba Técnica)

Este proyecto tiene como objetivo desarrollar una página web **dinámica y responsiva** en **PHP + TailwindCSS**, con un **menú principal de hasta tres niveles**, cargado desde un archivo `JSON`.

--- 

## Estructura del Proyecto

coterena/
│
├── public/ # Archivos accesibles desde el navegador
│ ├── index.php # Página principal
│ ├── assets/
│ │ ├── css/ # Estilos CSS compilados o estáticos
│ │ ├── js/ # Scripts JavaScript
│ │ ├── data/ # Archivos JSON (menú y otros datos)
│ │ └── images/ # Imágenes y favicon
│ └── favicon.png
│
├── src/ # Lógica del lado del servidor
│ ├── includes/ # Archivos incluidos (header, footer, etc.)
│ └── functions/ # Funciones PHP reutilizables
│
└── README.md # Documentación del proyecto


---

## Reglas de Desarrollo

1. **Estructura Modular:**  
   - `includes/` → fragmentos de página (header, footer)  
   - `functions/` → funciones auxiliares o lógicas del menú  

2. **Menú Dinámico:**  
   - Se carga desde `public/assets/data/menu.json`.  
   - Debe admitir hasta **tres niveles** de profundidad.  
   - El menú debe ser **totalmente responsivo**.

3. **Tecnologías Base:**  
   - **PHP 8+** → para la estructura modular.  
   - **TailwindCSS (vía CDN o compilado)** → para el diseño responsivo.  
   - **Headless UI** → como framework complementario de Tailwind, utilizado para el menú desplegable.  
   - **HTML5 + JavaScript nativo** → para la estructura semántica y las interacciones básicas.  
   - **JSON** → fuente de datos externa que contiene los elementos del menú.  


5. **Ejecución local:**  
   Desde la raíz del proyecto, ejecutar:  
   ```bash
   php -S localhost:8000 -t public
