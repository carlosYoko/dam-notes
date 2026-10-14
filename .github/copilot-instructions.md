# Reglas generales del repositorio DAM-Notes

Este repositorio es una bóveda de Obsidian para apuntes del CFGS de DAM. Escribe en español, en Markdown compatible con Obsidian.

- Antes de crear o modificar notas, examina los nombres de las carpetas y los índices existentes para encontrar la asignatura correcta. Si no está clara, pregunta.
- No inventes contenido de clase, bibliografía, criterios de evaluación ni fechas de exámenes. Separa **Material de clase** de **Ampliación explicativa** cuando proceda.
- No atribuyas al profesorado ejemplos generados por IA.
- No sobreescribas ni borres notas sin pedir confirmación. Haz cambios pequeños y revisables.
- Usa títulos descriptivos, encabezados claros, listas moderadas, tablas solo cuando aclaren y bloques de código con lenguaje (`sql`, `java`, `bash`, etc.).
- Enlaza notas existentes con `[[Nombre de nota]]`; comprueba la existencia del destino antes de enlazarlo. Puedes proponer enlaces nuevos sin darlos por existentes.
- Añade un índice por asignatura; mantenlo actualizado tras crear notas.
- Mantén las notas útiles para impresión: evita dependencias de plugins de visualización en el contenido esencial.
- No modifiques `.obsidian/`, `.github/` ni ajustes de Git salvo petición explícita.
- Evita incluir datos personales, credenciales, claves o información privada en notas o commits.
- Antes de ejecutar comandos o realizar cambios amplios, explica brevemente qué harás.


## Organización de DAM

- Cada asignatura tiene su propia carpeta.
- Cada asignatura contiene un único archivo `Diccionario.md` en su raíz.
- Dentro de cada asignatura hay subcarpetas por tema.
- Los apuntes extensos se guardan en las subcarpetas de los temas.
- Los conceptos breves se guardan exclusivamente en el diccionario de la asignatura.
- El diccionario debe estar agrupado por temas.
- No crear diccionarios dentro de las subcarpetas.
- No duplicar conceptos existentes.

## Selección de Skills

- Si el usuario proporciona conceptos o términos técnicos, utilizar `diccionario-dam`.
- Si solicita desarrollar un tema completo, utilizar `crear-apuntes`.
- Si el usuario no especifica el tema al añadir conceptos, preguntar antes de clasificarlos.
- No generar ejercicios ni resúmenes salvo que se soliciten expresamente.
