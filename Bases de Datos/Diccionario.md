# Bases de Datos

## El diagrama Entidad - Relación

### Modelo lógico

Representación de los datos, sus características y sus relaciones, independiente de cómo se implementen en un gestor concreto.

**Para qué sirve:** Organiza los requisitos de información y orienta el diseño de la base de datos.

**Ejemplo:** Un modelo lógico de una tienda puede definir las entidades `Cliente` y `Pedido`, sus atributos y la relación por la que un cliente realiza pedidos.

### Entidad e instancia

Una entidad es una clase de objetos sobre la que se guarda información; una instancia es un objeto concreto de esa clase. «Cliente» es una entidad; «el cliente con DNI 12345678A» es una instancia.

### Atributo

Dato que describe una característica de una entidad o de una relación.

**Para qué sirve:** Almacena información concreta, como el nombre o la fecha de nacimiento de un cliente.

### Atributo obligatorio y atributo opcional

Un atributo obligatorio debe tener valor; uno opcional puede quedar sin informar. En un cliente, el DNI puede ser obligatorio y un segundo teléfono, opcional.

### Atributo volátil y atributo no volátil

Un atributo volátil puede cambiar con frecuencia; uno no volátil suele permanecer estable. La dirección de un cliente puede ser volátil y su fecha de nacimiento, no volátil. Es preferible un dato estable para identificar registros y evitar cambios en las referencias.

### Identificador único (UID)

Atributo o conjunto de atributos que distingue de forma única cada instancia de una entidad.

**Para qué sirve:** Permite identificar y referenciar cada registro sin confundirlo con otro.

### UID candidato

Atributo o conjunto de atributos que podría identificar de forma única las instancias de una entidad. Si hay varios, se elige uno como identificador principal.

### UID compuesto

UID formado por dos o más atributos que, combinados, identifican de forma única una instancia. Por ejemplo, número de pedido y línea de pedido.

### UID artificial

Identificador creado expresamente, sin significado propio para el negocio, como un número secuencial `id_cliente`.

### Objetivos del modelo entidad-relación

El objetivo del modelo entidad-relación es representar de forma clara los datos que necesita un sistema y las relaciones entre ellos. Esta representación ayuda a comprender y comunicar los requisitos de información, detectar cómo se vinculan las entidades y orientar el diseño de la base de datos antes de implementarla.

### Relación entre entidades

Asociación entre instancias de una o varias entidades. Por ejemplo, un cliente realiza pedidos.

### Opcionalidad de una relación

Indica si una instancia debe participar en una relación o puede no hacerlo. «Debe» expresa participación obligatoria; «puede», opcional. Por ejemplo, un pedido debe pertenecer a un cliente.

### Cardinalidad

Número máximo de instancias de una entidad que pueden asociarse con una instancia de la otra. Hay tres tipos: uno a uno (1:1), un empleado tiene una taquilla; uno a muchos (1:N), un cliente realiza varios pedidos; muchos a muchos (N:M), alumnos cursan asignaturas.

### Relación recursiva

Relación de una entidad consigo misma. Por ejemplo, un empleado supervisa a otros empleados.

### Diagrama Entidad-Relación (ERD)

Representación gráfica del modelo entidad-relación. Incluye entidades, atributos, identificadores y relaciones, y suele indicar cardinalidad y opcionalidad. En un modelo lógico también puede mostrar tipos de datos y otras restricciones; depende del nivel de detalle y de la notación utilizada.

### Diagrama de matriz

Tabla que cruza entidades para analizar sus posibles relaciones. Se utiliza para detectar asociaciones que podrían omitirse antes de dibujar el ERD.

### Supertipo

Entidad general que reúne las características comunes de varios subtipos. Por ejemplo, `Persona` puede ser el supertipo de `Alumno` y `Profesor`.

### Subtipo

Entidad especializada que hereda atributos y relaciones de un supertipo y puede añadir características propias. `Alumno` puede ser un subtipo de `Persona`.

### Relación redundante

Relación que repite información ya deducible por otras relaciones del modelo. Por ejemplo, si cada pedido pertenece a un cliente y cada factura a un pedido, relacionar directamente la factura con el cliente puede ser redundante, pues el cliente se obtiene desde el pedido.

### Entidad de intersección

Entidad que representa la asociación entre entidades cuando su relación es muchos a muchos. La descompone en relaciones uno a muchos y puede guardar datos propios de la asociación. Por ejemplo, `Matrícula` relaciona `Alumno` y `Asignatura`, y puede incluir la fecha de matrícula.

### Relación de jerarquía

Relación «es un» entre un supertipo y sus subtipos. En un ERD se representa conectando el supertipo con sus subtipos mediante una notación de especialización, que puede variar según la herramienta. Por ejemplo, `Vehículo` puede ser el supertipo de `Coche` y `Motocicleta`.
