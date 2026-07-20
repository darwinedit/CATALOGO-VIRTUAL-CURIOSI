# Catálogo Curiosi

Página de catálogo con carrito y envío del pedido por WhatsApp.

## Archivos de este proyecto

- `index.html` → la página en sí (normalmente **no necesitas tocarla**).
- `products.json` → aquí es donde editas precios, descripciones, categorías y fotos.
- `images/` → carpeta donde puedes subir tus fotos de producto.

---

## 1. Publicar la página con GitHub Pages (solo la primera vez)

1. Sube estos 3 elementos (`index.html`, `products.json`, `images/`) a un repositorio de GitHub.
2. Entra a **Settings** (Configuración) del repositorio.
3. En el menú izquierdo, entra a **Pages**.
4. En "Source" / "Branch" elige `main` y la carpeta `/ (root)`. Guarda.
5. Espera 1-2 minutos. GitHub te dará un link tipo:
   `https://tu-usuario.github.io/nombre-del-repositorio/`
   Ese es el link que compartes con tus clientes.

---

## 2. Editar un precio, nombre, descripción o categoría

1. En GitHub, abre el archivo **`products.json`**.
2. Dale clic al ícono de lápiz (✏️) arriba a la derecha para editarlo.
3. Busca el producto que quieres cambiar. Cada producto se ve así:

   ```json
   {
     "id": "p1",
     "name": "Mini parlante Bluetooth",
     "description": "Sonido potente, batería de 8 horas, resistente a salpicaduras.",
     "price": 45,
     "category": "Tecnología",
     "image": "https://placehold.co/400x400/BF6832/FCF3E7?text=Parlante"
   }
   ```

4. Cambia solo lo que está **entre comillas** (o el número en `price`, que no lleva comillas).
   - Cambiar precio: `"price": 45` → `"price": 50`
   - Cambiar nombre: edita el texto dentro de `"name": "..."`
   - Cambiar descripción: edita el texto dentro de `"description": "..."`
   - Cambiar categoría: usa una de estas (o crea una nueva escribiéndola igual en varios productos): `Tecnología`, `Novedades`, `Hogar`, `Otros`
5. Baja al final de la página y dale a **"Commit changes"** (puedes elegir "Commit directly to the main branch").
6. Espera 1 minuto y actualiza la página del catálogo (Ctrl+F5 o Cmd+Shift+R para forzar que cargue lo nuevo).

⚠️ **Cuidado con la puntuación del JSON:**
- Cada producto va entre `{ }`.
- Los productos van separados por comas `,`.
- El **último** producto de la lista NO lleva coma después de su `}`.
- Si GitHub te muestra el texto en rojo o un aviso de error al guardar, revisa que no falte o sobre una coma o una comilla.

---

## 3. Agregar un producto nuevo

1. Copia un bloque completo de un producto existente (desde `{` hasta `}`).
2. Pégalo justo antes del `]` final, agregando una coma después del `}` del producto anterior.
3. Cambia el `"id"` por uno que no se repita (ejemplo: `"p7"`, `"p8"`...).
4. Edita nombre, descripción, precio, categoría y foto.

## 4. Eliminar un producto

1. Borra el bloque completo del producto (desde `{` hasta `}`, incluida la coma que lo separa del siguiente).
2. Revisa que no quede una coma "suelta" antes del `]` final.

---

## 5. Cambiar o agregar fotos

Tienes dos formas:

**Opción A — Subir la foto al repositorio (recomendado)**
1. Entra a la carpeta `images/` en GitHub.
2. Dale a **"Add file" → "Upload files"** y sube tu foto (ideal: cuadrada, menos de 1MB).
3. En `products.json`, en el campo `"image"` del producto, escribe:
   ```
   "image": "images/nombre-de-tu-foto.jpg"
   ```

**Opción B — Usar una URL de imagen que ya tengas en internet**
Simplemente pega el link directo de la imagen:
```
"image": "https://ejemplo.com/mi-foto.jpg"
```

---

## 6. Cambiar tu número de WhatsApp, nombre de tienda o moneda

Estos datos SÍ están en `index.html`, al final del archivo, dentro de `CONFIG`:

```javascript
const CONFIG = {
  storeName: "Curiosi",
  whatsappNumber: "51962599148",
  currency: "S/"
};
```

Edítalo igual que `products.json`: ícono de lápiz, cambias el texto entre comillas, y "Commit changes".

---

## Notas

- Los cambios que hagas en `products.json` se ven para **todos** los que visiten el link, no solo en tu navegador.
- Si algo se rompe (la página deja de mostrar productos), probablemente hay un error de puntuación en `products.json`. GitHub tiene un botón "Preview" al editar que ayuda a detectar errores; si el archivo no se ve bien formateado ahí, revisa comas y comillas.
