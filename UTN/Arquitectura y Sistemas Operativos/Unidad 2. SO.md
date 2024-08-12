# Sistemas Operativos 
### Sistemas Informáticos 
Los Sistemas Informáticos están compuestos por 3 partes:
	- Usuarios 
	- Software
	- Hardware 
Los tres están administrados por un Sistema Operativo. Este realiza una interacción en común entre los elementos  
##### Sistema Operativo
Provee un entorno en el cual otros programas pueden hacer trabajo útil. Podemos ver al SO como un asignador de recursos.
Su fuente principal de trabajo es un conjunto de tablas en las cuales se describen los recursos y a qué procesos están asignados los mismos
		_Administra recursos_
			Físicos (Memoria, procesador, almacenamientos, dispositivos)
			Lógicos (archivos y procesos)

____
###### SO son residentes 
- Esto quiere decir que se inicia en memoria ram y se mantiene en memoria ram hasta que se apague o se reinicie por algún motivo.
###### Utilitarios no residentes
- Esto quiere decir que se cargan en memoria ram solo cuando son utilizados (llamados), mientras tanto se mantienen almacenados en una memoria auxiliar (En el disco, son programas.) Son programas que le dan soporte al SO (Desfragmentador de disco, de memoria, etc)
[[Unidad 1. Software]]
---
### Conjunto de Rutinas SO 
El SO es un conjunto de programas y rutinas. 
	_Controla Operaciones_ (Operaciones de la computadora con minima intervención humana) y _Recursos_ (Lógicos y Físicos) 
	Incluye _Shell_
		La _Shell_ permite la interacción de la computadora con el usuario. Existen dos tipos: 
			- _CLI_ (Command Line Interface): Seria el equivalente a la consola. Donde nosotros podemos controlar la computadora desde esa interfaz 
			- _GUI_ (Graphical User Interface): Seria la interfaz Grafica. O motor grafico. 
	Incluye _Kernel_
		El _Kernel_ tiene la función de interactuar el Software con el Hardware. También conocido como Núcleo. 
			- La interacción es realizada a través de _drivers o controladores_
				Estos Programas o software son los que se encargar de que ambos _hablen el mismo idioma_.
				Núcleo del sistema operativo > Tareas:  
					- Secuenciar los procesos  
					- Reservar espacio de memoria y de disco  
					- Supervisar la transmisión de datos entre memoria principal y periféricos 
					- Satisfacer las peticiones de servicios de los procesos existentes
___
#### Funciones del Sistema Operativo 
Tiene tres funciones 
	- Inicialización 
	- Maquina Extendida
	- Administrador de Recursos 
###### Inicialización  
Inicializar la máquina
	Esta tarea es llevada a cabo por el Kernel, con rutinas residentes en memoria ROM o RAM de la máquina más otras residentes en el disco del sistema. La inicialización tiene por objetivo preparar la máquina real y llevarla a un estado tal que pueda ejecutar el primer trabajo.
	ROM es la abreviatura de "Read-Only Memory" (Memoria de Solo Lectura). Se refiere a un tipo de memoria de computadora no volátil que se utiliza para almacenar instrucciones y datos permanentes que son leídos por la máquina. 
En otras palabras la inicialización se encarga de buscar el SO e introducirlo en la memoria RAM
	Todos estos comandos o procesos se encuentran en la Bios (ROM). _Post_, _IPL_ _SETUP_ 
			Unidad de Control
				- Se Ejecuta el _Post_ Se encarga de revisar que el hardware este en las condiciones mínimas e indispensables para inicializar la maquina)
					- Si por algún motivo el _Post_ _no da la señal positiva_. Se ejecuta el _SETUP_. En la BIOS, _setup_ es un software o menú de configuración integrado en la BIOS misma. Permite al usuario acceder y modificar diversos ajustes y parámetros relacionados con el hardware y el funcionamiento del sistema. (Este elemento necesita de una pila)
						- Solucionar problemas de arranque para cambiar el orden de arranque de los dispositivos o habilitar/deshabilitar componentes que podrían estar causando el problema.
				- Cuando el _Post termina y da la Señal Positiva_. Este ejecuta la rutina _IPL_ (Cargador inicial de programa), donde busca en el _MBR_ (Tabla de particiones. Punto 0 del disco.) 
				- Una vez encontrado el SO se inicia el _Booter_. Es un software que tiene como principal función buscar en el disco el SO (el kernel y el shell) y cargarlos en memoria ram 
					 _Se inicializa el SO en memoria Ram_ 
###### Maquina Extendida
Es un modulo de SO denominado _SHELL_ o _Interprete de comandos_ 
	Este Actúa como medio de comunicación entre el usuario y el hardware.
	Facilitar la comunicación con el usuario
		Existen dos tipos: 
			- _CLI_ (Command Line Interface): Seria el equivalente a la consola. Donde nosotros podemos controlar la computadora desde esa interfaz 
			- _GUI_ (Graphical User Interface): Seria la interfaz Grafica. O motor grafico. 
###### Administración de Recursos 
Objetivos 
- Facilitar a los usuarios compartir y proteger recursos. 
- Optimizar el porcentaje de utilización de los recursos.
__El SO implementa__ 
1. Una Política dado que asigna prioridades (de uso y/o de acceso a los recursos).
2. Una Estrategia ya que ordena los accesos y los conflictos. 
3. Una Autoridad pues debe recuperar los recursos otorgados a los procesos y ordenar el uso de los mismos. 
4. Una Protección brindando seguridad a los usuarios entre sí y preservando la integridad de los recursos. 
5. Una Contabilidad para llevar el control del uso y disponibilidad de los recursos.
__Y el SO ofrece__
	a) Facilidades para crear, manipular y eliminar objetos sobre los que se quiere realizar operaciones, a través de la Gestión y Conservación de la Información sobre ellos. 
	b) Un ambiente para la ejecución de trabajos, mediante la gestión del conjunto de recursos que permiten ejecutar los mismos. 
	c) Facilidades para compartir el conjunto de recursos entre los usuarios.

---
##### Características de las Rutinas de la Bios 
- Firmware
	Todo aquello que esta escrito por hardware 
		En este caso serian las memorias ROM 
- Stand Alone 
	Es un concepto que representa que un programa o rutina pueda ser ejecutado sin que el SO. 
##### Características de Booter 
- Es un Software ya que es un programa creado por otro programa.
	Es creado por el SO.
- Stand Alone
	Ya que se ejecuta sin la necesidad de que el SO este en Memoria RAM 
----

#### Características Comunes de los SO
- Gestión de reparto de recursos:
	Tiene como objetivo _mejorar el tiempo del hardware_. optimizar los tiempos de servicios 
- Gestión de la información. Cooperación entre procesos y la protección  
	La gestión de la información en un sistema operativo permite _organizar y administrar los archivos_ y datos de manera eficiente.
		Permitir el retraso de los recursos: Capacidad de un sistema operativo para administrar y distribuir de manera eficiente los recursos de hardware disponible
- Cooperación entre recursos 
		Los procesos interactúan generando conflictos en los siguientes casos:
	\ - Compiten por el uso de los Recursos. 
	\ - Cooperan para alcanzar el objetivo de ejecutar las tareas del User.
	\ - Comparten objetos. 
	\ - Se Comunican 
	Estos problemas, generalmente, se plantean en los accesos a los recursos escasos en donde se visualizan los conflictos por lo que se solucionan a través de _herramientas de sincronización_ y de comunicaciones ofrecidos por el SO
- Protección
	Objetivos: 
		- Garantizar: Integridad de los recursos y procesos
		- Permite el cumplimiento de mecanismos:
			- Exclusión Mutua: __Impide__ el acceso Simultaneo a recursos por parte del procesador
			- Ejecución DUAL de instrucciones: Maestro-Esclavo método de seguridad en la que cada instrucción se ejecuta dos veces: una vez por el "maestro" y otra vez por el "esclavo". El esclavo verifica que la ejecución del maestro sea correcta. Si hay una _discrepancia_, se activan medidas de seguridad para prevenir posibles ataques maliciosos. 	
---
#### Capas SO 
###### Primer capa:
Primer Nivel: Administrador de pedidos (_JOB SCHEDULER_)
	Modulo de _JOB SCHEDULER_
	Este módulo, al que se lo conoce como _Job Scheduller_ o _Planificador de Trabajos_, este se encarga de:
		- Cargar programas.
		- Crear procesos.
		- Administrar y controlar los accesos de los usuarios.
		 -Establecer las protecciones.
	Se encarga de asignar un proceso. Los prepara para cederlo al SO para ser administrado. Cuando el proceso termina el que recupera todo esos recursos es el _Job Scheduller_ 
###### Segunda Capa: 
Segundo Nivel: Administrador de recursos 
	Consta de 2 módulos:
		 Administrador de procesos y procesadores (_Dispatcher_)
			Decide, una vez llegado un trabajo dividido en procesos, a qué procesador asignar el proceso que tiene que ser ejecutado y le otorga el uso del procesador
				¿Qué quiere decir?
					De la cola de procesos que tengo, el _Dispatcher_ es quien decide quien sigue.
		Controlador de trafico (_Trafic Control_)
			Este se encarga de crear, modificar y actualizar el contexto asociado a un proceso para posibilitar su pasaje entre los diferentes estados 
				Lleva el hoja de ruta de ese proceso 
				Tabla donde queda asentado su Id, recursos. 
					A crear, modificar y actualizar se de denomina _Contexto_