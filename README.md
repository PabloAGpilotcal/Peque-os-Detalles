# Pequeños Detalles — App (PWA)

Esta carpeta tiene todo el código de la app: `index.html`, `manifest.json`, `sw.js` (service worker) y los íconos.

Para que se pueda **instalar** en el celular (y no dependa de abrir un navegador cada vez), necesitás subir estos archivos a un hosting con HTTPS. Los navegadores solo permiten instalar una PWA si se sirve por `https://` (o `localhost` para probar).

## Opción recomendada: GitHub Pages (gratis)

1. Creá una cuenta en [github.com](https://github.com) si no tenés.
2. Creá un repositorio nuevo (público), por ejemplo `pequenos-detalles-app`.
3. Subí **todo el contenido de esta carpeta** (no la carpeta en sí, sino lo que está adentro: `index.html`, `manifest.json`, `sw.js` y la carpeta `icons/`) a la raíz del repositorio.
   - Se puede hacer arrastrando los archivos desde la web de GitHub ("Add file" → "Upload files"), sin usar la terminal.
4. Andá a **Settings → Pages** del repositorio.
5. En "Source" elegí la rama `main` y la carpeta `/ (root)`, y guardá.
6. GitHub te va a dar un link parecido a:
   `https://tu-usuario.github.io/pequenos-detalles-app/`
7. Esperá 1-2 minutos y abrí ese link desde el celular.

## Instalarla en el celular

**Android (Chrome):**
1. Abrí el link.
2. Tocá el menú (⋮) de arriba a la derecha.
3. Elegí "Instalar aplicación" (o "Agregar a pantalla de inicio").
4. Va a quedar un ícono como cualquier otra app, con el logo de Pequeños Detalles.

**iPhone (Safari):**
1. Abrí el link.
2. Tocá el botón de compartir (el cuadradito con la flecha hacia arriba).
3. Elegí "Agregar a pantalla de inicio".
4. Confirmá el nombre y tocá "Agregar".

Una vez instalada, se abre en pantalla completa, sin la barra del navegador, y funciona sin conexión (los datos ya cargados se ven igual; hace falta conexión solo la primera vez para bajar la app).

## Otras opciones de hosting

Si preferís no usar GitHub, cualquiera de estos sirve igual (todos gratis y con HTTPS automático), subiendo los mismos archivos:
- [Netlify](https://app.netlify.com/drop) — arrastrás la carpeta y listo, sin cuenta obligatoria para probar.
- [Vercel](https://vercel.com)
- [Cloudflare Pages](https://pages.cloudflare.com)

## Sobre los datos

Esta versión guarda todo **en el propio dispositivo** (localStorage del navegador), no en un servidor. Ventaja: es privado y no depende de internet para funcionar. Cuidado:
- Si se borra el historial/datos del navegador, se pierde la información.
- No se sincroniza sola entre el celular y la computadora: son "bases" separadas.
- Por eso la app tiene un botón **"Descargar respaldo"** en la pestaña Resumen — usalo cada tanto (por ejemplo, una vez por semana) para bajar un archivo `.json` con todo, y **"Restaurar respaldo"** para cargarlo de nuevo si hace falta (por ejemplo, si cambian de celular).

## Actualizar la app más adelante

Si en el futuro querés que Claude le cambie o agregue algo, avisale y te vuelve a pasar los archivos actualizados. Después solo hay que volver a subirlos (pisando los viejos) al mismo repositorio o carpeta del hosting. Si el `index.html` cambia, conviene subir también un número de versión nuevo en la primera línea de `sw.js` (`CACHE_NAME`) para que los celulares bajen la versión nueva y no se queden con la vieja guardada en caché.
