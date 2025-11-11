# Proyecto Menú Dinámico (Prueba Técnica)
**Versión:** `v2.1.0` — *Revisión estructural y corrección de despliegue*  
https://github.com/lbettero/responsivemenu  

Este proyecto implementa una **página web dinámica, modular y responsiva** desarrollada en **PHP + TailwindCSS**, con un **menú principal de hasta tres niveles** cargado automáticamente desde un archivo `JSON`.  
Se incluyen pruebas unitarias en **PHPUnit**, scripts JavaScript separados y documentación completa para su ejecución y mantenimiento.  

---

## 🔧 Cambios de la versión 2.1.0

- **Eliminación de la carpeta duplicada `public/`**: ahora los archivos se sirven directamente desde la raíz del proyecto.  
- **Corrección de contexto de apilamiento (z-index)** en `menu.php`, `header.php` y `main.css`, asegurando que los submenús se muestren correctamente en primer plano.  
- **Refactorización de rutas relativas** en `require` y `assets` para ajustarse a la nueva estructura sin `public/`.   
- **Ajustes visuales en `header.php` para compatibilidad con Alpine.js y TailwindCSS.  

---

## 📁 Nueva Estructura del Proyecto

```
RESPONSIVEMENU/
│
├── assets/
│   ├── css/
│   │   └── main.css              # Estilos principales personalizados (ajustado)
│   ├── data/
│   │   └── menu.json             # Datos estructurados del menú
│   ├── img/                      # Íconos y recursos gráficos
│   └── js/
│       ├── dashboard.js          # Controla el dashboard y sus eventos
│       └── menu.js               # Controla la interacción del menú dinámico
│
├── src/
│   ├── functions/
│   │   └── menu.php              # Lógica PHP para cargar y renderizar el menú
│   └── includes/
│       ├── header.php            # Encabezado HTML (meta, scripts, estilos)
│       └── footer.php            # Pie de página HTML
│
├── tests/
│   ├── MenuTest.php              # Pruebas de las funciones PHP del menú
│   └── DashboardScriptTest.php   # Pruebas de integración JS y HTML
│
├── index.php                     # Página principal del sitio (punto de entrada)
├── test-report.html              # Reporte visual de PHPUnit
├── test-report.txt               # Resumen de resultados de pruebas
├── composer.json                 # Configuración de dependencias
├── composer.lock                 # Versión bloqueada de dependencias
├── phpunit.xml                   # Configuración de PHPUnit
├── .phpunit.result.cache         # Cache interna de resultados
└── README.md                     # Este archivo
```

---

## 🚀 Instrucciones para Ejecutar la Prueba

1. **Clonar o descomprimir** el proyecto:  
   ```bash
   git clone https://github.com/lbettero/responsivemenu.git
   cd responsivemenu
   ```
2. **Iniciar un servidor local de PHP** (ahora desde la raíz):  
   ```bash
   php -S localhost:8000
   ```
3. **Abrir el navegador y acceder a:**  
   [http://localhost:8000](http://localhost:8000)

---

## 🧪 Ejecución de Pruebas Unitarias

Ejecutar las pruebas desde la raíz del proyecto:

```bash
vendor/bin/phpunit --testdox --colors=always tests/
```

Esto genera los siguientes reportes:  
- `test-report.txt` → resumen plano  
- `test-report.html` → reporte visual detallado  

---

## ⚙️ Motivo de la Elección Tecnológica

- **PHP 8+** → Renderizado modular del HTML desde el servidor.  
- **TailwindCSS** → Framework CSS ligero y eficiente para diseño responsivo.  
- **Alpine.js** → Control de interactividad reactiva sin frameworks complejos.  
- **JavaScript nativo** → Eventos y control fino del menú y dashboard.  
- **JSON** → Configuración editable sin alterar el código fuente.  

---

## 🧩 Partes Implementadas Manualmente

| Componente | Implementación manual |
|-------------|----------------------|
| `menu.php` | Lógica PHP para cargar, validar y renderizar el menú dinámico (hasta 3 niveles). |
| `menu.js` | Control de apertura/cierre del menú, comportamiento móvil y desktop. |
| `dashboard.js` | Envío y escucha de eventos personalizados (`menu:filter`, `menu:reset`). |
| `main.css` | Personalización de colores, tipografía, corrección de z-index y stacking context. |
| `header.php` / `footer.php` | Plantillas modulares HTML actualizadas tras la eliminación de `public/`. |
| `MenuTest.php` / `DashboardScriptTest.php` | Pruebas unitarias PHP y JS con PHPUnit. |

---

## 🧱 Estado del Proyecto

**Versión actual:** `v2.1.0`  
**Estado:** Implementación estable y corregida  

Incluye:
- Menú dinámico funcional y accesible.  
- Submenús visibles en primer plano en todos los niveles.  
- Interfaz moderna, responsiva y optimizada.  
- Sistema de pruebas unitarias activo.  
- Documentación actualizada con la nueva estructura.  

---

## 🗓️ Historial de Versiones

| Versión | Fecha | Descripción |
|----------|--------|-------------|
| **v2.1.0** | 11 de noviembre de 2025 | Eliminación de carpeta `public/` duplicada y ajuste general de rutas. Corrección definitiva del bug de visibilidad de submenús mediante actualización de `header.php`, `menu.php` y `main.css`. |
| **v2.0.0** | 10 de noviembre de 2025 | Integración del dashboard interactivo con Alpine.js, corrección de interactividad y pruebas unitarias JS. |
| **v1.0.1** | 8 de noviembre de 2025 | Versión estable del menú dinámico con carga desde `menu.json` y estructura modular PHP. |
| **v1.0.0** | 8 de noviembre de 2025 | Versión inicial funcional del proyecto con TailwindCSS y renderizado dinámico. |

---

**Autora:** Livia Pérez Bettero  
**Colaboración técnica:** ChatGPT (OpenAI)
