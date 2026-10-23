# Comunidad de monjes

Sitio estático de la renovación. La página inicial ya está publicada en el repositorio; el contenido llegará con las instrucciones.

## Requisitos

- Node.js 22
- npm

## Instalación

```bash
npm install
```

## Desarrollo

```bash
npm run dev
```

Vite queda a la escucha en todas las interfaces, en el puerto 43123: [http://127.0.0.1:43123](http://127.0.0.1:43123).

## Compilación

```bash
npm run build
```

La salida queda en la carpeta `dist`.

## Publicación en GitHub Pages

Cuando exista el remoto, el sitio se publicará con GitHub Actions. El flujo está en `.github/workflows/pages.yml`:

- se dispara con un push a la rama `main` y también de forma manual (`workflow_dispatch`);
- usa Node.js 22, instala con `npm ci` y compila con `npm run build`;
- sube la carpeta `dist` con `actions/upload-pages-artifact` y la despliega con `actions/deploy-pages`.

En el repositorio remoto hay que elegir **GitHub Actions** como origen de Pages (Settings → Pages). La opción `base: './'` de Vite permite servir el sitio aunque el repositorio no sea `usuario.github.io`.

El push al remoto todavía no está hecho.
