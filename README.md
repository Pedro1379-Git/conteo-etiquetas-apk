# Conteo de etiquetas Honda (APK con cámara en vivo)

App web de un solo archivo (`index.html`, funciona sin internet) empaquetada como APK de Android con Capacitor.
GitHub compila el APK; no necesitas instalar nada en tu computadora.

## Archivos (todos en la raíz del repositorio)
- `index.html` – la app completa (Módulo 4B).
- `package.json`, `capacitor.config.json` – configuración de Capacitor (appId `com.yorozu.conteoetiquetas`).
- `.github/workflows/android.yml` – flujo que compila el APK.
- `.gitignore`, `README.md`.

## Subir como una rama nueva (desde la web de GitHub)
1. Descomprime el zip. Sube **los archivos**, no la carpeta contenedora.
2. En tu repositorio: **Add file → Upload files** y arrastra `index.html`, `package.json`, `capacitor.config.json`, `.gitignore` y `README.md`.
3. Abajo, en «Commit changes», elige **Create a new branch for this commit**, ponle nombre (por ejemplo `modulo-4b`) y toca **Propose changes**.
4. El archivo del flujo va aparte (la carpeta oculta `.github` a veces no se sube arrastrando):
   **Add file → Create new file**, escribe en el nombre `.github/workflows/android.yml` (al teclear `/` crea las carpetas),
   pega el contenido de `android.yml`, elige la misma rama nueva y confirma.
5. Para compilar: pestaña **Actions → Compilar APK → Run workflow**, escogiendo tu rama nueva en «Use workflow from».
   (El flujo también corre solo al subir cambios a `main` o `master`; en otras ramas se corre a mano.)
6. Al terminar (5–10 min), descarga **conteo-etiquetas-apk** y dentro está `app-debug.apk`.
7. Instálalo en el celular permitiendo «instalar apps de origen desconocido». Al tocar «Abrir cámara en vivo», acepta el permiso.

## Actualizar la app
Reemplaza `index.html` (en la rama) y vuelve a correr **Compilar APK**.
Si Android rechaza instalar encima por firma distinta, desinstala la anterior primero (se pierden los conteos guardados).

## Notas
- APK de depuración (firmado con clave de prueba): uso interno, no Google Play.
- Para agregar números de parte, edita la lista `CATALOG` dentro de `index.html` y recompila.
- Si algo falla, abre el paso en rojo en **Actions** y copia el error.
