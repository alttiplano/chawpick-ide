# Contribuir a Chawpick IDE

Gracias por querer ayudar. Esta guía es corta a propósito: léela entera antes de abrir tu primer PR.

## Enlaces rápidos

- **Discord:** [discord.gg/Dx4YUqgrm9](https://discord.gg/Dx4YUqgrm9): preguntas, ideas y ayuda
- **Issues:** [github.com/alttiplano/chawpick-ide/issues](https://github.com/alttiplano/chawpick-ide/issues/new): bugs y propuestas
- **Arquitectura:** [ARCHITECTURE.md](ARCHITECTURE.md): cómo está organizado el código
- **Código de conducta:** [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

## ¿Qué quieres hacer?

1. **Arreglar un bug o algo pequeño** → abre un PR directamente.
2. **Añadir una función o cambiar la interfaz** → abre primero un issue o pregunta en Discord, y
   espera el visto bueno antes de programar.
3. **Un refactor grande** → no abras un PR, salvo que un mantenedor te lo pida.
4. **Hacer una pregunta** → Discord.
5. **Reportar un fallo de seguridad** → escribe a **security@alttiplano.com**. Nunca en un issue
   público.

Abrir un PR no garantiza que se fusione. Confirmar la idea antes te da las mejores opciones.

## Lo que más aceptamos

- Arreglos de bugs.
- Mejoras de rendimiento, con números de antes y después.
- Arreglos para un sistema concreto: Linux, Windows o macOS.
- Documentación y traducciones.
- Tests para código que aún no los tiene.

## Empezar

Necesitas Rust instalado con [rustup](https://rustup.rs). La versión exacta la elige solo el
archivo `rust-toolchain.toml`.

1. Haz un [fork](https://github.com/alttiplano/chawpick-ide/fork) del repositorio.
2. Clona tu fork y crea una rama para tu cambio a partir de `dev`:

```sh
git clone https://github.com/TU-USUARIO/chawpick-ide.git
cd chawpick-ide
git remote add upstream https://github.com/alttiplano/chawpick-ide.git
git fetch upstream
git checkout -b mi-cambio upstream/dev
```

### Ejecutar

**Linux**, la primera vez y después de cambiar el nombre o el icono:

```sh
scripts/install-desktop.sh
```

Arranca la app (la primera vez tarda unos minutos ⏱️):

```sh
cargo run
```

En Windows y macOS basta con `cargo run`.

## Antes de abrir un PR

Estos tres comandos tienen que pasar:

```sh
cargo fmt --check
cargo clippy --all-targets -- -D warnings
cargo test
```

- **Un tema por PR.** Si tocas varias cosas, sepáralas: un PR pequeño se revisa y se fusiona antes.
- **Máximo 2 PRs abiertos a la vez.** Termina uno antes de empezar otro.
- **Abre el PR contra `dev`**, nunca contra `main`.
- **Título:** `tipo: resumen`, por ejemplo `fix: el panel izquierdo pierde su ancho`. Tipos:
  `feat`, `fix`, `perf`, `docs`, `refactor`, `test` y `chore`.
- **Descripción corta:** qué cambia, por qué y cómo lo probaste.
- **Cambios visuales:** añade capturas de antes y después.

Fusionamos con *squash*: tu PR entra en `dev` como un solo commit.

## Rendimiento

Chawpick IDE tiene que sentirse rápido. Si tu cambio puede afectar al arranque, la escritura, el
scroll o la memoria, mide antes y después con `cargo run --release` y pon los números en el PR.

- **Nunca bloquees la ventana.** El trabajo lento (red, disco) va en un hilo aparte.
- **Cada dependencia nueva necesita una razón.** Menos dependencias significa compilar antes y un
  programa más ligero.

## Reglas del proyecto

Las reglas completas están en [AGENTS.md](AGENTS.md) y [ARCHITECTURE.md](ARCHITECTURE.md). Las más
importantes:

- **egui solo se usa en `crates/ui` y `apps/`.** Los demás crates no dibujan.
- **No cambies el nombre, el icono ni la versión** (`crates/brand`, `assets/app-icon/`, `Cargo.toml`).
  Eso lo hace el mantenedor.

## Herramientas de IA

Puedes usar IA para programar, pero el autor eres tú y respondes por cada línea:

- **Entiende tu código.** Si no sabes explicar un cambio, no lo envíes.
- **Escribe tú el PR y tus respuestas.** Queremos hablar contigo, no con un modelo. Si traduces con
  IA, añade también tu texto original.
- **Nada de bots ni agentes autónomos** abriendo PRs, issues o comentarios.
- **Sin firmas de IA** en commits ni PRs. Borra líneas como estas antes de enviar:

```
Co-Authored-By: Claude <noreply@anthropic.com>
🤖 Generated with Claude Code
```

Los PRs que no cumplan estas reglas se cierran.

## Licencia

Al contribuir, aceptas que tu aporte se publique bajo la licencia del crate que tocas:
[GPL-3.0-or-later](LICENSE-GPL) por defecto, o [MIT](LICENSE) en los crates cuyo `Cargo.toml` dice
`license = "MIT"`.

---

<sub>Mantenido por [Alttiplano](https://alttiplano.com).</sub>
