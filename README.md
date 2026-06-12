# Tarjetas de Territorio — PWA

Galería offline para tarjetas de territorio. Se instala como app en celulares.

---

## Estructura del proyecto

```
territorio-pwa/
├── index.html        ← página principal (no editar salvo la lista de imágenes)
├── manifest.json     ← configuración de la app
├── sw.js             ← Service Worker (caché offline)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── images/           ← AQUÍ van tus imágenes
    ├── tarjeta-01.jpg
    ├── tarjeta-02.jpg
    └── ...
```

---

## Paso 1: Agregar tus imágenes

1. Copia tus imágenes a la carpeta `images/`
2. Abre `index.html` en un editor de texto
3. Busca la sección `const IMAGES = [` y edita la lista:

```js
const IMAGES = [
  { file: 'tarjeta-01.jpg', label: 'Sector Norte 1' },
  { file: 'tarjeta-02.jpg', label: 'Sector Norte 2' },
  { file: 'mi-imagen.jpg',  label: 'Nombre visible' },
];
```

- `file`: nombre exacto del archivo en la carpeta `images/`
- `label`: nombre que verán los hermanos en la galería

---

## Paso 2: Publicar en GitHub Pages

1. Crea un repositorio en GitHub (puede ser privado)
2. Sube todos los archivos del proyecto
3. Ve a **Settings → Pages**
4. En *Branch* selecciona `main` y carpeta `/root`
5. Guarda — en unos minutos tendrás una URL tipo `https://tuusuario.github.io/territorio/`

---

## Paso 3: Instalar en el celular

**Android (Chrome):**
- Abre la URL en Chrome
- Aparece un banner "Instalar app" en la parte inferior
- Toca *Instalar* — queda en la pantalla de inicio

**iPhone (Safari):**
- Abre la URL en Safari
- Toca el botón de compartir (cuadro con flecha)
- Selecciona *Agregar a pantalla de inicio*

---

## Actualizar las imágenes después

1. Agrega nuevas imágenes a la carpeta `images/`
2. Edita la lista `IMAGES` en `index.html`
3. Cambia el número de versión en `sw.js`: busca `territorio-v1` y cámbialo a `territorio-v2` (o el siguiente número)
4. Sube los cambios a GitHub — los hermanos verán las nuevas imágenes al abrir la app con internet

---

## Notas

- Las imágenes se cachean automáticamente la primera vez que se abren con internet
- Después funcionan sin conexión
- Formatos recomendados: JPG o PNG
- Para mejor rendimiento en celular: imágenes de máximo 1–2 MB cada una
