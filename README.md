# Mercado Norte Sur — Landing "Próximamente"

Página única (autocontenida, sin dependencias externas salvo Google Fonts y una
foto de Wikimedia Commons) para publicar en **www.mercadonortesur.cl** mientras
se termina el desarrollo del sitio completo.

## Publicar en tu dominio propio (www.mercadonortesur.cl) usando GitHub Pages

### 1. Crear un repo nuevo, solo para la landing
Usar un repo aparte (ej: `mercadonortesur-landing`) es lo más prolijo: mantiene
el sitio completo (`mercadonortesur`) separado, mientras la landing pública usa
el dominio real.

En GitHub: **New repository** → nombre `mercadonortesur-landing` → Public → Create.
Subí este `index.html` (y este README si querés) igual que hiciste con el otro
repo (Add file → Upload files, o clonándolo en Cursor).

### 2. Activar GitHub Pages
En el repo: **Settings → Pages** → Branch `main`, carpeta `/ (root)` → Save.
Va a quedar temporalmente en `https://juanjogomezc.github.io/mercadonortesur-landing/`.

### 3. Conectar tu dominio (www.mercadonortesur.cl)
En la misma pantalla de **Settings → Pages**, en "Custom domain" escribí:
```
www.mercadonortesur.cl
```
y guardá. Esto crea automáticamente un archivo `CNAME` en el repo con ese dominio.

### 4. Configurar el DNS en NIC Chile
Entrá al panel de administración de tu dominio en NIC Chile (o donde lo tengas
delegado) y agregá estos registros:

**Para que funcione `www.mercadonortesur.cl`:**
| Tipo  | Nombre | Valor |
|-------|--------|-------|
| CNAME | www    | `juanjogomezc.github.io` |

**Para que funcione también sin el "www" (`mercadonortesur.cl` a secas), agregá además:**
| Tipo | Nombre | Valor |
|------|--------|-------|
| A    | @      | `185.199.108.153` |
| A    | @      | `185.199.109.153` |
| A    | @      | `185.199.110.153` |
| A    | @      | `185.199.111.153` |

(Estas 4 IPs son fijas de GitHub Pages, no cambian.)

### 5. Esperar propagación y activar HTTPS
La propagación de DNS puede tardar desde minutos hasta un par de horas. Una vez
que GitHub detecte el dominio correctamente, en la misma pantalla de Pages va a
aparecer la opción **"Enforce HTTPS"** — actívala para que el sitio quede con
candado seguro (`https://www.mercadonortesur.cl`).

## Cuando el sitio completo esté listo
Cuando quieras reemplazar la landing por el sitio real: subís el contenido del
repo `mercadonortesur` (el sitio completo) a este mismo repo de la landing
(o simplemente movés el archivo `CNAME` con el dominio al repo `mercadonortesur`
y desactivás Pages en este de la landing). El dominio sigue el `CNAME`, no el
repo — podés reapuntar cuándo quieras sin tocar el DNS de nuevo.
