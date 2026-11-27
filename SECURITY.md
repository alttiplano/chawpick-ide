# Política de seguridad

Gracias por ayudar a mantener Chawpick IDE seguro. En Alttiplano nos tomamos la seguridad muy en
serio, y agradecemos a quienes encuentran fallos y los reportan de forma responsable.

## Importante

**No aceptamos volcados de escáneres automáticos ni reportes generados por IA sin verificar.**
Recibimos muchos reportes inventados o sin pruebas, y no tenemos recursos para revisarlos todos.

- Un reporte sin una prueba de concepto (PoC) que se pueda reproducir y que muestre un impacto real
  puede cerrarse sin más revisión.
- El spam repetido puede terminar en un bloqueo en toda la organización de Alttiplano.

Puedes investigar con ayuda de IA, siempre que una persona haya comprobado el hallazgo y el reporte
incluya una PoC que funcione.

## Versiones soportadas

Solo la **última release** y la rama `main` reciben arreglos de seguridad. Si usas una versión
anterior, actualiza.

## Modelo de amenazas

Chawpick IDE funciona en tu equipo, con tus permisos. Lee y edita los archivos que abres, y solo
ejecuta lo que tú le pides. Abrir el proyecto de un desconocido tiene que ser seguro.

### Lo que sí es un fallo de seguridad

- Abrir un archivo o una carpeta hace que se ejecute código sin que lo pidas.
- La app lee, escribe o borra archivos fuera de lo que abriste, sin que se lo pidas.
- Alguien consigue que la app descargue o instale algo que no publicó Alttiplano.
- Tus datos (archivos, rutas, claves) salen de tu equipo sin tu permiso.

### Fuera de alcance

| Categoría | Motivo |
|---|---|
| **Lo que tú ejecutas** | Los comandos, scripts o compilaciones que lanzas a propósito hacen lo que dicen |
| **Dependencias de terceros** | Repórtalo al proyecto original, salvo que se pueda explotar a través de Chawpick IDE |
| **Archivos enormes o malformados** | Si solo vuelven lenta la app o la cierran, es un bug normal: abre un [issue](https://github.com/alttiplano/chawpick-ide/issues/new) |
| **Buenas prácticas que faltan** | Ajustes ausentes que no llevan a un fallo explotable |
| **Equipo ya comprometido** | Quien ya controla tu equipo puede hacer lo mismo sin Chawpick IDE |

## Cómo reportar

**No publiques el fallo** en issues, PRs, Discord ni redes hasta que lo hayamos revisado y
arreglado.

Repórtalo en privado desde
[Report a vulnerability](https://github.com/alttiplano/chawpick-ide/security/advisories/new). El
formulario te pide un resumen, los detalles, la prueba de concepto y el impacto. Añade también:

- La versión de Chawpick IDE (o el commit) y tu sistema operativo.
- Los archivos o funciones afectados, si los conoces.
- Una posible solución, si la tienes.

Quita de los logs contraseñas, rutas personales y cualquier dato privado. No ofrecemos recompensas
económicas (*bug bounty*).

## Divulgación

Seguimos una divulgación coordinada:

1. Respondemos a tu reporte en un máximo de **5 días hábiles**.
2. Buscamos publicar el arreglo en un máximo de **90 días**.
3. Al publicarlo, creamos un aviso de seguridad en GitHub con tu nombre, salvo que prefieras quedar
   en el anonimato.

Si en 5 días hábiles no has recibido respuesta, o no puedes usar el formulario, escribe a
**[security@alttiplano.com](mailto:security@alttiplano.com)**.

---

<sub>Mantenido por [Alttiplano](https://alttiplano.com).</sub>
