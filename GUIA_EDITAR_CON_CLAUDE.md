# Guía: Editar la página de ADC con Claude (gratis)

Esta guía explica cómo cualquier persona del equipo de ADC puede **pedir cambios a la
página web escribiendo en español**, sin saber programar. Claude (la inteligencia
artificial) hace el cambio y lo deja listo para que ustedes solo aprueben con un clic.

La página web vive en GitHub (en `adcurundu.org`). Cada cambio aprobado se publica solo.

---

## PARTE 1 — Configuración (UNA SOLA VEZ, la hace un administrador)

> Esto lo hace **una vez** una persona con acceso de administrador al repositorio
> (por ejemplo Connor o un encargado de ADC). Toma unos 10 minutos.

### Paso 1 — Crear una clave de Claude (API key)
1. Entra a **https://console.anthropic.com** y crea una cuenta (o inicia sesión).
2. Las cuentas nuevas reciben **$5 de crédito gratis**, suficiente para decenas de cambios.
3. Ve a **API Keys → Create Key**, ponle un nombre (ej. "Web ADC") y **copia la clave**
   (empieza con `sk-ant-...`). Guárdala; no se vuelve a mostrar.

### Paso 2 — Guardar la clave en GitHub (como secreto)
1. Abre el repositorio: **https://github.com/Asociacion-Deportiva-Curundu/my-website**
2. Ve a **Settings** (Configuración) → en el menú izquierdo, **Secrets and variables → Actions**.
3. Botón **New repository secret**.
4. En **Name** escribe exactamente: `ANTHROPIC_API_KEY`
5. En **Secret** pega la clave `sk-ant-...` del Paso 1. Guarda con **Add secret**.

### Paso 3 — Instalar la app de Claude en el repositorio
1. Entra a **https://github.com/apps/claude** y haz clic en **Install**.
2. Elige la organización **Asociacion-Deportiva-Curundu**.
3. Selecciona **Only select repositories → my-website** y confirma.
   (Esto le da permiso a Claude para leer la web, responder Issues y abrir Pull Requests.)

✅ Listo. La configuración queda hecha para siempre. No hay que repetirla.

---

## PARTE 2 — Pedir un cambio (lo hace CUALQUIER persona del equipo)

### Paso 1 — Abrir una "solicitud" (Issue)
1. Entra al repositorio: **https://github.com/Asociacion-Deportiva-Curundu/my-website**
2. Pestaña **Issues** → botón verde **New issue**.

### Paso 2 — Escribir lo que quieres, empezando con `@claude`
En el cuadro de texto escribe tu pedido **en español**, comenzando con `@claude`.
Mientras más específico, mejor (di en qué página y qué texto cambiar).

**Ejemplos:**

```
@claude En la página de FAQ, cambia el horario de entrenamiento de
"lunes y miércoles de 1:00 a 3:00 PM" a "martes y jueves de 2:00 a 4:00 PM".
```

```
@claude Agrega un patrocinador nuevo llamado "Panaderia La Espiga" en la barra de
patrocinadores de todas las páginas, con enlace a https://ejemplo.com
```

```
@claude En el blog, agrega una nota corta titulada "ADC gana la copa juvenil 2026"
con un párrafo describiendo el triunfo.
```

Haz clic en **Submit new issue**.

### Paso 3 — Esperar a Claude (1 a 3 minutos)
Claude responderá en la misma solicitud y **abrirá un "Pull Request"** (una propuesta de
cambio) con lo que modificó.

### Paso 4 — Revisar y publicar
1. Abre el **Pull Request** que creó Claude (pestaña **Pull requests**).
2. Lee el resumen del cambio. Si quieres, en la pestaña **Files changed** ves el antes/después.
3. Si todo está bien, haz clic en **Merge pull request** → **Confirm merge**.
4. La página **adcurundu.org** se actualiza sola en 1 o 2 minutos. 🎉

> ¿Algo no quedó bien? Escribe otro comentario en el mismo Pull Request, por ejemplo:
> `@claude el título quedó muy grande, hazlo más pequeño`. Claude lo corrige.

---

## Consejos

- **Sé específico:** menciona la página ("en la página de Contáctanos…") y el texto exacto.
- **Un cambio a la vez** funciona mejor que muchos cambios mezclados.
- **Siempre revisa** antes de hacer *Merge*. Nada se publica hasta que alguien aprueba.
- **Costo:** cada cambio cuesta unos pocos centavos de la clave de API. Con los $5 gratis
  alcanza para decenas de cambios. Si se acaba, se recarga la cuenta en console.anthropic.com.
- **Para gastar aún menos:** en el archivo `.github/workflows/claude.yml` se puede cambiar el
  modelo a `claude-haiku-4-5-20251001` (más barato, ideal para cambios de texto simples).

## Si Claude no responde
- Verifica que el comentario tenga `@claude` (con arroba), no `/claude`.
- Confirma que la app de Claude está instalada (Parte 1, Paso 3) y que el secreto
  `ANTHROPIC_API_KEY` existe (Parte 1, Paso 2).
- Revisa la pestaña **Actions** del repositorio para ver si la tarea se ejecutó.
