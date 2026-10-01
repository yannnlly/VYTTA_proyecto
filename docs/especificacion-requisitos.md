# Especificación de requisitos · VYTTA

**Sistema:** VYTTA - Sistema web de reservación y gestión de clases  
**Autor:** Luz Yanelly Garduño Paniagua

---

## 1. Propósito y alcance

### Propósito del documento

El propósito de este documento es definir de manera clara los requisitos funcionales y no funcionales de VYTTA, tomando como base la Visión del producto y la información obtenida durante la entrevista.

Este documento servirá como referencia para definir qué debe realizar el sistema, establecer criterios que permitan comprobar el cumplimiento de cada requisito y mantener la relación entre los requisitos, los casos de uso y los elementos del prototipo.

### Alcance del sistema

VYTTA será una aplicación web enfocada en facilitar la **reservación y gestión de clases** dentro del estudio.

Los clientes podrán registrarse, iniciar sesión, consultar clases y lugares disponibles, reservar clases, realizar pagos, cancelar reservaciones y consultar su historial de reservaciones.

Cada clase tendrá una **capacidad máxima de 8 alumnos**. VYTTA deberá mantener actualizada la cantidad de lugares disponibles e impedir nuevas reservaciones cuando una clase alcance los 8 alumnos registrados.

También podrán consultar su **programa de fidelidad**, el cual funcionará mediante un conteo de estrellas relacionado con su constancia y fidelidad con el estudio. Las estrellas podrán aumentar o disminuir de acuerdo con las reglas establecidas por el estudio y podrán relacionarse con promociones o beneficios.

Los clientes también podrán calificar las clases a las que hayan asistido, registrar testimonios sobre su experiencia y consultar testimonios registrados por otros clientes.

Las maestras podrán iniciar sesión, consultar las clases que tienen asignadas, consultar las personas registradas en cada una de sus clases, verificar el estado de pago de las reservaciones y registrar la asistencia de los clientes. De esta manera, antes de comenzar una clase podrán revisar quiénes están registrados y verificar si el pago correspondiente aparece como pagado o pendiente.

El administrador podrá registrar y modificar clases, registrar horarios, registrar maestras y consultar las reservaciones y pagos relacionados con las clases.

### Fuera del alcance

Quedan fuera del alcance de VYTTA las siguientes funciones:

- Desarrollar una aplicación móvil nativa para Android o iOS.
- Generar rutinas de ejercicio personalizadas.
- Realizar seguimiento médico o nutricional.
- Conectar relojes inteligentes u otros dispositivos.
- Impartir clases virtuales mediante videollamada.

Estas funciones quedan fuera del alcance porque VYTTA se enfocará en la reservación y gestión de clases dentro del estudio.

---

## 2. Usuarios y su contexto

Después de realizar la entrevista se pudo entender mejor qué necesita cada tipo de usuario y cuáles son los principales problemas que se presentan actualmente durante la reservación y gestión de clases.

| Usuario | Qué hace hoy sin el sistema | Qué espera del sistema |
| --- | --- | --- |
| **Cliente** | Se comunica por WhatsApp o redes sociales para preguntar por clases, horarios, precios y lugares disponibles. Después espera la confirmación del estudio. | Consultar clases y lugares disponibles. Reservar clases. Realizar pagos. Cancelar reservaciones. Consultar su historial. Consultar su programa de fidelidad. Calificar clases. Registrar testimonios. Consultar testimonios. |
| **Maestra** | Recibe mediante mensajes o listas la información de las clases que tiene asignadas y de las personas que asistirán. También puede necesitar confirmar con el estudio si las reservaciones se encuentran pagadas. Esta información puede no estar actualizada. | Iniciar sesión. Consultar las clases que tiene asignadas. Consultar las personas registradas en cada clase. Verificar si las reservaciones aparecen como pagadas o pendientes y registrar la asistencia de los clientes. |
| **Administrador** | Revisa mensajes, organiza reservaciones, comprueba pagos y lleva el control de los lugares disponibles. | Registrar clases. Modificar clases. Registrar horarios. Registrar maestras. Consultar reservaciones. Consultar pagos y mantener el control de la capacidad máxima de 8 alumnos por clase. |

### Conflictos identificados entre usuarios

Uno de los principales conflictos identificados durante la entrevista se relaciona con las cancelaciones.

El cliente puede necesitar cancelar una reservación, pero el estudio necesita contar con suficiente tiempo para liberar el lugar y permitir que otra persona pueda reservarlo.

Después de la entrevista se estableció que una reservación deberá cancelarse con un mínimo de **3 horas de anticipación** para evitar una penalización.

Cuando el cliente cancele con 3 horas o más de anticipación, el lugar se liberará sin aplicar una penalización.

Cuando el cliente cancele con menos de 3 horas de anticipación, el lugar se liberará, pero se descontará una estrella de su programa de fidelidad y el crédito correspondiente a la clase se registrará como utilizado.

Cuando un cliente tenga una reservación y no se presente a la clase, también se descontará una estrella de su programa de fidelidad.

Otro conflicto identificado es el posible sobrecupo de las clases. Cada clase tendrá una **capacidad máxima de 8 alumnos**, por lo que VYTTA deberá mantener actualizada la cantidad de lugares disponibles.

Cada reservación confirmada ocupará uno de los 8 lugares de la clase. Cuando se alcance la capacidad máxima, el sistema deberá mostrar 0 lugares disponibles e impedir que se registren nuevas reservaciones.

Cuando una reservación sea cancelada, el sistema deberá liberar nuevamente el lugar para que pueda ser reservado por otro cliente.

También se identificó que las maestras necesitan tener información actualizada antes de comenzar una clase. Actualmente pueden depender de mensajes o listas proporcionadas por el estudio, por lo que VYTTA permitirá que consulten directamente sus clases asignadas, las personas registradas y el estado de pago de cada reservación antes de registrar la asistencia.

---

# 3. Requisitos funcionales

## 3.1 Resumen

Los siguientes requisitos representan las funciones que realizará VYTTA. Cada requisito tiene un identificador único y expresa una sola función del sistema.

| ID | Nombre | Prioridad | Origen |
| --- | --- | --- | --- |
| RF-001 | Registrar usuario | Imprescindible | Visión del producto |
| RF-002 | Iniciar sesión | Imprescindible | Visión del producto |
| RF-003 | Consultar clases | Imprescindible | Visión del producto + Entrevista |
| RF-004 | Consultar lugares disponibles | Imprescindible | Entrevista |
| RF-005 | Reservar clase | Imprescindible | Visión del producto + Entrevista |
| RF-006 | Realizar pago | Imprescindible | Visión del producto |
| RF-007 | Cancelar reservación | Imprescindible | Entrevista + regla definida |
| RF-008 | Consultar historial de reservaciones | Importante | Visión del producto |
| RF-009 | Registrar asistencia | Imprescindible | Visión del producto + Entrevista |
| RF-010 | Consultar programa de fidelidad | Importante | Propuesta propia validada en entrevista |
| RF-011 | Calificar clase | Deseable | Visión del producto |
| RF-012 | Registrar testimonio | Importante | Visión del producto + Entrevista |
| RF-013 | Registrar clase | Imprescindible | Visión del producto + Entrevista |
| RF-014 | Modificar clase | Imprescindible | Visión del producto + Entrevista |
| RF-015 | Registrar horario | Imprescindible | Visión del producto + Entrevista |
| RF-016 | Registrar maestra | Imprescindible | Visión del producto + Entrevista |
| RF-017 | Consultar reservaciones | Imprescindible | Visión del producto + Entrevista |
| RF-018 | Consultar pagos | Imprescindible | Visión del producto + Entrevista |
| RF-019 | Consultar paquetes | Importante | Entrevista |
| RF-020 | Consultar promociones | Importante | Entrevista |
| RF-021 | Consultar testimonios | Importante | Entrevista |

---

## 3.2 Fichas

### RF-001 · Registrar usuario

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra un nuevo usuario cuando proporciona los datos obligatorios solicitados para crear una cuenta. |
| **Origen** | Visión del producto. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al ingresar todos los datos obligatorios con valores válidos, el sistema crea la cuenta. Si falta un dato obligatorio, el registro no se completa y el sistema identifica el dato faltante. |
| **Relacionado con** | RF-002, RNF-SEG-001 |

### RF-002 · Iniciar sesión

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema valida las credenciales de una cuenta registrada antes de iniciar una sesión y muestra las funciones correspondientes al tipo de usuario: Cliente, Maestra o Administrador. |
| **Origen** | Visión del producto. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al ingresar credenciales válidas, el sistema inicia la sesión correspondiente y permite acceder únicamente a las funciones autorizadas para ese tipo de usuario. Al ingresar credenciales que no coincidan con una cuenta registrada, el sistema rechaza el acceso. |
| **Relacionado con** | RF-001, RNF-SEG-001 |

### RF-003 · Consultar clases

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra al cliente las clases disponibles con su horario, maestra, duración, precio y cantidad de lugares disponibles. Para una Maestra autenticada, el sistema permite consultar las clases que tiene asignadas. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al consultar una clase disponible como Cliente, el sistema muestra el horario, maestra, duración, precio y cantidad de lugares disponibles de un máximo de 8. Cuando una Maestra consulta sus clases, el sistema muestra únicamente las clases que tiene asignadas con su fecha y horario correspondientes. |
| **Relacionado con** | RF-004, RF-005, RF-009, RF-017, RF-018, RNF-USA-001, RNF-REN-001 |

### RF-004 · Consultar lugares disponibles

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra la cantidad actual de lugares disponibles para cada clase, considerando una capacidad máxima de 8 alumnos. |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Una clase sin reservaciones deberá mostrar 8 lugares disponibles. Después de cada reservación, la disponibilidad disminuye en un lugar. Después de una cancelación, aumenta en un lugar. La cantidad mostrada nunca puede ser menor que 0 ni mayor que 8. |
| **Relacionado con** | RF-003, RF-005, RF-007, RNF-CON-001 |

### RF-005 · Reservar clase

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra una reservación cuando la clase seleccionada tiene al menos un lugar disponible y no ha alcanzado su capacidad máxima de 8 alumnos. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Si existen menos de 8 alumnos registrados, el sistema registra la reservación y disminuye la disponibilidad en un lugar. Cuando existen 8 alumnos registrados, el sistema muestra 0 lugares disponibles e impide registrar una nueva reservación. |
| **Relacionado con** | RF-003, RF-004, RF-006, RNF-CON-001 |

### RF-006 · Realizar pago

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra el pago correspondiente a una clase o paquete cuando la transacción es confirmada. |
| **Origen** | Visión del producto. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Cuando la transacción se confirma correctamente, el pago queda registrado como pagado. Cuando la transacción no se confirma, el pago no cambia al estado pagado. |
| **Relacionado con** | RF-005, RF-018, RF-019, RNF-SEG-001 |

### RF-007 · Cancelar reservación

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema cancela una reservación, libera uno de los 8 lugares de la clase y aplica las reglas establecidas según el tiempo restante para el inicio de la clase. |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Si la cancelación se realiza con 3 horas o más de anticipación, el sistema libera un lugar sin descontar estrellas. Si se realiza con menos de 3 horas, libera el lugar, descuenta una estrella del programa de fidelidad y registra el crédito de la clase como utilizado. La disponibilidad nunca deberá superar los 8 lugares. |
| **Relacionado con** | RF-004, RF-010, RNF-CON-001 |

### RF-008 · Consultar historial de reservaciones

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra las reservaciones realizadas por el cliente con la clase, fecha y estado correspondiente. |
| **Origen** | Visión del producto. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al consultar el historial, se muestran todas las reservaciones asociadas a la cuenta del cliente con su clase, fecha y estado. |
| **Relacionado con** | RF-005, RF-007 |

### RF-009 · Registrar asistencia

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema permite que una Maestra registre el estado de asistencia de cada cliente que tenga una reservación en una de sus clases asignadas. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | La Maestra selecciona una de sus clases asignadas, consulta las personas registradas y guarda el estado de asistencia de cada cliente. Al volver a consultar la clase, el estado guardado deberá mantenerse. La lista no podrá contener más de 8 alumnos registrados. |
| **Relacionado con** | RF-003, RF-005, RF-010, RF-017, RF-018, RNF-CON-001 |

### RF-010 · Consultar programa de fidelidad

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra el programa de fidelidad del cliente con su cantidad actual de estrellas y los beneficios relacionados con ellas. |
| **Origen** | Propuesta propia validada en entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al consultar el programa de fidelidad, se muestra el conteo actual de estrellas del cliente. Después de una acción que genere una penalización, el conteo disminuye exactamente una estrella y muestra el nuevo total. |
| **Relacionado con** | RF-007, RF-009, RF-020 |

### RF-011 · Calificar clase

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra la calificación de una clase únicamente cuando el cliente tiene una asistencia registrada para esa clase. |
| **Origen** | Visión del producto. |
| **Prioridad** | Deseable |
| **Criterio de aceptación** | Si el cliente tiene asistencia registrada, puede guardar una calificación asociada a esa clase. Si no existe asistencia registrada, el sistema impide guardar la calificación. |
| **Relacionado con** | RF-009 |

### RF-012 · Registrar testimonio

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra un testimonio de un cliente únicamente cuando tiene una asistencia registrada para la clase correspondiente. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Si existe una asistencia registrada, el cliente puede escribir y guardar un testimonio asociado a la clase. Si no existe asistencia registrada, el sistema impide guardar el testimonio. |
| **Relacionado con** | RF-009, RF-011, RF-021 |

### RF-013 · Registrar clase

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra una nueva clase con una capacidad máxima de 8 alumnos cuando el administrador proporciona todos los datos obligatorios. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al ingresar todos los datos obligatorios de una clase, el registro queda guardado con una capacidad máxima de 8 alumnos y aparece al consultar las clases. Si falta un dato obligatorio, el sistema no guarda la clase. |
| **Relacionado con** | RF-003, RF-004, RF-015, RF-016 |

### RF-014 · Modificar clase

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema actualiza la información de una clase registrada cuando el administrador confirma una modificación válida. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Después de modificar y confirmar un dato válido, la nueva información se muestra al volver a consultar la clase. La modificación no podrá permitir que una clase supere la capacidad máxima de 8 alumnos. |
| **Relacionado con** | RF-003, RF-013 |

### RF-015 · Registrar horario

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra una fecha y hora para una clase existente. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al registrar una fecha y hora válidas para una clase, el horario queda asociado a la clase seleccionada y se muestra al consultarla. |
| **Relacionado con** | RF-003, RF-013 |

### RF-016 · Registrar maestra

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema registra una maestra cuando el administrador proporciona todos los datos obligatorios. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al ingresar todos los datos obligatorios de la maestra, el registro queda guardado y la maestra aparece entre las opciones disponibles para asignar una clase. |
| **Relacionado con** | RF-013 |

### RF-017 · Consultar reservaciones

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra las reservaciones registradas para una clase. El Administrador puede consultar las reservaciones de las clases registradas y cada Maestra puede consultar las personas registradas únicamente en las clases que tiene asignadas. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al seleccionar una clase, se muestran las reservaciones activas asociadas. Cuando la consulta la realiza una Maestra, el sistema permite consultar únicamente las reservaciones de sus clases asignadas. El número de reservaciones activas nunca podrá ser mayor a 8. Una reservación cancelada deja de aparecer como activa y libera un lugar. |
| **Relacionado con** | RF-003, RF-004, RF-005, RF-007, RF-009, RF-018, RNF-CON-001 |

### RF-018 · Consultar pagos

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra el estado del pago relacionado con una reservación. El Administrador puede consultar los pagos registrados y la Maestra puede verificar el estado de pago de las reservaciones correspondientes a sus clases asignadas. |
| **Origen** | Visión del producto y entrevista. |
| **Prioridad** | Imprescindible |
| **Criterio de aceptación** | Al consultar una reservación, se muestra el estado de pago correspondiente como pagado o pendiente de acuerdo con el registro de la transacción. Cuando la consulta la realiza una Maestra, únicamente puede verificar el estado de pago de los clientes registrados en sus clases asignadas. |
| **Relacionado con** | RF-006, RF-009, RF-017, RNF-SEG-001 |

### RF-019 · Consultar paquetes

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra los paquetes activos disponibles para los clientes. |
| **Origen** | Entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al consultar los paquetes, se muestran todos los paquetes activos con su nombre, precio, cantidad de clases y condiciones de uso. Los paquetes inactivos no se muestran como disponibles. |
| **Relacionado con** | RF-006 |

### RF-020 · Consultar promociones

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra las promociones activas y las condiciones necesarias para obtener cada beneficio. |
| **Origen** | Entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al consultar las promociones, se muestran todas las promociones activas con su beneficio y condiciones. Cuando una promoción dependa del programa de fidelidad, se muestra la cantidad de estrellas necesaria para obtenerla. |
| **Relacionado con** | RF-006, RF-010 |

### RF-021 · Consultar testimonios

| Campo | Contenido |
| --- | --- |
| **Descripción** | El sistema muestra los testimonios registrados por clientes que hayan asistido a una clase. |
| **Origen** | Entrevista. |
| **Prioridad** | Importante |
| **Criterio de aceptación** | Al consultar la sección de testimonios, se muestran todos los testimonios disponibles. Si no existe ningún testimonio registrado, el sistema indica que todavía no hay testimonios disponibles. |
| **Relacionado con** | RF-012 |

---

# 4. Requisitos no funcionales

## 4.1 Resumen

Los requisitos no funcionales se clasifican utilizando las claves de atributos de calidad establecidas en la Guía de redacción de requisitos.

| ID | Atributo | Nombre | Prioridad | Origen |
| --- | --- | --- | --- | --- |
| RNF-REN-001 | Rendimiento | Mostrar información de clases | Importante | Derivado del tipo de sistema |
| RNF-SEG-001 | Seguridad | Restringir acceso por usuario | Imprescindible | Derivado del tipo de sistema |
| RNF-USA-001 | Usabilidad | Completar reservación | Imprescindible | Entrevista + tipo de sistema |
| RNF-CON-001 | Confiabilidad | Mantener disponibilidad de lugares | Imprescindible | Entrevista |

## 4.2 Fichas

### Rendimiento

#### RNF-REN-001 · Mostrar información de clases

| Campo | Contenido |
| --- | --- |
| **Atributo de calidad** | Rendimiento |
| **Descripción** | La información de las clases disponibles se muestra en un máximo de 3 segundos después de solicitar la consulta. |
| **Métrica** | Tiempo transcurrido entre la solicitud de consulta y el despliegue completo de la información, con hasta 100 clases registradas. El tiempo máximo aceptado será de 3 segundos. |
| **Origen** | Derivado del tipo de sistema: aplicación web de consulta y reservación de clases. |
| **Prioridad** | Importante |
| **Por qué importa** | Los clientes necesitan consultar las clases de manera rápida para realizar una reservación y las maestras necesitan consultar sus clases asignadas sin depender de mensajes. |
| **Afecta a** | RF-003, RF-004, RF-005 |

### Seguridad

#### RNF-SEG-001 · Restringir acceso por usuario

| Campo | Contenido |
| --- | --- |
| **Atributo de calidad** | Seguridad |
| **Descripción** | El sistema rechaza el 100 % de los intentos de acceso a funciones que no correspondan al tipo de usuario autenticado. |
| **Métrica** | En 10 intentos de acceso no autorizado por cada tipo de usuario, los 10 intentos deberán ser rechazados. |
| **Origen** | Derivado del tipo de sistema y de la existencia de los roles Cliente, Maestra y Administrador definidos en la Visión del producto. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Evita que un usuario tenga acceso a información o funciones que corresponden a otro tipo de usuario. En el caso de las maestras, limita la consulta de reservaciones y pagos a las clases que tengan asignadas. |
| **Afecta a** | RF-002, RF-003, RF-009, RF-013, RF-014, RF-015, RF-016, RF-017, RF-018 |

### Usabilidad

#### RNF-USA-001 · Completar reservación

| Campo | Contenido |
| --- | --- |
| **Atributo de calidad** | Usabilidad |
| **Descripción** | Al menos 9 de cada 10 usuarios de prueba completan una reservación sin recibir ayuda externa. |
| **Métrica** | Prueba con 10 personas que realicen el proceso desde consultar una clase hasta confirmar la reservación. Al menos 9 deberán completarlo sin ayuda. |
| **Origen** | Entrevista y derivado del tipo de sistema. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Si el proceso resulta complicado, los clientes podrían continuar realizando las reservaciones mediante mensajes en lugar de utilizar VYTTA. |
| **Afecta a** | RF-003, RF-004, RF-005 |

### Confiabilidad

#### RNF-CON-001 · Mantener disponibilidad de lugares

| Campo | Contenido |
| --- | --- |
| **Atributo de calidad** | Confiabilidad |
| **Descripción** | La cantidad de lugares disponibles coincide con el número real de reservaciones registradas, considerando una capacidad máxima de 8 alumnos por clase. |
| **Métrica** | Durante una prueba de 20 operaciones consecutivas de reservación y cancelación, las 20 deberán producir la cantidad correcta de lugares disponibles. El sistema nunca deberá mostrar menos de 0 ni más de 8 lugares disponibles y deberá impedir que una clase tenga más de 8 reservaciones activas. |
| **Origen** | Entrevista. |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Una disponibilidad incorrecta puede ocasionar sobrecupos o impedir que un cliente reserve un lugar que realmente se encuentra disponible. |
| **Afecta a** | RF-004, RF-005, RF-007, RF-009, RF-017 |

---

# 5. Casos de uso

| ID | Caso de uso | Actor principal | Requisitos relacionados |
| --- | --- | --- | --- |
| CU-01 | Registrar usuario | Cliente | RF-001 |
| CU-02 | Iniciar sesión | Cliente, Maestra, Administrador | RF-002 |
| CU-03 | Consultar clases | Cliente, Maestra | RF-003, RF-004, RF-019, RF-020, RF-021 |
| CU-04 | Reservar clase | Cliente | RF-004, RF-005, RF-006 |
| CU-05 | Cancelar reservación | Cliente | RF-004, RF-007, RF-008, RF-010 |
| CU-06 | Gestionar asistencia | Maestra | RF-009, RF-017, RF-018 |
| CU-07 | Consultar programa de fidelidad | Cliente | RF-010, RF-011, RF-012, RF-020 |
| CU-08 | Gestionar clases | Administrador | RF-013, RF-014, RF-015, RF-016, RF-017, RF-018 |

---

## CU-04 · Reservar clase

**Actor principal:** Cliente

**Objetivo:** Registrar un lugar para el cliente en una clase disponible, respetando la capacidad máxima de 8 alumnos.

### Precondiciones

- El cliente tiene una cuenta registrada.
- El cliente ha iniciado sesión.
- La clase se encuentra registrada en VYTTA.
- La clase tiene al menos un lugar disponible.
- La clase no ha alcanzado la capacidad máxima de 8 alumnos.

### Escenario principal

1. El cliente consulta las clases disponibles.
2. El sistema muestra la información de las clases.
3. El cliente selecciona una clase.
4. El sistema muestra la información de la clase y la cantidad de lugares disponibles.
5. El cliente solicita reservar la clase.
6. El sistema comprueba que la clase tiene menos de 8 alumnos registrados.
7. El cliente realiza el pago correspondiente.
8. El sistema confirma la transacción.
9. El sistema registra la reservación.
10. El sistema disminuye en uno la cantidad de lugares disponibles.
11. El sistema muestra la reservación registrada al cliente.

### Flujo alterno 1 · Clase sin lugares disponibles

1. El cliente selecciona una clase.
2. El sistema comprueba la cantidad de alumnos registrados.
3. El sistema detecta que la clase ya tiene 8 alumnos registrados.
4. El sistema muestra 0 lugares disponibles.
5. El sistema impide registrar una nueva reservación.
6. El sistema informa al cliente que la clase ya no tiene lugares disponibles.

### Flujo alterno 2 · Pago no confirmado

1. El cliente inicia el proceso correspondiente al pago.
2. La transacción no es confirmada.
3. El sistema no registra el pago como pagado.
4. La reservación no se confirma.
5. El sistema informa al cliente que el pago no pudo ser completado.

### Postcondición

Si el proceso se completa correctamente, la reservación queda registrada y la cantidad de lugares disponibles disminuye en uno.

El número total de reservaciones activas de una clase nunca podrá superar los **8 alumnos**.

**Requisitos relacionados:** RF-003, RF-004, RF-005, RF-006, RNF-USA-001 y RNF-CON-001.

---

# 6. Trazabilidad

| Requisito | Origen | Caso de uso | Elemento del prototipo |
| --- | --- | --- | --- |
| RF-001 | Visión del producto | CU-01 Registrar usuario | Pantalla de registro |
| RF-002 | Visión del producto | CU-02 Iniciar sesión | Pantalla de inicio de sesión |
| RF-003 | Visión + Entrevista | CU-03 Consultar clases | Pantalla de clases |
| RF-004 | Entrevista | CU-03 Consultar clases / CU-04 Reservar clase / CU-05 Cancelar reservación | Indicador de lugares disponibles de un máximo de 8 |
| RF-005 | Visión + Entrevista | CU-04 Reservar clase | Pantalla de reservación |
| RF-006 | Visión del producto | CU-04 Reservar clase | Pantalla de pago |
| RF-007 | Entrevista | CU-05 Cancelar reservación | Mis reservaciones |
| RF-008 | Visión del producto | CU-05 Cancelar reservación | Historial de reservaciones |
| RF-009 | Visión + Entrevista | CU-06 Gestionar asistencia | Lista de asistentes con máximo de 8 alumnos |
| RF-010 | Propuesta propia validada en entrevista | CU-07 Consultar programa de fidelidad / CU-05 Cancelar reservación | Programa de fidelidad |
| RF-011 | Visión del producto | CU-07 Consultar programa de fidelidad | Calificación de clase |
| RF-012 | Visión + Entrevista | CU-07 Consultar programa de fidelidad | Formulario de testimonio |
| RF-013 | Visión + Entrevista | CU-08 Gestionar clases | Panel del administrador |
| RF-014 | Visión + Entrevista | CU-08 Gestionar clases | Edición de clase |
| RF-015 | Visión + Entrevista | CU-08 Gestionar clases | Registro de horario |
| RF-016 | Visión + Entrevista | CU-08 Gestionar clases | Registro de maestra |
| RF-017 | Visión + Entrevista | CU-06 Gestionar asistencia / CU-08 Gestionar clases | Lista de reservaciones con máximo de 8 alumnos |
| RF-018 | Visión + Entrevista | CU-06 Gestionar asistencia / CU-08 Gestionar clases | Estado de pago de reservaciones |
| RF-019 | Entrevista | CU-03 Consultar clases | Sección de paquetes |
| RF-020 | Entrevista | CU-03 Consultar clases / CU-07 Consultar programa de fidelidad | Sección de promociones |
| RF-021 | Entrevista | CU-03 Consultar clases | Sección de testimonios |

---
