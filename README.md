# Panoramic — Marquesina del Ingreso

Sitio estático con las 4 propuestas de iluminación del cielo raso. Videos en máxima calidad servidos desde Cloudinary; código servido por Vercel desde GitHub.

**Estado: los 4 videos ya están subidos a Cloudinary y sus URLs ya están escritas en `index.html`. No hace falta tocar nada más ahí.**

---

## Cómo está armado

- `index.html` — todo el sitio (HTML + CSS + JS en un solo archivo). Los 4 `<video>` apuntan directo a Cloudinary (cloud `xwvlgym9`), con `f_auto,q_auto` para que cada visitante reciba el mejor formato/calidad según su dispositivo, sin perder la calidad del original.
- `assets/` — solo posters (miniaturas) e imágenes de producto, livianas (~450 KB en total). Los videos NO están acá a propósito — viven en Cloudinary.

---

## Subir a GitHub

1. En tu repositorio (`Witronix-apps/panoramic-marquesina-`), usa **"Add file" → "Upload files"**
2. Arrastra todo el contenido de esta carpeta: `assets/`, `.gitignore`, `index.html`, `README.md`, `vercel.json`
3. **Commit changes**

## Conectar a Vercel

1. Vercel → **Add New → Project → Import Git Repository**
2. Elige `panoramic-marquesina-`
3. **Deploy** (no hace falta tocar "Root Directory", es un repo dedicado)

De ahí en adelante: cualquier cambio en el texto/diseño → editas `index.html` → subes de nuevo a GitHub (Upload files, o `git push` si más adelante instalas Git) → Vercel redespliega solo.

---

## Si necesitas cambiar un video más adelante

1. Sube el video nuevo a Cloudinary (Media Library → arrastra el archivo)
2. Copia su "Delivery URL" (Cloudinary le va a asignar su propio nombre y número de versión)
3. En `index.html`, busca el bloque `CLOUDINARY_VIDEOS` (cerca de la línea 460) y reemplaza esa URL por la nueva
4. Sube el `index.html` actualizado a GitHub

No hace falta tocar nada de Vercel ni de la carpeta `assets/` para esto.
