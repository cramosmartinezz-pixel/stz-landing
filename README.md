# STZ Climatización — Landing page

Sitio estático de una sola página. Sin dependencias, sin build, sin framework.
Se despliega tal cual está.

## Archivos

| Archivo       | Qué es                                                  |
|---------------|---------------------------------------------------------|
| `index.html`  | Toda la página: estructura, estilos y scripts.           |
| `favicon.svg` | Ícono que aparece en la pestaña del navegador.           |

---

## Cómo cambiar los datos de contacto

Abrí `index.html`, bajá hasta el final y buscá el bloque `const STZ = {`.
**Es el único lugar que hay que tocar.**

```js
const STZ = {
  // Número de WhatsApp en formato internacional: sin +, sin espacios ni guiones.
  // Chile: 56 + 9 + los 8 dígitos  ->  "56961129694"
  whatsapp: "56961129694",

  // Cómo se muestra el número en pantalla
  telefono: "+56 9 6112 9694",

  // Usuario de Instagram, sin la @
  instagram: "stz.climatizacion",

  email:   "steerzcl@gmail.com",
  zona:    "Santiago de Chile",
  horario: "Lunes a sábado, 8:00 a 18:00"
};
```

Al cambiar ese bloque se actualizan solos:

- los 6 botones de WhatsApp de la página (incluido el flotante),
- el link de Instagram,
- el link de email,
- la zona de cobertura en el encabezado y el pie,
- el horario de atención.

### Lo único que queda aparte

**La lista de comunas**, en la sección *Zona de cobertura*. Busca
`<li>Maipú</li>` y edita los seis ítems.

---

## Desplegar en Vercel

El repositorio tiene `index.html` en la raíz, así que Vercel lo detecta como
sitio estático sin configuración.

1. En Vercel: **Add New → Project → Import** el repositorio de GitHub.
2. Framework Preset: **Other**.
3. Build Command y Output Directory: dejarlos vacíos.
4. **Deploy**.

> Si al subir los archivos a GitHub quedaron dentro de una carpeta
> (por ejemplo `LANDING STZ/index.html`), en Vercel hay que poner esa carpeta
> en **Root Directory** durante la importación.

Cada vez que hagas un cambio en GitHub, Vercel vuelve a desplegar solo.

### Después de tener el dominio final

En el `<head>` de `index.html`, actualizá la URL de `og:url` para que la vista
previa al compartir el link apunte al dominio real.

---

## Pendientes recomendados

- [x] Cargar el WhatsApp, Instagram, email y zona reales.
- [x] Reemplazar la lista de comunas.
- [ ] Confirmar los días de atención (hoy dice "Lunes a sábado").
- [ ] Sumar 2 o 3 fotos de trabajos terminados en la sección de servicios.
- [ ] Sumar testimonios de clientes con nombre y comuna.
- [ ] Conectar un dominio propio.
