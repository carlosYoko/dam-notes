# Bases de Datos

## El diagrama Entidad - Relación

### Modelo lógico

Representación estructurada de los datos que necesita un sistema, independiente de cómo se implementen en un gestor concreto. Especifica las entidades, sus atributos, sus identificadores únicos, las relaciones y las restricciones, como la cardinalidad y la opcionalidad.

**Distinción de niveles:** El modelo conceptual describe los conceptos del negocio mediante entidades y relaciones; el modelo lógico los organiza según el modelo de datos elegido. En un modelo lógico relacional se especifican tablas, columnas, claves y restricciones. El modelo físico concreta la implementación en un gestor. En algunos materiales introductorios se llama «modelo lógico» al ERD detallado.

**Para qué sirve:** Organiza los requisitos de información y orienta el diseño de la base de datos.

**Ejemplo:** Un modelo lógico de una tienda puede definir las entidades `Cliente` y `Pedido`, sus atributos y la relación por la que un cliente realiza pedidos.

### Entidad e instancia

Una **entidad** es una clase de objetos o conceptos sobre la que se guarda información; una **instancia** es un caso concreto de esa clase.

- **Ejemplo 1:** `Cliente` es una entidad; «el cliente con DNI 12345678A» es una instancia.
- **Ejemplo 2:** `Producto` es una entidad; «el teclado con código P025» es una instancia.

### Atributo

Dato que describe una característica de una entidad o de una relación.

**Para qué sirve:** Almacena información concreta, como el nombre o la fecha de nacimiento de un cliente.

### Atributo obligatorio y atributo opcional

Un atributo **obligatorio** debe tener valor en todas las instancias; uno **opcional** puede quedar sin informar.

**Ejemplo en un registro de clientes:** El DNI puede ser obligatorio si las reglas del negocio lo exigen para todos los clientes; un segundo teléfono puede ser opcional porque no todos tienen uno. La obligatoriedad depende de los requisitos del sistema, no del nombre del atributo.

### Atributo volátil y atributo no volátil

Un atributo **volátil** puede cambiar con frecuencia; uno **no volátil** suele permanecer estable.

**Ejemplo en un registro de clientes:** La dirección es volátil porque el cliente puede mudarse; la fecha de nacimiento es no volátil porque no cambia, aunque se puedan corregir errores de registro.

**Importancia al elegir un UID:** Conviene usar atributos estables para evitar cambios en el identificador y en las referencias desde otros registros. La estabilidad por sí sola no basta: la fecha de nacimiento no identifica de forma única a un cliente. Un `id_cliente` artificial y estable suele ser una buena alternativa. Los atributos volátiles siguen siendo necesarios para describir los datos actuales.

### Identificador único (UID)

Atributo o conjunto de atributos que distingue de forma única cada instancia de una entidad.

**Para qué sirve:** Permite identificar y referenciar cada registro sin confundirlo con otro.

### UID candidato

Atributo o conjunto mínimo de atributos que podría identificar de forma única cada instancia de una entidad. «Mínimo» significa que ningún atributo del conjunto puede eliminarse sin perder la unicidad.

**Ejemplo:** `id_cliente` y `DNI` pueden ser UID candidatos si ambos son únicos y obligatorios según las reglas del sistema. Se elige uno como identificador principal; los demás siguen siendo identificadores alternativos.

### UID compuesto

UID formado por dos o más atributos que, combinados, identifican de forma única una instancia.

**Ejemplo:** En `LíneaPedido`, el par (`numero_pedido`, `numero_linea`) identifica cada línea. El número de pedido se repite en sus distintas líneas y el número de línea se repite en distintos pedidos; la combinación no se repite.

### UID artificial

Identificador creado expresamente, sin significado propio para el negocio, como un número secuencial `id_cliente`.

### Objetivos del modelo entidad-relación

Los objetivos pueden resumirse en estos **cuatro puntos**:

1. **Recoger los requisitos de información:** Identificar qué datos necesita almacenar el sistema.
2. **Organizar los datos y sus reglas:** Definir entidades, atributos, identificadores, relaciones y restricciones del negocio.
3. **Comunicar y validar el diseño:** Ofrecer una representación comprensible para usuarios y diseñadores, que permita detectar omisiones, ambigüedades y redundancias.
4. **Servir de base para diseñar la base de datos:** Facilitar la transformación del modelo en una estructura de tablas y claves antes de su implementación.

### Relación entre entidades

Asociación entre instancias de una o varias entidades. Por ejemplo, un cliente realiza pedidos.

### Opcionalidad de una relación

Indica si una instancia debe participar en una relación o puede no hacerlo. Las palabras clave son **«debe»** (participación obligatoria, mínimo 1) y **«puede»** (participación opcional, mínimo 0).

**Ejemplo:** Un pedido **debe** pertenecer a un cliente, pero un cliente **puede** realizar pedidos: se admite registrar un cliente que todavía no tenga ninguno. Hay que analizar la opcionalidad en ambos sentidos.

### Cardinalidad

Responde a **«¿cuántas?»**: indica cuántas instancias de una entidad pueden asociarse con una instancia de la otra. Según la cardinalidad máxima en ambos extremos, hay **tres tipos**:

| Tipo | Definición | Ejemplo y reglas del caso |
| --- | --- | --- |
| **Uno a uno (1:1)** | Cada instancia de un lado se asocia, como máximo, con una del otro, y viceversa. | Un empleado tiene como máximo una taquilla y cada taquilla se asigna como máximo a un empleado. |
| **Uno a muchos (1:N)** | Una instancia del primer lado puede asociarse con varias del segundo; cada instancia del segundo se asocia como máximo con una del primero. | Un cliente puede realizar varios pedidos; cada pedido pertenece a un solo cliente. |
| **Muchos a muchos (N:M)** | Una instancia de cualquiera de los lados puede asociarse con varias del otro. | Un alumno puede cursar varias asignaturas y una asignatura puede tener varios alumnos. |

**Nota:** `N:1` es la misma relación `1:N` leída en sentido inverso, no un cuarto tipo. Cuando se expresan mínimo y máximo juntos se usan notaciones como `0..1`, `1..1`, `0..N` y `1..N`; el mínimo refleja la opcionalidad.

### Relación recursiva

Sí, una entidad puede relacionarse consigo misma: es una **relación recursiva** o **unaria**. Las instancias participan con papeles distintos.

**Ejemplo:** Un `Empleado` supervisa a otros empleados. Los papeles son **supervisor** y **supervisado**. Si cada empleado tiene como máximo un supervisor y un supervisor puede dirigir a varios empleados, la relación es `1:N`.

**Ejemplo de datos en `Empleado`:**

| id_empleado | nombre | id_supervisor |
| --- | --- | --- |
| 1 | Ana | NULL |
| 2 | Luis | 1 |
| 3 | Marta | 1 |
| 4 | Pedro | 2 |

`id_supervisor` hace referencia a `id_empleado` de la misma tabla
### Diagrama Entidad-Relación (ERD)

Representación gráfica del modelo entidad-relación. Incluye entidades, atributos, identificadores y relaciones, y suele indicar cardinalidad y opcionalidad. En un modelo lógico también puede mostrar tipos de datos y otras restricciones; depende del nivel de detalle y de la notación utilizada.

**Componentes de un ERD:**
- **Entidades:** Objetos o conceptos sobre los que se guarda información, como `Cliente`.
- **Atributos:** Características de las entidades, como `nombre`.
- **Identificadores únicos (UID):** Atributos que distinguen cada instancia, como `id_cliente`.
- **Relaciones:** Asociaciones entre entidades, como «un cliente realiza pedidos».
- **Cardinalidad y opcionalidad:** Indican cuántas instancias pueden relacionarse y si su participación es obligatoria u opcional.

### Diagrama de matriz

Tabla que coloca las entidades en filas y columnas para analizar sus posibles relaciones. En cada cruce se puede indicar si existe una relación, su nombre y, según la convención empleada, su cardinalidad.

**Para qué sirve:** Permite revisar sistemáticamente las asociaciones, detectar relaciones omitidas o duplicadas y comprobar la coherencia antes de dibujar el ERD. La diagonal permite estudiar relaciones recursivas.

### Supertipo

Entidad general que reúne las características comunes de varios subtipos. Por ejemplo, `Persona` puede ser el supertipo de `Alumno` y `Profesor`.

### Subtipo

Entidad especializada que hereda atributos y relaciones de un supertipo y puede añadir características propias. `Alumno` puede ser un subtipo de `Persona`.

**Ejemplo conjunto:** `Persona` contiene `id_persona`, `nombre` y `fecha_nacimiento`; `Alumno` hereda esos atributos y añade `numero_expediente`; `Profesor` los hereda y añade `especialidad`. Toda instancia de un subtipo es también una instancia del supertipo.

### Relación redundante

Relación que repite información ya deducible por otras relaciones del modelo. Por ejemplo, si cada pedido pertenece a un cliente y cada factura a un pedido, relacionar directamente la factura con el cliente puede ser redundante, pues el cliente se obtiene desde el pedido.

### Entidad de intersección

Entidad, también llamada **asociativa**, que representa la asociación entre entidades cuando su relación es muchos a muchos. La descompone en dos relaciones uno a muchos y puede guardar datos propios de la asociación.

**Ejemplo:** `Matrícula` relaciona `Alumno` y `Asignatura`, y puede incluir la fecha de matrícula. Cada matrícula corresponde a un alumno y a una asignatura; un alumno y una asignatura pueden aparecer en muchas matrículas. Si se permiten matrículas en distintos cursos, hay que incluir el curso académico al definir las reglas de unicidad.

### Relación de jerarquía

Una relación jerárquica organiza instancias o entidades en **niveles**, como una estructura padre-hijo.

**Ejemplo de jerarquía organizativa:** Un empleado depende de un superior, que puede depender de otro. En un ERD se representa mediante una relación recursiva `1:N` de `Empleado` consigo misma, indicando los papeles «superior» y «subordinado». La raíz puede no tener superior. Para que sea una jerarquía estricta deben impedirse los ciclos: un empleado no puede ser su propio superior, ni directa ni indirectamente.

**Jerarquía de tipos:** También se habla de jerarquía en la generalización/especialización, donde la relación es **«es un»** entre un supertipo y sus subtipos. Por ejemplo, `Coche` y `Motocicleta` son subtipos de `Vehículo`. Se representa conectando el supertipo con sus subtipos mediante un símbolo de especialización —por ejemplo, un triángulo ISA— o dibujando los subtipos dentro del supertipo, según la notación utilizada.

**Diferencia:** «Un empleado depende de otro» describe una jerarquía entre instancias; «un coche es un vehículo» describe una jerarquía entre tipos.

## Normalización de bases de datos

### Normalización

**Idea clave: Normalización → Organiza y reduce redundancia.**

La **normalización** es un proceso de organización de las tablas de una base de datos relacional para reducir redundancias y evitar anomalías al insertar, modificar o eliminar datos. Para aplicarla hay que conocer las claves y las dependencias entre los atributos, no solo observar los datos de ejemplo.

Las formas normales son acumulativas: para cumplir **2FN** hay que cumplir **1FN**, y para cumplir **3FN** hay que cumplir **2FN**.

### Conceptos previos

- **Clave candidata:** Conjunto mínimo de atributos que identifica de forma única cada fila. Se corresponde con el concepto de [[Bases de Datos/Diccionario#UID candidato|UID candidato]] aplicado a una tabla.
- **Clave primaria (PK):** Clave candidata elegida como identificador principal de la tabla. Puede ser simple o compuesta.
- **Clave foránea (FK):** Atributo o conjunto de atributos que referencia una clave primaria o una clave alternativa única de otra tabla, o de la misma tabla.
- **Dependencia funcional (`A → B`):** Un valor de `A` determina un único valor de `B`. Por ejemplo, `id_alumno → nombre_alumno` si cada identificador corresponde a un solo alumno.
- **Atributo primo:** Atributo que pertenece a alguna clave candidata. Un atributo **no primo** no pertenece a ninguna.

### Determinante

**Idea clave: Determinante → Determina.**

Un **determinante** es el atributo o conjunto de atributos situado a la izquierda de una dependencia funcional. En `A → B`, `A` es el determinante: cada valor de `A` determina un único valor de `B`.

**Ejemplo:** En `id_departamento → nombre_departamento`, el determinante es `id_departamento`, porque cada identificador de departamento tiene asociado un único nombre.

**Importante:** Un determinante no tiene por qué ser una clave candidata de la tabla. En una tabla de alumnos, `id_departamento` puede determinar el nombre del departamento sin identificar de forma única a cada alumno.

### Primera forma normal (1FN)

Una tabla está en **1FN** cuando cada celda contiene un único valor del dominio correspondiente, sin listas ni grupos repetidos de atributos. Los valores deben ser **atómicos para el uso previsto**: no necesitan dividirse para realizar las operaciones del sistema.

**Ejemplo que no cumple 1FN:** Se guardan varios teléfonos en la misma celda.

| id_alumno | nombre | telefonos |
| --- | --- | --- |
| 1 | Ana | 600111111, 600222222 |
| 2 | Luis | 600333333 |

**Solución:** Separar los alumnos de sus teléfonos.

**Tabla `Alumno`:**

| id_alumno (PK) | nombre |
| --- | --- |
| 1 | Ana |
| 2 | Luis |

**Tabla `TelefonoAlumno`:**

| id_alumno (FK) | telefono |
| --- | --- |
| 1 | 600111111 |
| 1 | 600222222 |
| 2 | 600333333 |

La clave primaria de `TelefonoAlumno` es (`id_alumno`, `telefono`). Cada teléfono ocupa una fila y no hacen falta columnas como `telefono1`, `telefono2` o `telefono3`.

### Segunda forma normal (2FN)

Una tabla está en **2FN** si está en **1FN** y cada atributo no primo depende de **la totalidad de cada clave candidata**, no solo de una parte de ella. Es decir, no existen **dependencias parciales** de atributos no primos respecto de una clave candidata.

**Ejemplo que cumple 1FN, pero no 2FN:** Suponemos que cada alumno tiene una sola nota por asignatura. La única clave candidata, elegida como primaria, es (`id_alumno`, `id_asignatura`).

| id_alumno | id_asignatura | nombre_alumno | nombre_asignatura | nota |
| --- | --- | --- | --- | --- |
| 1 | BD | Ana | Bases de Datos | 8 |
| 1 | PROG | Ana | Programación | 9 |
| 2 | BD | Luis | Bases de Datos | 7 |

**Problema:**

- `id_alumno → nombre_alumno`: el nombre del alumno depende solo de una parte de la clave.
- `id_asignatura → nombre_asignatura`: el nombre de la asignatura depende solo de otra parte.
- (`id_alumno`, `id_asignatura`) `→ nota`: la nota sí depende de la combinación completa.

**Solución:** Descomponer la tabla en:

- `Alumno(id_alumno, nombre_alumno)`: PK `id_alumno`.
- `Asignatura(id_asignatura, nombre_asignatura)`: PK `id_asignatura`.
- `Matricula(id_alumno, id_asignatura, nota)`: PK compuesta (`id_alumno`, `id_asignatura`); ambos identificadores son también FK a sus respectivas tablas.

Así, el nombre de Ana y el nombre de Bases de Datos se almacenan una sola vez en sus tablas correspondientes.

**Importante:** Si todas las claves candidatas son de un solo atributo, una tabla en 1FN cumple automáticamente 2FN. No basta con mirar solo la clave primaria si existen otras claves candidatas.

### Tercera forma normal (3FN)

Una tabla está en **3FN** si está en **2FN** y no tiene dependencias transitivas de atributos no primos respecto de las claves candidatas. En términos prácticos, se evita que un dato no clave determine otro dato no clave dentro de la misma tabla.

**Definición precisa:** Para toda dependencia funcional no trivial `X → A`, `X` debe ser una superclave (identificar de forma única cada fila) o `A` debe ser un atributo primo. Una dependencia es no trivial cuando `A` no forma parte de `X`.

**Ejemplo que cumple 2FN, pero no 3FN:** Cada alumno pertenece a un departamento y cada departamento tiene un único nombre. La única clave candidata es `id_alumno`.

| id_alumno (PK) | nombre_alumno | id_departamento | nombre_departamento |
| --- | --- | --- | --- |
| 1 | Ana | D01 | Informática |
| 2 | Luis | D01 | Informática |
| 3 | Marta | D02 | Administración |

**Problema:** Existe una dependencia transitiva:

`id_alumno → id_departamento → nombre_departamento`

El nombre del departamento se repite por cada alumno. Si cambia, habría que modificar varias filas y podrían aparecer inconsistencias.

**Solución:** Separar los datos en:

- `Alumno(id_alumno, nombre_alumno, id_departamento)`: PK `id_alumno`; `id_departamento` es FK.
- `Departamento(id_departamento, nombre_departamento)`: PK `id_departamento`.

El nombre del departamento queda almacenado una sola vez y se consulta relacionando ambas tablas.

### Resumen de las tres formas normales

| Forma normal | Condición principal | Problema que elimina |
| --- | --- | --- |
| **1FN** | Un valor por celda, sin listas ni grupos repetidos. | Varios valores dentro de un mismo campo. |
| **2FN** | Cumplir 1FN y evitar dependencias parciales de atributos no primos respecto de claves candidatas. | Datos que dependen solo de parte de una clave compuesta. |
| **3FN** | Cumplir 2FN y evitar dependencias transitivas de atributos no primos respecto de claves candidatas. | Datos no clave que dependen de otros datos no clave. |

## Notas relacionadas

- [[Bases de Datos/Índice|Índice de Bases de Datos]].
