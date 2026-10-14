# Instalación — DAM-Notes + Obsidian + GitHub Copilot

## 1. Copia los archivos

Descomprime este paquete y **copia su contenido dentro de tu bóveda `DAM-Notes`**, no la carpeta contenedora `dam-notes-starter`. Deben quedar rutas como `DAM-Notes/.github/skills/crear-apuntes/SKILL.md`.

Si ya tienes un `Inicio.md`, revisa antes de sustituirlo. No borres tu carpeta `.obsidian`.

## 2. Trabaja con la misma carpeta desde VS Code

En VS Code: `File > Open Folder...` y selecciona `DAM-Notes`. Inicia sesión en GitHub y activa Copilot Chat. Selecciona **Agent** si tu plan lo permite. Las Skills necesitan un agente que pueda leer y editar archivos; el plugin de chat de Obsidian que probaste puede no tener esas herramientas.

Si VS Code no detecta Skills del repositorio, revisa la versión de VS Code/Copilot, las configuraciones de Agent Skills y el registro de chat; como alternativa, pide explícitamente: `Sigue .github/skills/crear-apuntes/SKILL.md`.

## 3. Configura asignaturas

Crea una carpeta para cada una de tus tres asignaturas y `Índice.md` dentro de cada carpeta. Sustituye los elementos pendientes en `Inicio.md` por enlaces a índices reales.

## 4. Prueba

En el chat Agent: `Sigue la skill crear-apuntes. Lee el material que te paso y crea una nota de prueba en la carpeta de la asignatura correspondiente. Antes de editar, dime qué archivo modificarás.`

Revisa los cambios antes de aceptarlos. No subas material con información privada ni contenido que no tengas derecho a distribuir.

## 5. Versiona con GitHub

Usa un repositorio privado. Si la bóveda ya es un repositorio Git, no vuelvas a ejecutar `git init`. Revisa `git status` antes de cada commit. Es recomendable excluir archivos de configuración que cambian con frecuencia y cualquier documento sensible.

## 6. PDF

En Obsidian, abre la nota de repaso y utiliza `Más opciones > Exportar a PDF` (la etiqueta exacta puede variar). Comprueba márgenes, saltos de página y bloques de código en la vista previa.

## Prompts útiles

- `Usa crear-apuntes para convertir este material en una nota de Bases de Datos. Separa contenido de clase de ampliación y evita inventar datos.`
- `Usa tutor-dam. Explícame este concepto y pregúntame una cosa cada vez.`
- `Usa preparar-examen para los temas 1–3 de esta asignatura y guarda un simulacro con respuestas separadas.`
- `Usa organizar-notas y propón mejoras sin mover ni borrar archivos todavía.`
