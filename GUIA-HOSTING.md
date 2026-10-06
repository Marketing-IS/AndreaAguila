# Andrea Aguila — sitio completo para hosting

Este paquete contiene el diseño actual completo en HTML, CSS y JavaScript, junto con el logo, las ilustraciones PNG transparentes y la foto. Es un sitio estático: no necesita instalación de paquetes, compilación, Node.js, base de datos ni herramientas de Sites para funcionar.

## Subir a tu hosting

1. Descomprime `andrea-aguila-hosting.zip` en tu ordenador.
2. Abre el administrador de archivos de tu hosting o conéctate por FTP/SFTP.
3. Entra en la carpeta pública de tu dominio, normalmente `public_html`, `www` o `htdocs`.
4. Sube **el contenido del ZIP directamente dentro de esa carpeta**, incluyendo las carpetas de páginas y `assets`. El archivo `index.html` debe quedar en la raíz pública, no dentro de una carpeta adicional llamada `andrea-hosting`.
5. Abre tu dominio y verifica Inicio, Sobre mí, Acompañamiento, Mi enfoque, Preguntas frecuentes y Contacto.

Si el hosting ofrece selección de carpeta de publicación, selecciona la carpeta que contiene `index.html`. No hace falta ejecutar un comando de build. Las carpetas de cada página ya incluyen su propio `index.html`; no necesitas reglas de redirección de una SPA.

El sitio está preparado para la raíz de un dominio o subdominio, por ejemplo `https://tudominio.com/`. Para alojarlo en una subcarpeta como `/coaching/` hay que adaptar las rutas absolutas del HTML y de `app.js`.

Si ya existe una web en tu dominio, guarda una copia antes de sustituir sus archivos.

## Archivos y edición

| Archivo o carpeta | Contenido |
| --- | --- |
| `index.html` | Página de entrada y enlaces al CSS/JavaScript |
| `styles.css` | Todo el CSS del diseño reunido en un archivo, conservando el orden original |
| `app.js` | Textos en español/francés, estructura de páginas, navegación e interacciones |
| `assets/` | Logo horizontal, tres ilustraciones transparentes y foto |
| `sobre-mi/`, `acompanamiento/`, `mi-enfoque/`, `preguntas-frecuentes/`, `contacto/`, `privacidad/` | Entradas HTML para cada ruta |

Para cambiar textos, edita `app.js`. La función `t(textoEspañol, textoFrancés)` contiene las dos versiones de cada texto. El idioma francés usa `?lang=fr`.

Para cambiar colores, tamaños y distribución, edita `styles.css`. Los últimos bloques son los ajustes más recientes y tienen prioridad sobre los anteriores. Busca `pastel-theme.css` dentro de los comentarios del archivo para localizar la paleta actual.

El correo y WhatsApp están al principio de `app.js`, en `CONTACT`:

```js
const CONTACT = {
  email: 'andreaorrala19@gmail.com',
  whatsapp: '593978773938'
};
```

## Cómo funciona el contacto

El formulario prepara un correo y abre la aplicación de correo del visitante. El visitante revisa y envía el mensaje allí. No hay envío automático ni almacenamiento de datos en el hosting. Los botones de WhatsApp abren la conversación correspondiente.

Para enviar directamente desde la web necesitas añadir un servicio de formularios o un backend. Este paquete conserva el funcionamiento actual.

## Recursos y animaciones

Las fuentes se cargan desde Google Fonts; el CSS incluye fuentes de respaldo si no hay conexión. Las imágenes están incluidas localmente. Las animaciones, el carrusel, las pestañas y las preguntas frecuentes funcionan con el código incluido. La animación de la mano puede pausarse y respeta la preferencia de reducir movimiento.

El logo es el archivo suministrado por el usuario. La foto actual es provisional; reemplaza `assets/portrait-photo.png` por la fotografía definitiva de Andrea cuando esté disponible.

## Vista previa local

Abre la carpeta con un servidor HTTP local, por ejemplo Live Server en tu editor. No abras `index.html` haciendo doble clic: las rutas del sitio parten de la raíz del servidor.
