# Procesos 
### Introducción 
Un proceso en un SO se refiere a una instancia de un programa en ejecución. Cuando se ejecuta un programa el SO crea un proceso para manejar la administración de recursos y la ejecución del programa. 
###### Un proceso es una porción de programa en ejecución más su contexto.
PROCESO = porción de programa en ejecución + PCB

Es un conjunto formado por: 
- Las Instrucciones de un programa destinadas a ser ejecutadas por el microprocesador 
- Su estado de ejecución en un momento dado, esto es, los valores de los registro CPU para dicho programa 
- Su memoria de trabajo, eso quiere decir, la memoria que ha sido reservada y su contenido 
- Otra información que permite al SO su planificación 

_¿En que difiere un programa de un proceso?_
- Para empezar un programa se mantiene en memoria secundaria (Disco Rígido), en ese momento no cumple ninguna función hasta que es llamado, cuando este se ejecuta solamente una parte y se carga en memoria ram, es ahí cuando se convierte en proceso mas su PCB (es su contexto; Archivos que puede llegar a requerir recursos de hardware, todos los recursos que vaya necesitando). Ningún programa puede estar en ejecución sin una copia de si mismo en memoria ram 	todo proceso esta identificado por un _ID_ y es único e irrepetible 

Diagrama de transición o diagramas de estados
modelo de 2 estados 
	Se utiliza para SO monotareas 
		El proceso se esta ejecutando o no ejecutando (No existen otras opciones)

Modelo 5 estados 
	Solo utiliza memoria ram 
		Estados son: Nuevos, listos, ejecutando, terminados, esperando 
			Nuevo: Se crea nuevo proceso e ingresa
			Listo: Aceptan al nuevo proceso, donde el dispacher se encarga de enviar el proceso al procesador 
			Se ejecuta el programa 
				En el caso de que ocurra un suceso que impide finalizar, pasa al estado de esperando (hasta que ocurra un suceso o hasta que se libere el recurso)
			Una vez se den todas las condiciones pasa a finalizarse 
_Job Scheduller_ trabaja con el estado nuevo y el estado terminado
	Al comienzo este le asigna el proceso estado nuevo con todos sus recursos y una vez finalizado agarra todo los recursos que se le fueron asignados y los libera 

En el caso de que en algun momento haya algun proceso con mucha mas prioridad, el proceso de menos prioridad vuelve a listo, esto se le conoce como desalojo 

Modelo de 5 estados mas Suspendido
	Trabaja en memoria ram y en disco rigido 
	Este trabaja con un sistema Swap (de intercambio con disco rigido, a memoria secundaria)
	Este agrega los 2 sistemas de listo y suspendido y bloqueado y suspendido
	Bloqueado seria el equivalente a esperando 
	La diferencia de listo y suspendido a listo es que listo y suspendido se encuentra en memoria secundaria, una vez pasa a memoria ram este pasa a listo, el dispacher no trabaja con memoria secundaria, solo en memoria ram, unicamente con listo 
	Bloqueado y suspendido es que se encuentra en memoria secundaria esperando un suceso o esperando recursos. para pasar a listo y suspendido y de ahi a listo en memoria ram 

Politicas de asignacion 
Posee pautas para mejorar el desempeño
	Maximizar los tiempos de:
		Uso del 100% del procesador 
		Cantidad de Trabajos por unidad de tiempos 
	Minimizar los tiempos de:
		Tiempos de ejecucion: Tiempo desde que ingresa hasta cuando sale un proceso 
		Tiempo de espera: tiempo en el que un proceso permanece el listo
		Tiempo de respuesta: tiempo en que tarda obtener un resultado 
Tenemos las politicas de:
	FIFO 
		Primero entrar es el primero en salir, Se respeta el orden de llegada, No hay desalojo. Un proceso para a bloqueado por desicion propia, y una vez sale de bloqueado va al final de la cola de "listos"
	Mas Cortos primero (jsf) sin desalojo
		Ordena por cantidad de tiempo que requiere el procesador
	Mas corto primero con desalojo 
		Existe la posibilidad que un proceso se este ejecutando y tenga que volver a la cola de listos
	Administadores de Prioridades
		el que tenga mayor prioridad va a estar mas adelante en la cosa de listos
	round robin 
		Este sistema de procesamiento el procesador le dedica el mismo tiempo a todos los procesos y tiempo se denomina quantum. No importa si el proceso no termino, siempre le dedica el mismo tiempo a todos los procesos. 
	Multicolas 


Hilos de ejecucion
	Tareas del proceso 
		el proceso tiene pcb, los hilos tiene pcb de los procesos que los creoo
		Un hilo es una tarea de un proceso, en cambio un proceso es una part