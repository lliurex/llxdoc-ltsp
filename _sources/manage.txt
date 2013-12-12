Gestión del aula con LliureX LTSP
=================================

A partir de LliureX Pandora 13.06, la gestión del aula se realiza con *Epoptes* (en versiones anteriores se empleaba *TCOSMonitor*). Esta aplicación permite realizar una serie acciones a uno o varios equipos cliente seleccionados, a saber:

* Compartir (mostrar) la pantalla.
* Ejecutar aplicaciones.
* Envío de mensajes.
* Bloquear y desbloquear pantallas.
* Iniciar, reiniciar o apagar.

Epoptes se accede desde el menú: Aplicaciones > Administración de Lliurex > Epoptes, control de aula. Puede seleccionar el conjunto de equipos a controlar desde la interfaz de Epoptes.

Compartir la pantalla
---------------------

Si no dispone de proyector en el aula o simplemente quiere mostrar cómo se realiza alguna tarea en varios equipos a la vez, puede emplear esta opción.

.. image:: _static/epoptes-show.png
   :align: center

Ejecutar aplicaciones
---------------------

Si necesita lanzar una aplicación en los equipos seleccionados puede hacerlo mediante la opción resaltada en la imagen.

.. image:: _static/epoptes-run.png
   :align: center

Envío de mensajes
-----------------

Igualmente, desde el mismo menú anterior o bien desde la barra de herramientas, puede enviar mensajes a los equipos seleccionados.

.. image:: _static/epoptes-msg.png
   :align: center

Bloquear y desbloquear pantallas
--------------------------------

De la misma manera puede bloquear (y desbloquear) equipos.

.. image:: _static/epoptes-block.png
   :align: center

Iniciar, reiniciar o apagar
---------------------------

Como utilidad adicional, puede iniciar (encender), reiniciar o apagar los equipos seleccionados.

.. image:: _static/epoptes-session.png
   :align: center

Es posible que lleguemos con el tiempo justo al aula, y no queramos perder el tiempo esperando que los alumnos arranquen los equipos, el Epoptes, nos va a permitir arrancar todos los equipos del aula a la vez, pero para ello nuestra aula debe cumplir unos requisitos:

* Que los equipos soporten la opción de `Wake On LAN`_ (Encendido por red)
* Que la red se encuentre correctamente cableada por medio de un *switch*
* Haber realizado el `Registro de equipos`_ del aula en un grupo de Epoptes

Una vez se cumplan estos requisitos, vamos a poder arrancar todos los equipos del aula a la vez, con lo cual no tenderemos que ir uno a uno o esperar a que los alumnos los arranquen, desde el servidor los encenderemos todos.

Tanto para evitar que se quede encendido algún equipo (una vez finalizadas las clases) como para reiniciar algún equipo concreto, podemos mirar con Epoptes los clientes que se detectan:

.. image:: _static/epoptes-detect.png
   :align: center

De esta manera podemos proceder a apagarlos o reiniciarlos mediante la correspondiente opción del menú.

Registro de equipos
-------------------

Aunque Epoptes puede realizar un registro de equipos propio, es recomendable hacerlo primero desde LliureX LTSP. De esta manera tendremos como resultado toda el aula registrada, para cualquier aplicación (no sólo Epoptes). Este proceso de registro asocia un ordenador concreto con un nombre definido por nosotros. De esta manera podemos tener identificado desde el ordenador del profesor a cualquier equipo de un alumno (por ejemplo mediante un sistema de coordenadas: *a1_34* para el aula 1, tercera fila, cuarto ordenador desde la ventana).

El proceso a seguir es el siguiente:

#. En el equipo cliente debe lanzar la aplicación *LliureX LTSP Info* y le aparecerá la siguiente ventana:

.. image:: _static/llx-ltsp-register.png
   :height: 600px
   :align: center

2. Pulsar en el botón *Enviar la MAC al servidor*. Con esta operación envía al servidor LTSP la información necesaria para poder registrar el equipo.

#. Por último, en el Gestor de LliureX LTSP, pulsamos el botón de *Cliente nuevo* e importamos la información enviada, tal y como se muestra en la imagen:

.. image:: _static/llx-ltsp-classroom-mgmt-new-client.png
   :width: 500px
   :align: center

Creación de un grupo en Epoptes
-------------------------------

Para poder realizar acciones a todo un grupo de ordenadores (como por ejemplo el apagado del aula), es necesario crear un grupo en Epoptes e incluir los equipos correspondientes. Será necesario realizar los siguientes pasos:

* Es necesario tener la **sesión iniciada** en todos los ordenadores (*no deben estar en la pantalla de login*).
* Desde la ventana de Epoptes, esperaremos a que vaya analizando la red y aparezcan todos los equipos.
* A continuación creamos un grupo nuevo (pulsando en el símbolo *+* verde en la esquina inferior izquierda).
* Ahora iremos arrastrando -uno a uno- los clientes detectados al nuevo grupo.

Cuando, por ejemplo, deseemos apagar los equipos podremos realizar esta opción desde el menú (a todo el grupo) y aparecerán con el siguiente icono:

.. image:: _static/epoptes-client-offline.png
   :align: center

Wake On LAN
-----------

El soporte de *Encendido por Red* viene implementado en el ordenador. Los equipos portátiles más modernos con *wifi* también suelen soportarlo, aunque en estos casos se llama *Wake on Wireless LAN*. El único requerimiento para que funcione es que esté activado en la configuración de la BIOS de cada ordenador del aula.

Para ver si la BIOS esta correctamente configurada, haga lo siguiente:

* Reinicie el equipo y entre a la BIOS presionando la tecla necesaria según corresponda (ESC, DEL, F2, F5, F11, F12)
* Una vez dentro de la BIOS, deberemos entrar a las opciones de alimentación (POWER) y activar la opción *Wake on LAN* o similar

.. important:: Recuerde guardar los cambios en la BIOS antes de salir.


.. figure:: _static/wakeonlan1.png
   :align: left

   Ejemplo 1


.. figure:: _static/wakeonlan2.jpg
   :align: right

   Ejemplo 2
