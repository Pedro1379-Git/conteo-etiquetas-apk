# Conteo de etiquetas Honda – APK

Envuelve `www/index.html` (la app completa, funciona sin internet) en un APK de Android con Capacitor.
GitHub compila el APK por ti; no necesitas instalar nada en tu computadora.

## Pasos
1. En GitHub: **New repository** (puede ser privado), por ejemplo `conteo-etiquetas`.
2. Sube **el contenido** de esta carpeta (que en la raíz queden `package.json`, `capacitor.config.json`, `www/`, `scripts/` y `.github/`).
   Con la web de GitHub: **Add file → Upload files**. Arrastra todo, incluida la carpeta oculta `.github`
   (si tu navegador no sube carpetas ocultas, crea el archivo `.github/workflows/android.yml` con **Add file → Create new file** y pega su contenido).
3. Abre la pestaña **Actions → Compilar APK → Run workflow**. (También corre solo cada vez que subes cambios a `main`.)
4. Cuando termine (unos 5–10 minutos, check verde), entra a esa ejecución y descarga **conteo-etiquetas-apk** (un .zip con `app-debug.apk`).
5. Pasa el APK al celular, ábrelo y permite **instalar apps de origen desconocido** cuando lo pida.
6. Al abrir la app y tocar «Abrir cámara en vivo», Android pide el permiso de cámara; acepta.

## Actualizar la app
Reemplaza `www/index.html` por la versión nueva, súbelo y vuelve a correr **Compilar APK**. Instala el APK nuevo encima del anterior (conserva el mismo nombre de paquete: `com.yorozu.conteoetiquetas`).
Si Android rechaza la actualización por firma distinta, desinstala la anterior primero (se pierden los conteos guardados).

## Notas
- El APK es de depuración (firmado con clave de prueba): sirve para uso interno, no para Google Play.
- Si la compilación falla, abre el paso en rojo en **Actions** y copia el error.
- Para agregar números de parte nuevos hay que editar la lista `CATALOG` dentro de `www/index.html` y recompilar.
