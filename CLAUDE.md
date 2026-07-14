# CLAUDE.md — Guía para editar el sitio de Asociación Deportiva Curundú (ADC)

Este repositorio es el sitio web público de ADC, una fundación sin fines de lucro de
fútbol juvenil en Curundú, Panamá. El sitio es **HTML/CSS/JS estático** servido por
**GitHub Pages** en **adcurundu.org**. No hay build ni framework: los cambios en los
archivos `.html`/`.css`/`.js` se publican solos al hacer merge a `main`.

## Reglas al hacer cambios

- **Idioma:** todo el contenido visible va en **español** (variante de Panamá). El sitio
  es bilingüe vía un toggle ES/EN, así que no traduzcas manualmente el texto.
- **Diseño:** respeta el sistema visual existente en `styles.css` (variables CSS como
  `--green`, `--font-h`, etc.). Reusa las clases y patrones que ya existen; no introduzcas
  bibliotecas ni frameworks nuevos.
- **Imágenes:** las imágenes se auto-hospedan en `assets/img/` y `assets/photos/`.
  **Nunca** vuelvas a enlazar imágenes desde `squarespace-cdn.com` ni `squarespace.com`.
  Optimiza imágenes nuevas a un tamaño web razonable.
- **SEO / datos estructurados:** no rompas los bloques `<title>`, `<meta>`, `<link rel="canonical">`,
  Open Graph/Twitter, ni el JSON-LD (`application/ld+json`) en `index.html`, `alianzas.html`
  y `faq.html`. Si cambias contenido relevante (horarios, teléfono, etc.), actualiza también
  el JSON-LD y `llms.txt` para que coincidan.
- **Teléfono/correo oficiales:** teléfono `+507 6388-0003`, correo `adcurundu@gmail.com`,
  Instagram `@adcurundu`. Mantén estos datos idénticos en todo el sitio.
- **Barra de patrocinadores:** debe tener el **mismo orden en todas las páginas**:
  BY, Afrolatino Travel, CR/GR Enterprise, Duke Engage.
- **No toques** nada relacionado con `/admin`, claves de API ni secretos. Si una tarea
  requiere un secreto, detente y avisa en el PR.

## Páginas principales

`index.html` · `acercadeadc.html` · `calendario.html` · `participar.html` ·
`contactanos.html` · `blog.html` · `faq.html` · `donar.html` · `alianzas.html` · `gracias.html`
Compartidos: `styles.css`, `nav.js`, `lang.js`, `chatbot.js`.

## Cómo trabajar

- Haz el cambio mínimo necesario y abre un Pull Request con un resumen claro **en español**
  de qué cambió y en qué páginas.
- Al ser un sitio estático, no hay pruebas que correr. Verifica que el HTML quede bien formado
  y que los enlaces e imágenes apunten a rutas que existen.
