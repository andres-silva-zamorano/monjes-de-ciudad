# Monjes de Ciudad

Sitio estático. Se abre directo en el navegador, sin Node ni compilación.

## Abrir en local

Abre `index.html` en el navegador, o sirve la carpeta así:

```bash
python3 -m http.server 43123
```

La página queda en [http://127.0.0.1:43123](http://127.0.0.1:43123).

## GitHub Pages

Cuando exista el remoto, GitHub Actions publicará el `index.html` de la raíz. El flujo está en `.github/workflows/pages.yml`:

- se dispara con un push a la rama `main` y también de forma manual (`workflow_dispatch`);
- no hay build de Node ni `npm`;
- el artefacto es un directorio `site/` que contiene solo ese `index.html`, subido con `actions/upload-pages-artifact` y desplegado con `actions/deploy-pages`.

En el repositorio remoto hay que elegir **GitHub Actions** como origen de Pages (Settings → Pages).

El push al remoto todavía no está hecho.
