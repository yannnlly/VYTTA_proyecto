# Visión del producto

**Autor:** Luz Yanelly Garduño Paniagua
**Fecha de la última versión:** 1 de septiembre de 2026
**Repositorio:** Proyecto VYTTA

---

## 1. Descripción del sistema

**Nombre del sistema:**
VYTTA — Sistema web de reservación y gestión de clases de Barre

**Descripción:**
VYTTA es una aplicación web que permite a las personas consultar y reservar clases de Barre desde un navegador web. Los usuarios podrán consultar las clases disponibles, horarios, maestras y lugares disponibles, realizar el pago de sus reservaciones y consultar su historial de clases.

Las maestras podrán consultar la información de sus clases, conocer a las personas inscritas y registrar la asistencia. El administrador podrá gestionar usuarios, clases, horarios, maestras, pagos y reservaciones.

Además, VYTTA contará con un sistema de estrellas que permitirá reconocer la constancia y confiabilidad de los usuarios de acuerdo con su asistencia, cancelaciones y participación en la plataforma.

---

## 2. Problema y usuarios

**El problema:**

Actualmente, la reservación de clases se realiza principalmente mediante un grupo de WhatsApp y las redes sociales del estudio. Esto provoca diferentes problemas, ya que algunos mensajes pueden perderse y, en ocasiones, las clases pueden sobre-venderse porque no todas las instructoras cuentan con la misma lista o agenda de reservaciones.

También puede suceder que algunas reservaciones no se registren correctamente o que exista confusión sobre quién reservó primero cuando los lugares son limitados.

Además, el establecimiento puede tener dificultades para mantener un registro organizado de los pagos, personas inscritas, cancelaciones y asistencias.

VYTTA busca solucionar este problema centralizando las reservaciones en una sola plataforma, donde los usuarios puedan consultar la disponibilidad en tiempo real, reservar y pagar sus clases, mientras que las maestras y el administrador puedan llevar un mejor control de la información.

**Cómo se resuelve hoy sin el sistema:**

Sin VYTTA, los usuarios se comunican con el estudio mediante WhatsApp y redes sociales para preguntar por horarios, precios y lugares disponibles.

Después de confirmar la disponibilidad, el usuario realiza el pago mediante transferencia, efectivo u otro método establecido por el establecimiento. Posteriormente, el personal debe revisar manualmente los mensajes, identificar quién reservó primero, confirmar los lugares y registrar las reservaciones.

Este proceso puede generar mensajes perdidos, errores en los registros, sobrecupos, confusión entre las reservaciones y dificultad para conocer en tiempo real cuántos lugares quedan disponibles.

**Usuarios del sistema:**

| Tipo de usuario       | Qué necesita del sistema                                                                                                                                                                             | Qué le preocupa                                                                                                                                       |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Usuario / Cliente** | Consultar clases, horarios y lugares disponibles; reservar y pagar clases; cancelar reservaciones; consultar su historial; calificar clases; dejar testimonios y obtener estrellas de confiabilidad. | Que su reservación sea correcta, que exista disponibilidad real, que el pago sea seguro y que sus estrellas reflejen correctamente su comportamiento. |
| **Maestra**           | Consultar sus clases asignadas, conocer las personas inscritas, consultar los lugares disponibles, registrar asistencias y consultar calificaciones y testimonios de sus clases.                     | Tener información actualizada sobre sus grupos y evitar confusiones con los horarios, asistentes o reservaciones.                                     |
| **Administrador**     | Gestionar usuarios, clases, horarios, maestras, capacidad, reservaciones, pagos, cancelaciones, calificaciones y estadísticas del sistema.                                                           | Mantener el control de la operación, evitar sobrecupos y tener información confiable sobre pagos y reservaciones.                                     |

**Un conflicto entre usuarios:**

Puede existir un conflicto entre el usuario y el administrador cuando una persona reserva una clase y posteriormente necesita cancelar.

El usuario puede querer tener flexibilidad para cancelar su reservación, mientras que el administrador necesita evitar que un lugar permanezca ocupado innecesariamente y que otra persona pierda la oportunidad de utilizarlo.

Para solucionar este conflicto, VYTTA establecerá reglas de cancelación. Si el usuario cancela con suficiente anticipación, podrá recuperar el crédito correspondiente y no perderá una estrella. En cambio, si cancela fuera del tiempo permitido o no se presenta a la clase, el crédito podrá considerarse utilizado y podrá perder una estrella de confiabilidad.

---

## 3. Alcance

### Dentro del alcance

* Registro e inicio de sesión de usuarios, maestras y administradores.
* Consulta de clases, horarios, maestras y lugares disponibles.
* Reservación y cancelación de clases.
* Consulta del precio de las clases y realización de pagos mediante Stripe.
* Control de la capacidad de las clases para evitar sobrecupos.
* Consulta del historial de reservaciones y asistencias.
* Registro de asistencia por parte de las maestras.
* Calificación de las clases y registro de testimonios.
* Sistema de estrellas para reconocer la constancia y confiabilidad de los usuarios.
* Administración de usuarios, clases, horarios, maestras y reservaciones por parte del administrador.
* Acceso mediante una Web App responsiva desde computadora, tablet o celular.

### Explícitamente fuera del alcance

* Aplicación móvil nativa para Android o iOS.
* Rutinas de ejercicio personalizadas.
* Seguimiento médico o nutricional.
* Integración con relojes inteligentes u otros dispositivos.
* Clases virtuales por videollamada.
* Venta de productos físicos.

**Por qué queda fuera:**

Estas funciones no son necesarias para resolver el problema principal de VYTTA, que es organizar y facilitar la reservación y administración de las clases de Barre. Dejarlas fuera permite que el proyecto se concentre en sus funciones principales y sea más sencillo de desarrollar.

---

## 4. Tipo de sistema y restricciones

**Tipo de sistema:**

**Web **

**Por qué es de ese tipo:**

VYTTA es una **Web App** porque sus funcionalidades estarán disponibles mediante un navegador web y no será necesario instalar una aplicación móvil independiente.

Los usuarios podrán consultar clases, realizar reservaciones y efectuar pagos desde diferentes dispositivos. Las maestras podrán consultar sus clases y registrar asistencias, mientras que el administrador tendrá acceso a las funciones necesarias para gestionar el sistema.



**Atributos de calidad que impone:**

| Atributo           | Por qué importa en mi caso                                                                                 | Qué pasa si no se cumple                                                                               |
| ------------------ | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Seguridad**      | VYTTA manejará cuentas de usuarios y pagos, por lo que debe proteger la información y controlar el acceso. | Podrían existir accesos no autorizados, pérdida de información o problemas relacionados con los pagos. |
| **Disponibilidad** | Los usuarios necesitan consultar horarios y reservar clases cuando lo necesiten.                           | Los usuarios podrían no poder reservar y el establecimiento podría perder oportunidades de venta.      |
| **Usabilidad**     | La plataforma debe ser sencilla para encontrar una clase, reservarla y realizar el pago.                   | Los usuarios podrían abandonar el proceso y volver a reservar por WhatsApp.                            |
| **Confiabilidad**  | La información sobre lugares disponibles, reservaciones, pagos y asistencias debe ser correcta.            | Podrían generarse sobrecupos, errores en pagos o problemas con las asistencias.                        |
| **Compatibilidad** | VYTTA debe funcionar en diferentes navegadores y tamaños de pantalla.                                      | Algunos usuarios podrían tener problemas para utilizar la plataforma.                                  |

**Reglas de negocio :**

1. **Una clase no puede superar su capacidad máxima.** Cuando todos los lugares estén ocupados, el sistema no permitirá nuevas reservaciones.

2. **Un usuario debe tener una cuenta para realizar una reservación.** Esto permitirá asociar cada reservación con una persona específica.

3. **Una reservación debe estar asociada a un usuario y a una clase específica.** Esto permitirá conocer quién reservó y a qué clase asistirá.

4. **Las cancelaciones deben respetar un periodo establecido.** Las cancelaciones realizadas con anticipación no penalizarán al usuario, mientras que las cancelaciones fuera del periodo permitido podrán afectar su puntuación.

5. **Un usuario nuevo comienza con una estrella.** Podrá obtener estrellas por asistir constantemente a sus clases y participar mediante testimonios.

6. **El usuario puede perder estrellas por cancelaciones de último momento o inasistencias.**

7. **Cada cinco estrellas acumuladas permitirán identificar un nivel de confiabilidad.** Esto permitirá reconocer a los usuarios que mantienen un comportamiento constante y responsable.

8. **Los permisos dependen del tipo de usuario.** Los clientes, maestras y administradores tendrán diferentes funciones dentro del sistema.

9. **Cuando una clase requiera pago anticipado, la reservación deberá contar con un pago confirmado.** Esto evita mantener lugares reservados sin confirmar la transacción.

---

## 5. Ciclo de vida elegido

**Modelo elegido:**

**Ágil**

**Por qué le conviene a este proyecto:**

Se eligió el modelo **Ágil** porque VYTTA puede tener cambios durante su desarrollo y sus funcionalidades pueden mejorar conforme el equipo reciba comentarios de los usuarios.

El proyecto puede desarrollarse por partes, comenzando con funciones principales como el registro, consulta de clases y reservaciones, para después agregar funciones como pagos, cancelaciones, asistencia y el sistema de estrellas.

También es importante que el usuario esté presente durante el desarrollo, ya que sus comentarios pueden ayudar a identificar qué partes de la plataforma son fáciles de utilizar y cuáles necesitan cambios.

Por ejemplo, después de probar VYTTA se podría determinar que es necesario modificar la forma en que se muestran los horarios, cambiar las reglas de cancelación o mejorar el sistema de estrellas. El modelo Ágil permite realizar estos cambios durante el proyecto.

Además, este modelo se adapta a un proyecto que busca crear un producto que pueda evolucionar según la reacción y las necesidades de sus usuarios.

### Alternativas descartadas

**Alternativa 1: Cascada**

*Por qué la descarté:*

Se descartó porque requiere definir gran parte de los requisitos desde el inicio y desarrollar el proyecto de manera secuencial. En VYTTA pueden surgir cambios en las necesidades de los usuarios, en las reglas de cancelación o en el sistema de estrellas, por lo que un modelo más rígido podría dificultar estos cambios.

**Alternativa 2: Modelo en V**

*Por qué la descarté:*

Se descartó porque tiene un proceso más estructurado y requiere que los requisitos estén definidos de una manera más estable desde el inicio. Para VYTTA es más conveniente recibir retroalimentación durante el desarrollo y realizar mejoras conforme se prueban las diferentes funcionalidades.

---
