# EOS · Extracción de datos de contratos

Página web para subir contratos (PDF o imagen) y volcar los datos de sus intervinientes en un Google Sheet.

**Web:** https://mirimariegr.github.io/EOS/ (GitHub Pages desde `main`, carpeta raíz)

## Cómo funciona

1. La página envía cada archivo al webhook del workflow de n8n **«EOS · Documento a Google Sheet»**.
2. Claude lee el contrato (sobre todo las páginas 1 y 2) e identifica a todos los intervinientes.
3. Se añade **una fila por interviniente** en «Hoja 1» del Sheet con estas columnas:

| NOMBRE PDF | DNI/NIE | NOMBRE INTERVINIENTE | DIRECCION PARTICULAR COMPLETA | POBLACION | PROVINCIA | PAIS | CODIGO POSTAL |
| --- | --- | --- | --- | --- | --- | --- | --- |

`NOMBRE PDF` es el nombre del archivo sin `.pdf`; el nombre del interviniente incluye nombre y dos apellidos.

## Publicación

Es una web estática (`index.html`), sin compilación. Se publica con GitHub Pages desde la rama `main` (carpeta raíz).

Para probar con la URL de test de n8n: `https://mirimariegr.github.io/EOS/?webhook=<url-de-test>`.
