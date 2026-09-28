# Especificación de requisitos · VYTTA

**Sistema:** VYTTA 


**Autor:** Luz Yanelly Garduño Paniagua  


---

## 1. Propósito y alcance

### Propósito del documento
El proposito de este documento es poder definir de una manera mas clara todas las especificaciones que debe de tener VYTTA y las funciones que debe de  realizar a los distintos tipos de usuarios dentro de VYTTA

Para realizarlo se tomó en cuenta la Visión del producto que se hizo anteriormente y también la información que se obtuvo durante la entrevista. 
### Alcance del sistema

VYTTA será una aplicación web que ayudará a llevar de una manera más organizada las reservaciones de las clases del estudio.

Los clientes podrán crear una cuenta, iniciar sesión, consultar las clases disponibles, ver los horarios, maestras, precios y lugares disponibles. También podrán reservar una clase, realizar su pago, cancelar una reservación y consultar sus próximas clases y su historial de fidelidad dentro del estudio.

Las maestras podrán consultar las clases que tienen asignadas, ver qué personas están registradas, los lugares que cada persona va a ocupar, llevar el control de las asistencias, y verificar que los usuarios ya hayan pagado su clase antes de impartirla.

Por otro lado, el administrador tendrá un control más completo del sistema y podrá administrar las clases, horarios, maestras, reservaciones, pagos, cancelaciones y asistencias; las asistencias no solo serán de la parte de los usuario sino también de  las maestras.

VYTTA también tendrá un sistema de estrellas que servirá para reconocer a los clientes que son constantes y responsables con las reservaciones que realizan.

### Fuera del alcance

Al momento de pagar un paquete o de ser usuarios VYTTA NO CONTARA con lo siguiente:

- Una aplicación móvil para Android o iOS.
- Rutinas de ejercicio personalizadas.
- Seguimiento médico o nutricional.
- Conexión con relojes inteligentes u otros dispositivos.
- Clases virtuales por videollamada.

Estas funciones quedan fuera porque VYTTA está enfocado principalmente en mejorar la manera en la que se reservan y administran las clases dentro del estudio.

---

## 2. Usuarios y su contexto

Después de realizar la entrevista se pudo entender mejor qué necesita cada tipo de usuario y qué problemas tienen actualmente al organizar las reservaciones.

| Usuario | Qué hace hoy sin el sistema | Qué espera del sistema |
|---|---|---|
| **Cliente** | Se comunica por WhatsApp o redes sociales para preguntar por horarios, precios y lugares disponibles. Después tiene que esperar a que el estudio le confirme su lugar. | Poder consultar las clases disponibles ne cualquier momento , reservar, pagar, cancelar y revisar sus reservaciones de una manera sencilla. También podrá consultar sus estrellas, y sus premios a ganar por mantener la fidelidad o por ser un usuario reciente. |
| **Maestra** | Recibe por mensajes o visualiza las listas de información de las personas que asistirán a sus clases, pero esta información puede no estar actualizada. | Poder consultar sus clases, horarios y las personas que están registradas, además de llevar el control de asistencia y visualizar si los usuarios ya cuentan con la clase pagada o aun esta en adeudos . |
| **Administrador** | Tiene que revisar mensajes, organizar las reservaciones, comprobar pagos y llevar el control de los lugares disponibles o lugares recientemente cancelados. | Poder tener en un mismo lugar el control de las clases, horarios, usuarios, reservaciones, pagos, cancelaciones y asistencias actualizadas en tiempo y hora. |

### Conflictos identificados entre usuarios

Uno de los conflictos que se pueden presentar es con las cancelaciones.

Por una parte, el cliente puede necesitar cancelar una clase, pero también es importante que el estudio tenga tiempo para liberar ese lugar y que otra persona pueda reservarlo.

Por esta razón, se decidió que los clientes podrán cancelar una reservación sin recibir una penalización siempre que lo hagan mínimo 3 horas antes de que comience la clase.

Si cancelan cuando faltan menos de 3 horas, perderán una estrella y el crédito de esa clase se tomará como utilizado. Lo mismo sucederá si reservaron una clase y no se presentan.

Otro de los conflictos que se presentan son la sobre venta de los cupos dentro del estudio.

Por una parte las maestras del administrados pueden perder comunicación con las clases que ya se encuentran vendidas y las restantes, puede causar confusión al momento de que esta se encuentre comenzando.

Si se encuentra actualizado en tiempo y forma como se administran las clases de cada horario esto puede agilizar y evitar que esto suceda.

---

## 3. Requisitos funcionales

### 3.1 Resumen

| ID | Nombre | Prioridad | Origen |
|---|---|---|---|
| RF-001 | Registro e inicio de sesión | Imprescindible | Visión del producto |
| RF-002 | Consulta de clases | Imprescindible | Visión del producto + Entrevista |
| RF-003 | Consulta de lugares disponibles | Imprescindible | Entrevista |
| RF-004 | Reservación de clase | Imprescindible | Visión del producto + Entrevista |
| RF-005 | Pago de reservación | Imprescindible | Visión del producto |
| RF-006 | Cancelación de reservación | Imprescindible | Entrevista + regla definida |
| RF-007 | Historial de reservaciones | Importante | Visión del producto |
| RF-008 | Registro de asistencia | Imprescindible | Visión del producto + Entrevista |
| RF-009 | Sistema de estrellas | Importante | Visión del producto + Entrevista |
| RF-010 | Calificaciones y testimonios | Deseable | Visión del producto |
| RF-011 | Administración de clases | Imprescindible | Visión del producto + Entrevista |
| RF-012 | Paquetes y promociones | Importante | Entrevista |

### 3.2 Fichas

#### RF-001 · Registro e inicio de sesión

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema permitirá que los usuarios puedan crear una cuenta e iniciar sesión para entrar a VYTTA. |
| **Origen** | Visión del producto. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Si el usuario llena correctamente todos los datos necesarios podrá crear su cuenta e iniciar sesión. Si falta algún dato o es incorrecto, el sistema deberá indicarlo y no permitirá continuar hasta corregirlo. |
| **Relacionado con** | RNF-SEG-001 |

#### RF-002 · Consulta de clases

| Campo | Contenido |
|---|---|
| **Descripción** | El cliente podrá consultar las clases disponibles y ver información como el tipo de clase, horario, maestra, duración, precio,  lugares disponibles y su testimonio de las alumnas que ya hayan tomado esa clase. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Cuando el cliente seleccione una clase deberá poder ver toda su información antes de decidir si quiere reservarla o adquirirla. |
| **Relacionado con** | RF-003, RF-004, RNF-USA-001 |

#### RF-003 · Consulta de lugares disponibles

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema mostrará cuántos lugares quedan disponibles en cada clase y en cuales les gustaría ocupar a cada usuario . |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Cada vez que una persona reserve o cancele, la cantidad de lugares disponibles deberá actualizarse. Si ya no existen lugares, se deberá mostrar que la clase está llena y no se podrán realizar más reservaciones. |
| **Relacionado con** | RF-002, RF-004, RF-006, RNF-CON-001 |

#### RF-004 · Reservación de clase

| Campo | Contenido |
|---|---|
| **Descripción** | El cliente podrá reservar un lugar en cualquiera de las clases que todavía tenga lugares disponibles. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Cuando el cliente realice correctamente una reservación, el sistema deberá guardar su lugar y disminuirla cantidad de lugares disponibles. Si la clase está llena, no deberá permitir otra reservación. |
| **Relacionado con** | RF-003, RF-005, RNF-CON-001 |

#### RF-005 · Pago de reservación

| Campo | Contenido |
|---|---|
| **Descripción** | El cliente podrá realizar el pago de una clase o de alguno de los paquetes disponibles. |
| **Origen** | Visión del producto. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Cuando el pago se realice correctamente, deberá aparecer como confirmado. Si existe algún problema y el pago no se completa, no deberá aparecer como pagado. |
| **Relacionado con** | RF-004, RF-012, RNF-SEG-001 |

#### RF-006 · Cancelación de reservación

| Campo | Contenido |
|---|---|
| **Descripción** | El cliente podrá cancelar una reservación. Si cancela mínimo 4 horas antes de la clase no recibirá ninguna penalización. |
| **Origen** | Entrevista y regla definida después de la entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Si el cliente cancela con 4 horas o más de anticipación, su lugar se liberará sin perder una estrella. Si cancela cuando faltan menos de 4 horas, el lugar también se liberará, pero perderá una estrella y el crédito de la clase se tomará como utilizado. |
| **Relacionado con** | RF-003, RF-009 |

#### RF-007 · Historial de reservaciones

| Campo | Contenido |
|---|---|
| **Descripción** | El cliente podrá consultar las clases que tiene reservadas y también las clases en su historial. |
| **Origen** | Visión del producto. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al entrar a su historial, el cliente deberá poder ver sus reservaciones y conocer la fecha, la clase y el estado de cada una. |
| **Relacionado con** | RF-004, RF-006 |

#### RF-008 · Registro de asistencia

| Campo | Contenido |
|---|---|
| **Descripción** | Las maestras podrán registrar la asistencia de las personas inscritas en sus clases. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | La maestra podrá entrar a una de sus clases, consultar la lista de personas registradas y marcar quién asistió y quién no asistió. |
| **Relacionado con** | RF-009 |

#### RF-009 · Sistema de estrellas

| Campo | Contenido |
|---|---|
| **Descripción** | VYTTA tendrá un sistema de estrellas que servirá para reconocer a los clientes que son constantes y responsables con sus reservaciones. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Cada cliente nuevo comenzará con una estrella. Podrá aumentar sus estrellas por su constancia y participación. Si cancela faltando menos de 4 horas para la clase o no se presenta, perderá una estrella. Cada cinco estrellas acumuladas servirán para identificar un nivel de confiabilidad del cliente. |
| **Relacionado con** | RF-006, RF-008, RF-010, RF-012 |

#### RF-010 · Calificaciones y testimonios

| Campo | Contenido |
|---|---|
| **Descripción** | Los clientes podrán calificar las clases a las que asistieron y también podrán dejar un testimonio. |
| **Origen** | Visión del producto. |
| **Prioridad** | Deseable |
| **Criterio de aceptación** | Después de asistir a una clase, el cliente podrá calificarla y tendrá la opción de escribir un testimonio sobre su experiencia. |
| **Relacionado con** | RF-008, RF-009 |

#### RF-011 · Administración de clases

| Campo | Contenido |
|---|---|
| **Descripción** | El administrador podrá llevar el control de las clases, horarios, maestras, capacidad y reservaciones. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | El administrador podrá consultar y modificar la información de las clases, además de revisar sus reservaciones, lugares disponibles, pagos y asistencias. |
| **Relacionado con** | RF-002, RF-003, RF-004, RF-008 |

#### RF-012 · Paquetes y promociones

| Campo | Contenido |
|---|---|
| **Descripción** | Los clientes podrán consultar los diferentes paquetes, precios y promociones que tenga disponibles el estudio. |
| **Origen** | Entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al entrar a la sección correspondiente, el cliente deberá poder consultar los paquetes y promociones disponibles, además de conocer su precio y las condiciones para utilizarlos. |
| **Relacionado con** | RF-005, RF-009 |

---

## 4. Requisitos no funcionales

### 4.1 Resumen

| ID | Atributo | Nombre | Prioridad | Origen |
|---|---|---|---|---|
| RNF-SEG-001 | Seguridad | Control de acceso | Imprescindible | Tipo de sistema |
| RNF-DIS-001 | Disponibilidad | Disponibilidad del sistema | Importante | Tipo de sistema |
| RNF-USA-001 | Usabilidad | Facilidad de uso | Imprescindible | Entrevista |
| RNF-CON-001 | Confiabilidad | Control correcto de lugares | Imprescindible | Entrevista |
| RNF-COM-001 | Compatibilidad | Uso en diferentes dispositivos | Importante | Visión del producto |

### 4.2 Fichas

#### RNF-SEG-001 · Control de acceso

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Seguridad |
| **Descripción** | Cada usuario solamente podrá entrar a las funciones que le corresponden dependiendo de si es cliente, maestra o administrador. |
| **Métrica** | Durante las pruebas, ninguno de los tres tipos de usuario deberá poder entrar a funciones que pertenezcan únicamente a otro tipo de usuario. |
| **Origen** | Tipo de sistema y Visión del producto. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | No todos los usuarios deben tener acceso a la misma información ni realizar las mismas acciones dentro de VYTTA. |
| **Afecta a** | RF-001, RF-011 |

#### RNF-DIS-001 · Disponibilidad del sistema

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Disponibilidad |
| **Descripción** | VYTTA deberá estar disponible la mayor parte del tiempo para que los clientes puedan consultar y reservar clases cuando lo necesiten. |
| **Métrica** | El sistema deberá tener por lo menos un 99 % de disponibilidad mensual, sin contar los mantenimientos programados. |
| **Origen** | Tipo de sistema. |
| **Prioridad** | Importante |
| **Por qué importa** | Si la página no está disponible, los clientes no podrán consultar horarios ni realizar sus reservaciones. |
| **Afecta a** | RF-002, RF-003, RF-004 |

#### RNF-USA-001 · Facilidad de uso

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Usabilidad |
| **Descripción** | Consultar y reservar una clase deberá ser sencillo y fácil de entender para los clientes. |
| **Métrica** | En una prueba con 10 personas, por lo menos 9 deberán poder buscar una clase y completar una reservación sin necesitar ayuda. |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Si VYTTA es difícil de utilizar, los clientes podrían preferir seguir haciendo sus reservaciones por WhatsApp. |
| **Afecta a** | RF-002, RF-004 |

#### RNF-CON-001 · Control correcto de lugares

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Confiabilidad |
| **Descripción** | Los lugares disponibles que aparezcan en VYTTA deberán coincidir con las reservaciones realizadas. |
| **Métrica** | Durante las pruebas se realizarán 20 reservaciones y cancelaciones. Después de cada operación, la cantidad de lugares mostrada deberá coincidir con la cantidad real de lugares disponibles y nunca superar la capacidad de la clase. |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Uno de los problemas que se busca solucionar con VYTTA es evitar los sobrecupos y la confusión sobre cuántos lugares quedan disponibles. |
| **Afecta a** | RF-003, RF-004, RF-006 |

#### RNF-COM-001 · Uso en diferentes dispositivos

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Compatibilidad |
| **Descripción** | VYTTA deberá poder utilizarse desde una computadora, tableta o celular por medio de un navegador web. |
| **Métrica** | Durante las pruebas, las funciones principales deberán poder utilizarse correctamente en pantallas de celular, tableta y computadora sin que la información importante quede fuera de la pantalla. |
| **Origen** | Visión del producto. |
| **Prioridad** | Importante |
| **Por qué importa** | No todos los clientes van a entrar a VYTTA desde el mismo tipo de dispositivo. |
| **Afecta a** | RF-001, RF-002, RF-004, RF-007 |

---

## 5. Casos de uso

A partir de los requisitos anteriores se identificaron los siguientes casos de uso principales:

| ID | Caso de uso |
|---|---|
| CU-01 | Registrarse e iniciar sesión |
| CU-02 | Consultar clases |
| CU-03 | Reservar una clase |
| CU-04 | Realizar pago |
| CU-05 | Cancelar reservación |
| CU-06 | Consultar reservaciones |
| CU-07 | Registrar asistencia |
| CU-08 | Consultar estrellas |
| CU-09 | Calificar una clase |
| CU-10 | Administrar clases |
| CU-11 | Consultar paquetes y promociones |

---

## 6. Trazabilidad

| Requisito | Origen | Caso de uso | Elemento del prototipo |
|---|---|---|---|
| RF-001 | Visión del producto | CU-01 Registrarse e iniciar sesión | Pantalla de registro e inicio de sesión |
| RF-002 | Visión del producto + Entrevista | CU-02 Consultar clases | Pantalla de clases |
| RF-003 | Entrevista | CU-02 Consultar clases | Lugares disponibles de la clase |
| RF-004 | Visión del producto + Entrevista | CU-03 Reservar una clase | Pantalla de detalle y reservación |
| RF-005 | Visión del producto | CU-04 Realizar pago | Pantalla de pago |
| RF-006 | Entrevista + regla definida | CU-05 Cancelar reservación | Pantalla de mis reservaciones |
| RF-007 | Visión del producto | CU-06 Consultar reservaciones | Historial de clases |
| RF-008 | Visión del producto + Entrevista | CU-07 Registrar asistencia | Lista de asistentes |
| RF-009 | Visión del producto + Entrevista | CU-08 Consultar estrellas | Perfil y estrellas |
| RF-010 | Visión del producto | CU-09 Calificar una clase | Pantalla de calificación |
| RF-011 | Visión del producto + Entrevista | CU-10 Administrar clases | Panel del administrador |
| RF-012 | Entrevista | CU-11 Consultar paquetes y promociones | Pantalla de paquetes y promociones |

---

## 7. Registro de cambios

| Fecha | Requisito | Qué cambió | Por qué |
|---|---|---|---|
| 10/09/2026 | Documento | Se creó la primera versión de la especificación de requisitos de VYTTA. | Era necesario definir de una manera más clara las funciones y necesidades del sistema. |
| 21/09/2026 | RF-002 | Se agregó más información que el cliente podrá consultar antes de reservar una clase. | Durante la entrevista se vio que un cliente necesita conocer información como el horario, maestra, duración, precio y lugares disponibles. |
| 21/09/2026 | RF-006 | Se estableció que una cancelación deberá realizarse mínimo 4 horas antes para no recibir una penalización. | La regla de cancelación todavía no estaba completamente definida. |
| 21/09/2026 | RF-009 | Se mantuvo el sistema de estrellas y se definió mejor cómo se relacionará con las cancelaciones e inasistencias. | Durante la entrevista se consideró que las estrellas podían ser una buena forma de reconocer a los clientes constantes y diferenciar a VYTTA. |
| 21/09/2026 | RF-012 | Se agregaron los paquetes y promociones. | Durante la entrevista se identificó que los clientes también necesitan conocer estas opciones antes de reservar. |

---
