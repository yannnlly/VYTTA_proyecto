# Guion de entrevista · VYTTA

**Sistema:** VYTTA — Sistema web de reservación y gestión de clases  
**Autor:** Luz Yanelly Garduño Paniagua  
**Técnica:** Entrevista

---

## Objetivo de la entrevista

El objetivo de esta entrevista es conocer cómo se realiza actualmente el proceso de reservación de clases en el estudio y cómo llevan el registro de las personas que reservan.

También se busca conocer qué problemas se presentan, qué reglas sigue actualmente el estudio y qué cosas les gustaría mejorar o implementar.

Por otra parte, se quiere conocer cómo les gustaría llevar la gestión de clases y reservaciones, qué información les gustaría mostrarles a sus clientes al momento de reservar y qué necesitarían visualizar los administradores y las maestras para poder llevar un mejor control del estudio.

---

# 1. CONTEXTO

1. Cuéntame, ¿cómo se organizan actualmente las clases?
2. ¿Qué personas participan en la organización de las clases y qué hace cada una?
3. ¿Cómo se comunican actualmente con las personas interesadas en tomar una clase?
4. ¿Qué información necesitan tener disponible para poder organizar las clases durante el día?
5. ¿Qué tipos de clases ofrecen actualmente? ¿Siempre manejan las mismas o existen diferentes tipos?
6. ¿Cómo manejan los precios de las clases? ¿Cuentan con clases individuales, paquetes u otras opciones?
7. ¿Qué reglas tiene actualmente el estudio para reservar y asistir a una clase?
8. ¿Manejan actualmente promociones o algún tipo de beneficio para sus clientes? ¿Cómo funcionan?
9. Cuando llega un cliente nuevo, ¿cómo le explican en qué consisten las clases y cómo funciona el estudio?

---

# 2. PROCESO ACTUAL

1. Cuéntame paso a paso qué sucede desde que una persona pregunta por una clase hasta que queda registrada su reservación.
2. ¿Cómo llevan actualmente el control de las personas que tienen una reservación?
3. ¿Cómo saben cuántos lugares quedan disponibles en cada clase?
4. ¿Cuántos lugares tiene disponible el estudio para cada clase? ¿La cantidad siempre es la misma o puede cambiar?
5. ¿Cómo realizan actualmente los clientes el pago de sus clases?
6. Después de recibir un pago, ¿cómo registran o comprueban que corresponde a la persona que realizó la reservación?
7. ¿En qué momento consideran que una reservación ya está confirmada?
8. ¿Cómo se comparte con las maestras la información de las personas que van a asistir a sus clases?
9. ¿Cómo llevan el control de las personas que realmente asistieron a una clase?

---

# 3. DOLORES

1. ¿Qué parte del proceso actual de reservaciones te genera más trabajo o te resulta más complicada?
2. Cuéntame sobre algún problema que haya ocurrido al organizar una reservación.
3. ¿Qué tipo de errores o confusiones ocurren con mayor frecuencia?
4. ¿Qué información es la más difícil de mantener actualizada?
5. Cuando varias personas quieren reservar al mismo tiempo, ¿cómo manejan la situación?
6. ¿Qué problemas llegan a tener con los pagos, cancelaciones o asistencias?
7. ¿Qué dificultades tienen al explicarle a un cliente nuevo cómo funcionan las clases, los precios o las reservaciones?
8. Si pudieras mejorar algo de la forma en la que trabajan actualmente, ¿qué sería y por qué?

---

# 4. EXCEPCIONES

1. ¿Qué hacen cuando una persona quiere reservar una clase que ya no tiene lugares disponibles?
2. ¿Qué sucede cuando una persona que ya tenía una reservación decide cancelar?
3. ¿Qué hacen cuando una persona reserva una clase pero no se presenta?
4. ¿Qué sucede si existe algún problema con el pago de una clase?
5. ¿Qué hacen cuando una clase cambia de horario o tiene que cancelarse?
6. ¿Qué sucede si una maestra no puede impartir una clase que ya tenía personas registradas?
7. Si una persona cancela y vuelve a quedar un lugar disponible, ¿qué hacen con ese espacio?
8. ¿Hay alguna otra situación poco común que cambie la forma normal en la que manejan una reservación?

---

# 5. VERIFICACIÓN DE SUPUESTOS

En la primera versión de VYTTA se plantearon algunas ideas sobre cómo podría funcionar el sistema. Con estas preguntas se busca saber cuáles realmente serían útiles para el estudio y cuáles tendrían que modificarse.

## Supuesto 1 · Capacidad de las clases

Pensando en un sistema de reservación de clases, ¿cómo les gustaría que se manejara una clase cuando ya alcanzó su número máximo de personas?

## Supuesto 2 · Información necesaria para reservar

¿Qué datos consideran necesarios para que una persona pueda realizar correctamente una reservación?

## Supuesto 3 · Cancelaciones

¿Qué reglas les gustaría establecer para las cancelaciones y qué debería pasar cuando una persona cancela con muy poco tiempo de anticipación?

## Supuesto 4 · Inasistencias

¿Qué consideran que debería pasar cuando una persona reserva un lugar y no se presenta a la clase?

## Supuesto 5 · Programa de fidelidad

Durante el desarrollo de VYTTA se propuso implementar un **programa de fidelidad** basado en un conteo de estrellas, donde los clientes puedan obtener estrellas dependiendo de su constancia y fidelidad con el estudio.

¿Qué comportamientos consideran importantes para identificar a un cliente que es constante y fiel con el estudio?

¿Qué les parecería implementar un programa de fidelidad donde los clientes puedan ganar estrellas por su constancia y por respetar sus reservaciones?

¿Consideran adecuado que algunas acciones, como faltar sin cancelar o cancelar fuera del tiempo permitido, puedan ocasionar la pérdida de estrellas?

¿Les gustaría que las estrellas acumuladas dentro del programa de fidelidad pudieran dar acceso a algún beneficio, promoción o descuento?

## Supuesto 6 · Pago y confirmación

Pensando en VYTTA, ¿en qué momento les gustaría que una reservación apareciera como confirmada?

¿Cómo les gustaría que el sistema manejara una reservación que todavía tiene un pago pendiente?

## Supuesto 7 · Información para el cliente

Cuando un cliente esté buscando una clase, ¿qué información les gustaría que pudiera ver antes de reservar?

Después de realizar la reservación, ¿qué información consideran importante que pueda consultar?

¿Cómo les gustaría que el cliente pudiera revisar sus próximas clases y reservaciones?

## Supuesto 8 · Gestión de clases

¿Cómo les gustaría visualizar las clases y reservaciones desde el lado del administrador?

¿Qué información consideran importante tener disponible de cada clase?

¿Cómo les gustaría llevar el control de los lugares disponibles, pagos, reservaciones y asistencias?

## Supuesto 9 · Información para las maestras

¿Qué información necesitaría consultar una maestra para poder llevar un mejor control de sus clases?

¿Qué cosas debería poder hacer una maestra dentro del sistema y cuáles consideran que deberían quedar únicamente para el administrador?

## Supuesto 10 · Precios, paquetes y promociones

¿Cómo les gustaría manejar dentro del sistema los diferentes precios y paquetes?

¿Qué tipo de promociones o beneficios les gustaría poder ofrecer?

¿Cómo les gustaría que los clientes pudieran consultar esas promociones?

---

# 6. CIERRE

1. De todo lo que hemos hablado, ¿hay algo que consideres que entendí mal o que debería aclarar mejor?
2. ¿Existe alguna regla importante del estudio que no te haya preguntado?
3. ¿Hay alguna situación que ocurra en el estudio y que consideres importante tomar en cuenta para VYTTA?
4. ¿Hay alguna función que te gustaría encontrar en VYTTA y que no hayamos mencionado?

---

# BITÁCORA DE LA ENTREVISTA

**Fecha de aplicación:** lunes 21 de septiembre

**Persona entrevistada:** Jesus Cendejas / cliente  
**Duración:** 1 hora 20 minutos

## Supuestos confirmados

Durante la entrevista se confirmó que uno de los problemas principales es llevar las reservaciones por medio de mensajes, porque cuando varias personas quieren reservar al mismo tiempo puede haber confusión sobre quién pidió primero el lugar, quién ya pagó o cuántos espacios siguen disponibles.

También se confirmó que es importante tener actualizado el número de lugares disponibles de cada clase para evitar registrar a más personas de las que realmente pueden asistir.

Otro punto que se confirmó fue la importancia de tener registrada la información de la persona que reserva, la clase que eligió, el horario y el estado de su reservación.

Las cancelaciones y las inasistencias también son importantes, ya que una persona puede apartar un lugar y finalmente no asistir, dejando ocupado un espacio que pudo haber utilizado otro cliente.

También se confirmó que cada tipo de usuario necesita ver información diferente. El cliente necesita consultar y reservar clases, la maestra necesita saber qué clases tiene y quiénes van a asistir, mientras que el administrador necesita tener un control más completo de la gestión de clases, horarios, reservaciones, pagos y asistencias.

### Programa de fidelidad

Una de las propuestas que se realizó para VYTTA fue implementar un **programa de fidelidad** para reconocer a los clientes que son constantes y fieles con el estudio.

La propuesta consiste en manejar un **conteo de estrellas** dentro del perfil de cada cliente. Estas estrellas servirán para representar la constancia del cliente dentro del estudio y podrán aumentar dependiendo de su participación y cumplimiento con las reservaciones.

Por ejemplo, un cliente podrá ganar estrellas por asistir constantemente a sus clases y respetar las reservaciones que realiza. De esta manera, mientras mayor sea su constancia dentro del estudio, mayor podrá ser la cantidad de estrellas acumuladas dentro de su programa de fidelidad.

También se propuso que las estrellas puedan disminuir cuando un cliente realice acciones que afecten la organización de las clases. Por ejemplo, no presentarse a una clase que tenía reservada o cancelar fuera del tiempo permitido podría ocasionar la pérdida de una estrella.

Durante la entrevista esta propuesta llamó la atención porque no solamente serviría para llevar un registro de las reservaciones, sino también para reconocer a los clientes que mantienen una mayor constancia con el estudio.

El programa de fidelidad también podría ayudar a que los clientes sean más responsables con los lugares que reservan, principalmente porque las clases cuentan con lugares limitados. Cuando una persona reserva y no se presenta, ese espacio pudo haber sido utilizado por otro cliente.

Además, las estrellas acumuladas podrán relacionarse con beneficios para los clientes. Por ejemplo, se podrían ofrecer promociones, descuentos o algún reconocimiento cuando el cliente alcance determinada cantidad de estrellas.

De esta manera, el programa de fidelidad se convierte en una característica que puede diferenciar a VYTTA de un sistema que solamente permite la reservación de clases, ya que también busca reconocer y premiar la fidelidad de los clientes con el estudio.

---

## Supuestos que resultaron falsos o que necesitan modificarse

No se descartó ninguna de las ideas principales de VYTTA, pero sí hubo algunas que necesitan definirse mejor antes de implementarlas.

En el caso de las cancelaciones, se confirmó que sí existe un tiempo determinado para que una cancelación sea válida sin recibir una penalización. La reservación deberá cancelarse con un mínimo de **3 horas de anticipación** antes del inicio de la clase para respetar las políticas establecidas por el estudio.

Si el cliente realiza la cancelación con menos de 3 horas de anticipación, se considerará una cancelación fuera del tiempo permitido. En este caso, se podrá aplicar una penalización dentro del programa de fidelidad mediante la pérdida de una estrella y el crédito de la clase se considerará como utilizado.

También se tendrá que definir mejor cómo se manejarán los pagos, sobre todo si el estudio ofrece clases individuales y diferentes paquetes.

En el caso del programa de fidelidad, la propuesta fue aceptada durante la entrevista. Sin embargo, todavía será necesario establecer exactamente cuántas estrellas se podrán ganar por la constancia del cliente y qué cantidad de estrellas será necesaria para obtener cada beneficio.

En cuanto a las penalizaciones, se estableció que cancelar fuera del tiempo permitido o no presentarse a una clase podrá ocasionar la pérdida de estrellas dentro del programa de fidelidad.

---

## Información inesperada

Algo que surgió durante la entrevista y que no se había considerado con tanto detalle fue la experiencia de los clientes nuevos.

Cuando una persona nunca ha asistido al estudio, puede necesitar más información antes de reservar, por ejemplo, saber en qué consiste la clase, quién la imparte, cuánto dura, cuánto cuesta, el horario y cuántos lugares quedan disponibles.

También surgió la importancia de mostrar claramente los diferentes tipos de clases, paquetes, precios y promociones para que el cliente pueda conocer sus opciones antes de reservar.

Otro punto que se tomó en cuenta fue que no todos los usuarios deberían ver lo mismo dentro del sistema. El cliente necesita una forma sencilla de buscar y realizar la reservación de clases, la maestra necesita principalmente consultar sus clases y asistentes, y el administrador necesita tener una vista más completa para realizar la gestión de clases.

También se mencionó que las promociones y beneficios podrían relacionarse con el **programa de fidelidad**. De esta manera, los clientes que acumulen estrellas por mantener una mayor constancia con el estudio podrán recibir diferentes beneficios.

---

## Cambios que se realizarán en VYTTA

Después de la entrevista se decidió mantener la propuesta del **programa de fidelidad**. Este programa funcionará mediante un conteo de estrellas que permitirá reconocer la constancia y fidelidad de los clientes con el estudio.

Las estrellas podrán aumentar dependiendo de la constancia del cliente y del cumplimiento de sus reservaciones. También podrán disminuir cuando el cliente no se presente a una clase reservada o realice una cancelación fuera del tiempo permitido.

Las estrellas acumuladas podrán relacionarse con promociones, descuentos o beneficios para los clientes que sean más constantes. La cantidad exacta de estrellas necesaria para obtener cada beneficio se definirá posteriormente de acuerdo con las reglas del estudio.

Se agregará información más completa de las clases para que, antes de reservar, el cliente pueda consultar datos como el horario, la maestra, el precio, la duración y los lugares disponibles.

También se tomará en cuenta que puedan existir diferentes tipos de clases, paquetes, precios y promociones.

Para el administrador se buscará tener una vista general que le permita realizar la **gestión de clases** y consultar horarios, reservaciones, lugares disponibles, pagos, cancelaciones y asistencias.

En el caso de las maestras, se deberá permitir que consulten sus clases y las personas registradas, además de poder llevar el control de asistencia.

También se establecerá dentro de VYTTA que las cancelaciones deberán realizarse con un mínimo de **3 horas de anticipación** para no recibir una penalización, de acuerdo con las políticas establecidas por el estudio.

---

## Conclusión de la entrevista

La entrevista ayudó a entender mejor cómo se realizan actualmente las reservaciones y qué problemas se pueden presentar en la **gestión de clases**.

También ayudó a confirmar varias de las ideas que ya se habían pensado para VYTTA y a encontrar otras cosas que no se habían considerado tanto, como la información que necesita un cliente nuevo, los paquetes, las promociones y la forma en la que cada tipo de usuario debería visualizar el sistema.

Una de las propuestas que se decidió mantener fue el **programa de fidelidad**, el cual funcionará mediante un conteo de estrellas que los clientes podrán acumular de acuerdo con su constancia y fidelidad con el estudio.

Este programa puede ayudar a reconocer a los clientes constantes y motivarlos a respetar las reservaciones que realizan. Además, las estrellas podrán relacionarse con beneficios o promociones, haciendo que VYTTA tenga una característica diferente a un sistema que únicamente permite la **reservación de clases**.

Con la información obtenida se podrán definir de una mejor manera los requisitos de VYTTA y decidir qué funciones son realmente necesarias para el estudio.
