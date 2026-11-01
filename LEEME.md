# pmenor.es

Web de una página de pMenor · Estadística clínica en R. Es HTML y CSS estáticos, sin dependencias ni cookies, y se publica gratis con GitHub Pages.

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La web |
| `aviso-legal.html`, `privacidad.html` | **Borradores.** Hay que rellenar lo marcado como `[PENDIENTE]` con la gestoría |
| `404.html` | La página que se muestra si alguien entra en una dirección que no existe |
| `fonts/` | IBM Plex Sans y Mono alojadas en la propia web, sin Google Fonts, para no enviar la IP de las visitas a Google |
| `favicon.*`, `icon-*.png`, `apple-touch-icon.png`, `site.webmanifest` | Iconos del kit del logo |
| `og-image.png` | La imagen que aparece al compartir el enlace en WhatsApp, LinkedIn y otras redes |
| `CNAME` | Le dice a GitHub Pages que el dominio es pmenor.es |
| `robots.txt`, `sitemap.xml` | Para Google |

## Antes de publicar

1. **Las páginas legales.** Completa el nombre, el NIF, el domicilio y el plazo de conservación en `aviso-legal.html` y `privacidad.html`, y quita el recuadro de «Borrador».
2. **La clave del formulario.** Entra en web3forms.com, escribe pmenor.biostats@gmail.com y te llegará una *access key* por correo. En `index.html`, busca `TU_CLAVE_WEB3FORMS` y sustitúyelo por la clave. La clave no es secreta, porque está pensada para ir en la web. Mientras no la pongas, el formulario muestra un aviso de «vista previa» y no envía nada.

## Publicar en GitHub Pages

1. En GitHub, con la cuenta **pmenor-biostats**, crea un repositorio público que se llame `pmenor.es`, sin README.
2. Pulsa **Add file → Upload files**, arrastra todo el contenido de esta carpeta y pulsa **Commit changes**.
3. Ve a **Settings → Pages**:
   - En **Source**, elige *Deploy from a branch*. En **Branch**, elige `main` y `/ (root)`, y pulsa **Save**.
   - En **Custom domain**, escribe `pmenor.es` y pulsa **Save**.
4. Para que nadie más pueda usar tu dominio en GitHub, verifícalo así: entra en tu foto de perfil → **Settings → Pages → Add a domain**, escribe `pmenor.es` y añade en DonDominio el registro TXT que te indique.

## DNS en DonDominio

En el panel de DonDominio, entra en el dominio y abre **Zona DNS**. Borra los registros A, AAAA o CNAME que traiga por defecto para `@` y `www`, y crea estos:

| Tipo | Nombre | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | pmenor-biostats.github.io. |

Los cambios pueden tardar de unos minutos a 24 horas en propagarse. Cuando GitHub muestre «DNS check successful» en **Settings → Pages**, marca **Enforce HTTPS**.

No toques los registros MX si más adelante configuras un correo en el dominio.

## Comprobación final

- `https://pmenor.es` y `https://www.pmenor.es` abren la web, con el candado.
- Envía una consulta de prueba desde el formulario y comprueba que llega a pmenor.biostats@gmail.com. Revisa también la carpeta de spam.
- Pon `pmenor.es` como enlace en la bio de Instagram.
