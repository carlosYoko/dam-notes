# Sistemas Operativos

Definiciones ordenadas alfabéticamente por título.

## Arquitectura cliente-servidor

Modelo en el que un **cliente** solicita un servicio y un **servidor** lo proporciona. Ambos pueden ejecutarse en el mismo equipo o en equipos distintos. En algunos sistemas operativos basados en micronúcleo, servicios como la gestión de archivos se ejecutan como procesos servidores fuera del núcleo y atienden peticiones mediante mensajes.

## BSD (Berkeley Software Distribution)

Familia de licencias de software libre permisivas. Permiten usar, modificar y redistribuir el código, incluso en software propietario, respetando sus condiciones, como conservar los avisos de autoría y licencia. No obligan a publicar las modificaciones.

## Disco virtual en formato VDI

VDI (*VirtualBox Disk Image*) es el formato nativo de disco virtual de VirtualBox. Guarda en un archivo el sistema operativo, los programas y los datos de una máquina virtual. Puede tener tamaño fijo o reservar espacio dinámicamente, creciendo según se utiliza hasta el máximo configurado.

## Firmware UEFI

Firmware moderno que inicializa el hardware y prepara el arranque del sistema operativo; es el sucesor del BIOS tradicional. En una máquina virtual, puede seleccionarse para que el sistema invitado arranque con este tipo de firmware.

## GPL (GNU General Public License)

Licencia de software libre que permite usar, estudiar, modificar y distribuir el programa. Es una licencia con **copyleft**: al distribuir el programa o una obra derivada, deben respetarse sus condiciones, como mantener la licencia GPL y proporcionar el código fuente correspondiente en los términos exigidos. No obliga a publicar las modificaciones que se usan únicamente de forma privada.

## LGPL (GNU Lesser General Public License)

Licencia de software libre con **copyleft limitado**, utilizada principalmente en bibliotecas. Permite que programas con otras licencias, incluso propietarios, utilicen la biblioteca si cumplen sus condiciones. Las modificaciones de la propia biblioteca siguen sujetas a la LGPL; al distribuirla, deben cumplirse las obligaciones relativas al código fuente y a la posibilidad de sustituir o volver a enlazar la biblioteca, según la versión y el modo de distribución.

## Licencia por volumen

Modalidad de contratación destinada a organizaciones que necesitan licenciar varios usuarios o equipos. Facilita la compra y la administración centralizada de licencias. Las condiciones de instalación, activación y uso dependen del contrato; no implica instalaciones ilimitadas.

## MIT

Licencia de software libre permisiva que permite usar, copiar, modificar y distribuir el programa, incluso como parte de software propietario. Exige conservar el aviso de derechos de autor y el texto de la licencia. No obliga a publicar las modificaciones.

## Multiprogramación

Técnica que mantiene varios programas en memoria y alterna su ejecución para aprovechar la CPU. Cuando uno espera una operación de entrada/salida, otro puede ejecutarse. En un único núcleo, esto no significa que sus instrucciones se ejecuten simultáneamente.

## Núcleo (kernel)

Parte central del sistema operativo que gestiona recursos como la CPU, la memoria y los dispositivos, y ofrece servicios básicos a los programas mediante llamadas al sistema. Se ejecuta con privilegios elevados y controla el acceso al hardware.

## OEM (Original Equipment Manufacturer)

Modalidad de licencia habitual en software propietario preinstalado en equipos nuevos. Normalmente queda vinculada al equipo original y tiene restricciones para transferirse a otro. Sus condiciones concretas dependen del fabricante y del producto.

## Oracle VM VirtualBox Extension Pack

Paquete adicional de VirtualBox que amplía sus funciones, por ejemplo, con soporte para dispositivos USB 2.0 y 3.0 en las máquinas virtuales. Se instala aparte del programa principal.

## Retail

Modalidad de licencia de software vendido por separado al usuario final. Habitualmente permite trasladarlo a otro equipo, dejando de utilizarlo en el anterior, según las condiciones del producto. No implica que pueda usarse simultáneamente en varios equipos.

## Shell

Intérprete de órdenes que permite interactuar con el sistema operativo, ejecutar programas y automatizar tareas mediante scripts. Ejemplos: **Bash** y **PowerShell**. No es el núcleo ni el terminal: el terminal permite introducir y mostrar información, mientras que la shell interpreta las órdenes.

## Sistema centralizado

Sistema en el que el procesamiento y la gestión de los recursos principales se concentran en un equipo central. Los usuarios pueden acceder mediante terminales o clientes que dependen de ese equipo.

## Sistema distribuido

Conjunto de equipos independientes conectados por una red que coordinan su trabajo para ofrecer servicios o resolver tareas. El procesamiento y los recursos se reparten entre varios nodos; no basta con que los equipos estén conectados para que formen un sistema distribuido.

## Sistema monousuario

Sistema operativo diseñado para que un solo usuario utilice sus recursos en un momento dado. Puede ejecutar uno o varios programas: **monousuario no significa monotarea**.

## Sistema operativo de tiempo real

Sistema operativo diseñado para responder a eventos dentro de plazos temporales definidos y con un comportamiento predecible. No se caracteriza solo por ser rápido, sino por cumplir los tiempos requeridos. En tiempo real **estricto**, incumplir un plazo puede ser un fallo crítico; en tiempo real **flexible**, suele degradar la calidad del servicio. Ejemplo: el control de una máquina industrial.

## Sistema operativo monolítico

Sistema operativo cuyo núcleo reúne servicios como la planificación de procesos, la gestión de memoria, los sistemas de archivos y los controladores, que se ejecutan en espacio de núcleo. Puede admitir módulos sin dejar de ser monolítico. **Linux** es un ejemplo de núcleo monolítico modular.

## Software de aplicación horizontal

Software destinado a necesidades comunes de usuarios o empresas de distintos sectores. Ejemplos: procesadores de texto, hojas de cálculo y aplicaciones de correo electrónico.

## Software de aplicación vertical

Software especializado en las necesidades de un sector o actividad concreta. Ejemplos: una aplicación de gestión de clínicas dentales o de reservas hoteleras.

## Terminal tonto

Dispositivo de entrada y salida, normalmente con teclado y pantalla, que permite comunicarse con un ordenador central. No ejecuta las aplicaciones del usuario localmente: el procesamiento principal se realiza en el equipo central.

## Time-sharing (tiempo compartido)

Técnica que reparte el tiempo de CPU en intervalos breves entre procesos para ofrecer interacción ágil a varios usuarios o tareas. Es una evolución del uso de la multiprogramación orientada a la respuesta interactiva; cada usuario percibe que dispone del sistema aunque comparta sus recursos.

## TPM 2.0 virtual

Módulo TPM 2.0 virtual proporcionado por el hipervisor. Permite a la máquina virtual almacenar claves de forma segura y usar funciones de protección, como el cifrado del disco. El TPM virtual se presenta al sistema invitado como un componente de seguridad propio.

## Unix

Familia de sistemas operativos originada en Bell Labs a finales de la década de 1960, caracterizada por ser multiusuario y multitarea. Ha influido en numerosos sistemas actuales. **Linux es de tipo Unix**, pero no deriva del código original de Unix. La marca **UNIX** se utiliza para sistemas certificados conforme a la especificación correspondiente.

## Notas relacionadas

- [[Sistemas Operativos/Índice|Índice de Sistemas Operativos]].
