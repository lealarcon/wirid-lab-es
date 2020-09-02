Inicio Rapido Laboratorio WIRID - LAB
=======================================
## https://sphinx-rtd-theme.readthedocs.io/en/stable/index.html
Introducción
------------
El wirid-lab está diseñado para controlar equipos de radio definido por software (SDR) y dispositivos IoT mediante la reserva de nodos (Experimentos) donde el usuario puede el tipo de aplicación a desplegar en cada uno de ellos.  Para brindar la mejor experiencia de usuario,  el laboratorio cuenta con dos tipos de accesos; uno de ellos mediante terminal SSH o mediante aplicativos basados en la WEB
A continuación encontrará los pasos necesarios para ingresar al laboratorio WIRID-LAB, realizar el proceso de reserva y acceder a los nodos del laboratorio. 

Acceso y Registro al Laboratorio
--------------------------------

   Para acceder al la plataforma ingrese a https://wirid-lab.umng.edu.co y realice el proceso de autenticación con una cuenta de gmail dando clic en el botón login. Si usted es estudiante, docente o personal con correo @unimilitar.edu.co puede ingresar automáticamente, el sistema se encargará de registrarlo.  Si no hace parte de la comunidad, haga click en el link Signup para llenar el formulario y esperar la aprobación por parte de los administradores.

   Si entra por primera vez, se recomienda actualizar los datos dirigiéndose al perfil que encuentra en el menú o en el link https://wirid-lab.umng.edu.co/#/home/user/my-profile  



Generar Claves de Acceso al Laboratorio
---------------------------------------

Linux / Mac / Windows 10
^^^^^^^^^^^^^^^^^^^^^^
a) Abrir  terminal / powershell
b) Ejecutar el siguiente comando:   ``ssh-keygen -C guestuser`` y en las opciones seleccionar todos los valores por defecto oprimiendo la tecla «Enter». El comando se encarga de generar automáticamente la clave pública y privada.  La ruta donde se guardan las claves por defecto son:
c) Linux:  ``/home/<USER>/.ssh/``
d) Mac:  ``/Users/<USER>/.ssh/``
e) Windows: ``C:\Users\<USER>/.ssh/``

``<USER>`` corresponde al nombre de usuario del equipo.

Windows 7/8/10
^^^^^^^^^^^^^^^^^^^^^^
Si no cuenta con una versión reciente de windows debe instalar un cliente SSH y generar las respectivas claves. Para ello realice lo siguiente:

Descargar e instalar el paquete MSI (‘Windows Installer’)  de acuerdo con la versión de su sistema operativo en el link https://www.chiark.greenend.org.uk/~sgtatham/putty/download.html
Una vez instalado, abrir PuTTYgen.exe
Hacer clic en «Generate» y mover aleatoriamente el cursor dentro del área en blanco para generar la clave.
Una vez generada la clave, oprimir el botón Save public key para guardar la clave pública; guarde esta clave con el nombre id_rsa.pub. Luego guarde la clave privada oprimiendo el botón Save private key  con el nombre id_rsa.ppk.  El programa generó un texto que corresponde a la clave pública, guarde esta información en un documento de texto para utilizarla en el paso 4.
Cargar Claves de Acceso a la Plataforma
Sí generó las claves por medio  del terminal o powershell, ejecute el comando cat ~/.ssh/id_rsa.pub y copie el texto generado.
Si utilizó PuTTYgen copie el  texto generado de la casilla key, si quiere conocer la clave pública a partir de una clave privada ya almacenada seleccione Load Private Key y cargue la clave privada, automáticamente el programa le mostrará la clave pública correspondiente.
En el menú seleccione SSH Keys o ingrese al link https://wirid-lab.umng.edu.co/#/home/user/my-keys, haga clic en el botón New SSH Public Key, pegue la cadena de texto y haga clic en crear.
Usted puede agregar tantas claves públicas como quiera, recuerde que al menos debe contar con una para ingresar a los nodos mediante SSH

Crear Experimento
-----------------
Ingrese en el menú a Experiments -> Create
Indique la fecha y hora de reserva
Seleccione el tiempo de la reserva en minutos o en horas.
Seleccione los nodos a reservar.
A medida que reserva los nodo puede seleccionar la aplicación a instalar.
Una vez configurada la reserva haga click en Create Experiment.


Si existen otras reservas en el tiempo seleccionado se mostrarán en la tabla inferior la cantidad y nodos reservados.

Acceso al Laboratorio
^^^^^^^^^^^^^^^^^^^^^^
Al ingresar en el menú  Experiments -> My Experiments  encontrará una lista de experimentos, cuando el experimento se está ejecutando en el tiempo de la reserva verá una dirección IP asignada a cada nodo.  Dependiendo de la aplicación puede necesitar un token de acceso, para conocerlo haga clic en el icono de la llave. Si desea detener la reserva haga clic en el icono rojo.



Dependiendo de la aplicación a cargar en los nodos, el usuario tiene las siguientes opciones de conexión:

Una interfaz web jupyter para trabajar con archivos python.
Una interfaz web SSH para acceder al nodo y ejecutar comandos específicos. Si realizó la instalación de algún paquete, toda la información se perderá dado a que el laboratorio se basa en contenedores Docker.
Una interfaz web VNC* , esta opción está disponible únicamente para los equipos que ejecutan la aplicación GNU Radio.
Igualmente, durante el desarrollo del experimento tiene la posibilidad apagar o encender el nodo, tenga en cuenta que al apagar el nodo, está apagando el computador embebido y el dispositivo SDR o IOT.  Si enciende el nodo deberá esperar un tiempo aproximado de 1 minuto mientras se despliega nuevamente la aplicación seleccionada para tener acceso mediante SSH o WEB.

Si desea acceder a estas aplicaciones mediante un terminal SSH desde su computador revise el tutorial avanzado.

Para conocer más acerca de cómo usar  aplicaciones que dispone el laboratorio puede ir a Tutoriales.

 
.. Attention::
   Una vez finalizado el tiempo de su experimento, el sistema cerrará automáticamente cualquier conexión que tenga hacia el nodo.  No se preocupe si dejó abierta alguna sesión en el navegador, toda información generada durante la reserva será eliminada de forma permanente.


.. toctree::
   :maxdepth: 3
   :caption: Radio Platform

   pages/radio-platform/intro-radio

.. toctree::
   :maxdepth: 2
   :caption: IoT Platform
   
   pages/iot/intro




