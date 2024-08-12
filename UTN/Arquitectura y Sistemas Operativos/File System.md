# Administración de la Información 
Todo sistema debe poseer un modulo del manejo de archivos. Este se encarga de algunos aspectos como el almacenamiento y la recuperación de datos.
#### Funciones Básicas del administrador de archivos
###### Llevar un registro o rastro de la información a través de tablas 
Las tablas contienen para cada archivo: 
- Nombre
- Ubicación
- Longitud (Cant de registros del archivo)
- Longitud de registro lógico
- Longitud de registro físico 
- Fecha de creación
- Fecha de expiración
- Derecho de Acceso 
- ETC
###### También decide la políticas de donde y como es almacenada la información. 
- Utilización efectiva del almacenamiento Secundario
- Flexibilidad a usuarios 
- Acceso Eficiente
- Proyección con los permisos de los datos 
###### Asigna Recursos de la información 
Deben encontrar información, hacer accesible información al proceso y establecer derechos de acceso.
###### desasigna Recursos de la información 
Una vez que no es necesaria la tabla puede ser eliminada

#### Modelo general de Sistema de Archivos 
##### Modulo Sistema de Archivo Simbólico (SAS) o Capa 1
El modulo SAS realiza la llamada. 
Tiene 2 tablas. Tabla Directorio de Archivo Simbólico (DAS)
- Tabla Directorio de Archivo Simbólico (DAS) 
	- Posee todos los archivos del Sistema (Disco Rígido)
- Tabla Nombre Activos (TNA) 
	- Posee únicamente los archivos activos (Memoria Ram) 
Todos los archivos correspondientes al sistema esta en la tabla DAS y cuando se quiere abrir un archivo se crea una tabla TNA y se copian solamente los archivos que estén en uso.  

El SAS realiza un llamado al modulo SAB (Sistema de Archivo Básico)
##### Módulo SAB (Sistema de Archivo Básico). Capa 2 
El SAS que posee los archivos de todo el sistema al realizar la llamada al _SAB_ este lo encuentra con un identificador (Un _ID_ único e irrepetible). El modulo _SAB_ también tiene 2 tablas:
- _DAB_ (Directorio de archivo básico): Posee todos los parámetros de un archivo referido. Todos los archivos 
- _TAA_ (Tabla de archivos activos): Posee solamente los archivos que se están utilizando. Cuando estos archivos pasan al _TAA_ estos poseen un numero de entrada. Ya no trabaja con el numero de _ID_ en disco, sino que trabaja con el numero de entrada que esta en la memoria RAM 
El modulo _SAB_ realiza una llamada _VCA_ (Verificación de Control de Acceso) quien actúa como módulo de control entre el _SAB_ y el _SAL_ 

##### Módulo VCA (Verificación de Control de Acceso). Capa 3
Es un módulo que se encarga exclusivamente de los permisos. 
Si los permisos existentes están para lo que se requiere utilizar el archivo este simplemente pasa al módulo siguiente sin modificar nada. 

##### Módulo SAL (Sistema Archivo Lógico). Capa 4
Convierte el registro lógico (Como lo conocemos nosotros) a una cadena de bytes lógicos para ser almacenado. Quiere decir, se traduce a lenguaje computacional 
Se averiguan dos parámetros:
- Longitud de secuencia de bytes lógicos (_LSB_). Dato ya almacenado.
- Dirección de Bytes Lógicos (_DBL_). El cual se compone como N° de registro lógico - 1  * la Longitud de registro Lógico. 

**El Sistema Operativo Solo trabaja hasta la Capa 4.**
##### Módulo SAF (Sistema Archivo Físico). Capa 5
El Sistema Operativo ya NO trabaja hasta el módulo _SAF_. A partir de aquí trabaja el _driver_ o _controlador_ (Un drive o controlador es un programa (software) especifico del dispositivo para que el kernel y el dispositivo hable el mismo idioma) 
_El módulo SAF es administrado por el drive o controlador, no por el sistema operativo_

El _SAF_ posee 2 módulos
Si la operación es de escritura el _SAF_ utilizara ambos módulos
- MEA (Módulo de estrategia de asignación): Busca un espacio donde poder escribir 
- MEP (Módulo de Estrategia de Periféricos): Transforma el numero de bloque físico en un formato de acorde al periférico. 

_Si SOLAMENTE NECESITO LEER. Con utilizar solo MEP alcanza_ 



#### Estructura de Control de Acceso
Se basa en los permisos que controla el módulo _VCA_ (Verificación de Control de Acceso) almacenados en el _DAB_ 
Tenemos dos Métodos 
- Lista de Control de Acceso (LCA): Por cada archivo tengo una lista de control de acceso que me dice que usuario puede trabajar y que permiso tiene. Los permisos esta especificado por cada archivo, le digo que usuario y que puede hacer 
- Lista de Control de Usuario (LCU): Por cada usuario, que archivo tiene y que permiso puede hacer en esos archivos. 


