# Proyecto Menú Dinámico (Prueba Técnica)
**Versión:** `v2.0.0` — *Entrega final evaluable*
https://github.com/lbettero/responsivemenu

Este proyecto implementa una **página web dinámica, modular y responsiva** desarrollada en **PHP + TailwindCSS**, con un **menú principal de hasta tres niveles** cargado automáticamente desde un archivo `JSON`.  
Se incluyen pruebas unitarias en **PHPUnit**, scripts JavaScript separados y documentación completa para su ejecución y mantenimiento.

---

## Requisitos para el Desarrollo de una Web Simple con Menú Dinámico

### 1. Estructura del Menú
- El menú debe ser **responsivo**, adaptándose correctamente a diferentes tamaños de pantalla.  
- Puede tener **hasta tres niveles de profundidad**:  
  **Padre → Hijo → Nieto**.  
- El menú se **genera automáticamente** cargando su estructura desde un archivo **JSON**.

### 2. Contenido Mínimo del Menú
- Al menos **10 categorías padre**.  
- Por lo menos **una categoría padre sin hijos**.  
- Las demás deben tener una media de **6 hijos**.  
- Aproximadamente **20 % de los hijos** deben tener nietos.

### 3. Buscador
- Debe existir un **buscador** que filtre, oculte o destaque las opciones del menú que coincidan con el patrón de búsqueda.  
- El filtro debe considerar coincidencias por:
  - **Nombre del menú**, y/o  
  - **Etiqueta interna (tag)** definida en el JSON.  
- Si se encuentra una coincidencia en un nivel inferior (hijo o nieto), se deben mostrar también sus **ancestros** para mantener el contexto visual.

### 4. Interacción y Usabilidad
- El menú debe poder **plegarse y expandirse**, optimizando el uso del espacio.  
- Junto al menú se incluye una **página principal o dashboard** con varios **botones de interacción (al menos tres)**.  
- Cada botón debe **filtrar, resaltar o recolocar** ciertas opciones del menú.  
- Debe existir una opción para **volver al estado original** del menú.

---

## Requisitos Técnicos

### 1. Tecnología Base
- No se busca desarrollar el menú completamente desde cero.  
- Se debe seleccionar una **tecnología o framework base** y extenderla con código propio.  
- Si la tecnología elegida cumple todos los requisitos, puede usarse directamente.

### 2. Opciones Posibles
- Renderizado desde el **backend** (por ejemplo, con **PHP** o **Python**).  
- Desarrollo completo en el **frontend** (HTML, CSS, JavaScript).  
- Frameworks o bibliotecas sugeridas (no obligatorias):
  - [AdminLTE](https://adminlte.io/)
  - [Tabler](https://tabler.io/)
  - [BootstrapMade](https://bootstrapmade.com/)
  - O cualquier solución moderna basada en **React**, **Vue**, etc.

### 3. Estructura y Entrega
- Entregar el proyecto en un **archivo comprimido (.zip)**.  
- Incluir un archivo **README.md** o un **video** con:
  - Breve descripción del proyecto.  
  - Tecnología o framework elegidos y **motivo de la elección**.  
  - Instrucciones para ejecutar la prueba.  
  - Qué parte del trabajo proviene del framework base y **qué se ha implementado manualmente**.

---

## Estructura del Proyecto

```
RESPONSIVEMENU/
│
├── public/
│   ├── assets/
│   │   ├── css/
│   │   │   └── main.css            # Estilos principales personalizados
│   │   ├── data/
│   │   │   └── menu.json           # Datos estructurados del menú
│   │   ├── img/                    # Íconos y recursos gráficos
│   │   └── js/
│   │       ├── dashboard.js        # Controla el dashboard y sus eventos
│   │       └── menu.js             # Controla la interacción del menú dinámico
│   │
│   ├── index.php                   # Página principal del sitio
│   ├── test-report.html            # Reporte visual de PHPUnit
│   ├── test-report.txt             # Resumen de resultados de pruebas
│   └── .htaccess                   # (Vacío) — sin configuración adicional
│
├── src/
│   ├── functions/
│   │   └── menu.php                # Lógica PHP para cargar y renderizar el menú
│   └── includes/
│       ├── header.php              # Encabezado HTML (meta, scripts, estilos)
│       └── footer.php              # Pie de página HTML
│
├── tests/
│   ├── MenuTest.php                # Pruebas de las funciones PHP del menú
│   └── DashboardScriptTest.php     # Pruebas de integración JS y HTML
│
├── vendor/                         # Dependencias gestionadas por Composer
│
├── composer.json                   # Configuración de dependencias
├── composer.lock                   # Versión bloqueada de dependencias
├── phpunit.xml                     # Configuración de PHPUnit
├── .phpunit.result.cache           # Cache interna de resultados
└── README.md                       # Este archivo
```

---

## Motivo de la Elección Tecnológica

- **PHP 8+** → Permite renderizar HTML dinámico desde el servidor con estructura modular.  
- **TailwindCSS** → Framework CSS moderno y ligero, ideal para interfaces responsivas.  
- **Alpine.js** → Añade interactividad reactiva sin frameworks complejos.  
- **JavaScript nativo** → Control directo sobre los eventos del menú y el dashboard.  
- **JSON** → Facilita la actualización del menú sin modificar el código fuente.

---

## Partes Implementadas Manualmente

| Componente | Implementación manual |
|-------------|----------------------|
| `menu.php` | Lógica PHP para cargar, validar y renderizar el menú dinámico (hasta 3 niveles). |
| `menu.js` | Control de apertura/cierre del menú, comportamiento móvil y desktop. |
| `dashboard.js` | Envío y escucha de eventos personalizados (`menu:filter`, `menu:reset`). |
| `main.css` | Personalización de colores, tipografía y ajustes responsivos. |
| `header.php` / `footer.php` | Plantillas modulares HTML. |
| `MenuTest.php` / `DashboardScriptTest.php` | Pruebas unitarias PHP y JS con PHPUnit. |

---

## Instrucciones para Ejecutar la Prueba

1. **Clonar o descomprimir** el proyecto en tu entorno local.  
2. Acceder al directorio raíz del proyecto:  
   ```bash
   cd RESPONSIVEMENU
   ```
3. **Iniciar un servidor local de PHP**:  
   ```bash
   php -S localhost:8000 -t public
   ```
4. Abrir el navegador y acceder a:  
   [http://localhost:8000](http://localhost:8000)

---

## Ejecución de Pruebas Unitarias

El proyecto incluye un conjunto de pruebas desarrollado con **PHPUnit**, que verifica la validez del JSON, la generación del HTML del menú y la integración de los scripts del dashboard.

Ejecutar las pruebas desde la raíz del proyecto:

```bash
vendor/bin/phpunit --testdox --colors=always tests/
```

Esto generará los siguientes reportes:
- **`public/test-report.txt`** → resumen plano.  
- **`public/test-report.html`** → reporte visual con resultados detallados.  

---

## Estado del Proyecto

**Versión actual:** `v2.0.0`  
**Estado:** Entrega final lista para evaluación  

Incluye:
- Menú dinámico completamente funcional.  
- Interfaz moderna y responsiva.  
- Integración con dashboard interactivo.  
- Sistema de pruebas unitarias funcional.  
- Reportes de test automáticos en HTML y texto.  
- Documentación completa en este `README.md`.

---

## Historial de Versiones

| Versión | Fecha | Descripción |
|----------|--------|-------------|
| **v2.0.0** | 10 de noviembre de 2025 | Incorporación del **dashboard interactivo** con eventos personalizados (`menu:filter`, `menu:reset`) y comunicación bidireccional con el menú. Se integró **Alpine.js** para el control de estado reactivo (apertura, cierre y transiciones del menú), mejorando la **usabilidad móvil** y la experiencia general de usuario. Se añadieron pruebas unitarias específicas para `dashboard.js` e integración con `index.php`. |
| **v1.0.1** | 8 de noviembre de 2025 | Versión estable del **menú dinámico** con carga desde `menu.json`, renderizado recursivo en PHP, estructura modular (`includes/`, `functions/`) y pruebas unitarias con PHPUnit. |
| **v1.0.0** | 8 de noviembre de 2025 | Versión inicial funcional del proyecto con **TailwindCSS**, diseño **responsivo**, y generación dinámica del menú a partir de `menu.json`. Base técnica y estructura general del sistema. |

---

## Registro de Tiempo de Desarrollo

| Fecha | Duración | Descripción de la jornada |
|--------|-----------|---------------------------|
| **08/11/2025** | 6 horas | Implementación del menú dinámico, configuración inicial de TailwindCSS, pruebas PHP y validación JSON. |
| **09/11/2025** | 4 horas | Refinamiento de interactividad, estructura modular y pruebas unitarias. |
| **10/11/2025** | 2 horas | Integración del dashboard, Alpine.js y eventos personalizados (`menu:filter`, `menu:reset`). Preparación del README final y validaciones previas al envío. |
| **⏳ Total acumulado** | **≈ 12 horas** | Tiempo total efectivo de desarrollo hasta la versión `v2.0.0` (pausas excluidas). |

---

**Autora:** Livia Pérez Bettero  
**Colaboración técnica:** ChatGPT (OpenAI)  
