# 📱 iPhone Club — Panel de Precios

Herramienta interna para gestión de listas de precios, generación de mensajes de difusión y atención al cliente. Diseñada para usar desde el celular como PWA (Progressive Web App).

---

## ¿Qué es?

Una app web instalable que reemplaza el proceso manual de armar listas de precios para WhatsApp. Permite gestionar múltiples catálogos, aplicar plantillas temáticas a los mensajes y guardar mensajes frecuentes con etiquetas.

---

## Funcionalidades

### 📤 Generar
- Elegís una lista, una plantilla y el tipo de mensaje (minorista / mayorista / libre)
- Seleccionás qué productos incluir con checkboxes
- Vista previa en tiempo real antes de copiar
- Copiás al portapapeles con un toque
- Podés guardar el mensaje generado en la sección Guardados

### 📋 Mis Listas
- Creás listas con nombre, emoji, modo de precios y color
- Cuatro modos de precios disponibles:
  - **USD dual** — mayorista base, minorista = +$20 automático
  - **USD único** — un solo precio en dólares
  - **ARS dual** — precio solo accesorio / precio con celular
  - **ARS único** — un solo precio en pesos
- Cada lista tiene sus propios productos y condiciones de pago
- Soporte de descuentos por volumen (compra mínima, tramo 1 y tramo 2)
- Campos por producto: emoji, nombre, precio, batería %, stock, nota, extra/categoría

### 🎨 Plantillas
- 12 plantillas temáticas incluidas: Estándar, Oferta, San Valentín, Navidad, Año Nuevo, Otoño, CyberMonday, Black Friday, Verano, Invierno, Pascuas, Fiesta y China
- Todas editables
- Podés crear plantillas propias con:
  - Línea decorativa (arriba y abajo del mensaje)
  - Título y subtítulo
  - Símbolo de bullet por producto
  - Frase de cierre
  - Pie adicional opcional
  - Variables dinámicas: `{{fecha}}` y `{{lista}}`
- El mensaje **minorista** usa la estética completa de la plantilla
- El mensaje **mayorista** siempre queda limpio y sin decoración

### 💬 Guardados
- Guardás cualquier mensaje con nombre y etiquetas
- Filtrás por etiqueta (mayorista, promo, cliente, etc.)
- Copiás o editás cualquier mensaje guardado

---

## Listas incluidas por defecto

| Lista | Modo | Productos |
|---|---|---|
| 📱 iPhone Club | USD dual | iPhones nuevos, usados, MacBooks, iPad, AirPods, Watch, Gaming |
| 🇨🇳 Lista China | ARS único | Electrónica y accesorios importados con descuentos por volumen |

---

## Archivos del proyecto

```
iphone-club/
├── index.html       → App completa (HTML + CSS + JS en un solo archivo)
├── manifest.json    → Configuración PWA (nombre, ícono, colores)
├── sw.js            → Service worker (caché offline)
├── icon-192.png     → Ícono PWA 192×192
├── icon-512.png     → Ícono PWA 512×512
└── README.md        → Este archivo
```

---

## Instalación como app (PWA)

La app está hosteada en GitHub Pages con HTTPS, lo que permite instalarla directamente desde el navegador.

**En iPhone (Safari):**
1. Abrí la URL en Safari
2. Tocá el botón compartir (cuadrado con flecha)
3. *Agregar a pantalla de inicio*
4. Tocá *Agregar*

**En Android (Chrome):**
1. Abrí la URL en Chrome
2. Tocá los tres puntos → *Instalar app*
3. O esperá el banner automático de instalación

Una vez instalada funciona en pantalla completa, sin barra del navegador, con ícono propio y soporte offline.

---

## Almacenamiento

Todos los datos (listas, productos, plantillas, mensajes guardados) se guardan en el **localStorage del dispositivo**. No hay base de datos externa ni servidor.

Para hacer backup usá el botón ⬇ en la barra superior — exporta un archivo `.json` con todo. Para restaurar usá ⬆ e importá ese archivo.

> Si borrás la caché del navegador se pierden los datos. Se recomienda hacer backup periódicamente.

---

## Formato de los mensajes

Los mensajes generados usan formato WhatsApp:
- `*texto*` → **negrita**
- `_texto_` → _cursiva_
- Variables disponibles en plantillas: `{{fecha}}` y `{{lista}}`

---

## Tecnologías

- HTML5 + CSS3 + JavaScript vanilla (sin frameworks)
- Progressive Web App (PWA) con Service Worker
- Almacenamiento en localStorage
- Fuente: Inter (Google Fonts)
- Hosting: GitHub Pages

---

## Desarrollo

El proyecto vive en un único archivo `index.html` por diseño — facilita el deployment y las actualizaciones. Para modificar la app:

1. Editá `index.html` localmente
2. Subí el archivo actualizado al repositorio
3. GitHub Pages lo publica automáticamente en ~1 minuto
4. Recargá la app en el celu (puede requerir cerrar y volver a abrir)

---

*Proyecto privado — iPhone Club*
