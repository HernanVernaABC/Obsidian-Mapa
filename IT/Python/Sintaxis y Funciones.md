### Sintaxis de Python y que función cumplen 
Tenemos la función mas básicas de todas que será _print_. 
````
print(variable)
`````

para escribir un string utilizamos una variable = "algo" (Siempre deben ir en comillas dobles)
x = "Algo"
Si realizamos """ """ Podemos poner un texto dentro.
y = """ Algo mucho mas largo"""
print(y)
Nos mostrara por pantalla que es lo que contiene la variable Y

Si nosotros queremos hallar la cantidad de caracters que tiene Y debemos usar el comando _len_, devolviendo la cantidad. 

_len_(variable string)

en las variables string tenemos formas de convertirlas 
variable = "Gato"
variable.upper() ---> Las transforma en mayuscula 
variable.lower() ---> Las tranforma en nimusculas
variable.capitalize() ---> Tranforma solo la primer letra en Mayuscula
variable.title() ---> Tranforma todas las primeras letras de una oracion en mayuscula 
variable.strip() ---> Modifica el string para que no haya espacios vacios en el comienzo como en el final
variable.lstrip() ---> Saca los espacios en blanco de la izquierda
variable.rstrip() ---> Saca los espacios en blanco de la derecha 
variable.find() ---> Busca si encuentra un caracter determinado 
	- variable.find(ato) ---> Si la encuentra devuelve el primer lugar del caracter donde lo encontro. En este caso devolvera 1
	- Si no la encuentra devuelve -1
variable.replace("G","P") ---> En este caso encuentra el caracter buscado y lo reemplaza por el caracter/s asignado. 
print("Gat" in variable) ---> En este caso _in_ busca en la variable si se encuentra ese caracter y devuelve un True o False. El print esta para visualizar, puede usarse en un if por ejemplo. 

Varias de estas se pueden utilizar a la misma vez
variable = "Gato"
variable = variable.strip().capitalize()
Estos valores deben guardarse. Solo funcionan en el momento al menos que no sean guardados 

----
Tenemos para los numeros la palabra reservada _round_ 
_round_ nos da un valor numero mas cercano en numero entero, del valor que nosotros le damos
_round(1.3)_ ---> 1 
_round(1.8)_ ---> 2
