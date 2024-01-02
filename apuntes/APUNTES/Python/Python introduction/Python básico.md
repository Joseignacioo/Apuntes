# VARIABLES

VARIABLES

	variable_str = "Mi string Variable"
	variable_int = 898
	variable_boolean = False
	VARIABLE_CONSTANTE = 'VARIABLE UNICA'
VARIABLES EN UNA LINEA + CONCATENACIÓN

	name,  surname, alias, age = "Jose", "Romero", "Joseignacioo", 20
	print(f"mi nombre es {name} {surname}, tengo {age} y mi alias es {alias}" ) 

# OPERADORES

OPERADORES

	print(15+2) # SUMA
	print(15-2) # RESTA
	print(15*2) # MULTIPLICACION
	print(15/2) # DIVISION (SI TIENE // LO TRANSFORMA  A NUMERO ENTERO)
	print(15%2) # RESTO
	print(15//2) # DIVISION APROXIMADA A NUMERO ENTERO	
	print(15**2) # EXPONENTE
	
	![[Pasted image 20231018135431.png]]

	print("Hola " + "Python") # CONCATENACION CON (+)
	print("Hola " + str(5))  # TRANSFORMAR UN (INT) EN (STRING) CON STR()	
	print("Hola " * 5) # MULTIPLICAR LA PALABRA 5 VECES
	print("Hola " * (2**3)) #MULTIPLICA LA PALABRA 2**3 = 8 VECES	
	variable_float = 2.5 * 2
	print("Hola " * int(variable_float)) # TRANSFORMAR UN (FLOAT) EN (ENTERO) CON INT()
	
	![[Pasted image 20231018135619.png]]
OPERADORES COMPARATIVOS O RELACIONALES
	
	print(3 > 4) # MAYOR A
	print(3 < 4) # MENOR A
	print(3 >= 4) # MAYOR IGUAL A
	print(3 <= 4) # MENOR IGUAL A
	print(3 == 4) # IGUALDAD A
	print(3 != 4) # DISTINTO A

	print("Hola " > "Python")
	print("Hola " < "Python")
	print("Hola " >= "Python")
	print("Hola " <= "Python")
	print("Hola " == "Python")
	print("Hola " != "Python")
OPERADORES LOGICOS 

	print(3 > 4 and "Hola " > "Python") # FALSE and FALSE = FALSE	
	print(3 > 4 or "Hola " > "Python") # FALSE or FALSE = FALSE
	print(3 < 4 and "Hola " > "Python") # TRUE and TRUE = FALSE
	print(3 < 4 or "Hola " > "Python") # TRUE or FALSE = TRUE
	print(not(3 > 4)) # NOT = NEGAR LA CONDICION

# STRINGS

STRINGS

	a = "Mi String"
	b = "Mi segundo String"
	print(len(a))
	print(len(b))
	print(a + " " + b)

	![[Pasted image 20231018140349.png]]

	c = "Este es un String\ncon salto de linea"
	print(c)

	d = "\tEste es un String con tabulacion"
	print(d)

	e = "\\tEste es un String \\n escapado"
	print(e)

	print(a,b,sep=' ') # SEPARA EL  CONTENIDO CON LO ASIGNADO EN EL SEP

  ![[Pasted image 20231018140537.png]]
FORMATEO

	name, surname, age = "Jose", "Romero", 20
	print("Mi nombre es {} {} y mi edad es {}".format(name, surname, age))
	print(f"Mi nombre es {name} {surname} y mi edad es {age}")

	# $s = STRING, %d = ENTERO. [ES MAS SEGURO]	
	print("Mi nombre es %s %s y mi edad es %d" %(name, surname, age)) 

	![[Pasted image 20231018140954.png]]
DESEMPAQUEADO DE CARACTERES

	lenguaje = "python"	
	a, b, c, d, e, f = lenguaje
	print(a) # p
	print(e) # o

  ![[Pasted image 20231018141133.png]]
DIVISION

	lenguaje_slice = lenguaje[1:3] # EL RANGO DEL 2 HASTA EL 3
	print(lenguaje_slice)
	lenguaje_slice = lenguaje[1:] #TODD MENOS EL PRIMERO
	print(lenguaje_slice)
	lenguaje_slice = lenguaje[-3] # DE DERECHA A IZQUIERDA
	print(lenguaje_slice)
	lenguaje_slice = lenguaje[1:2:4] #CARACTERES QUE NO SE VAN A MOSTRAR
	print(lenguaje_slice)
	
	![[Pasted image 20231018141341.png]]
REVERSA

	lenguaje_reversa = lenguaje[::-1] # SE INVIERTE EL STRING
	print(lenguaje_reversa)
	
	![[Pasted image 20231018141417.png]]
FUNCIONES 

	print(lenguaje.count("t")) # CONTAR
	print(lenguaje.capitalize()) # LA PRIMERA ENMAYUSCULA
	print(lenguaje.upper()) # TODD EN MAYUSCULA
	print(lenguaje.lower()) # TODD MINUSCULAS
	print(lenguaje.upper().isupper()) # TODD EN MAYUSCULAS, ¿ESTAN EN MAYUSCULAS?
	print(lenguaje.isnumeric()) # ¿ES UN NUMERO?
	print("1".isnumeric()) # ¿ES UN NUMERO?
	
	![[Pasted image 20231018141700.png]]

	lenguaje = 'Python//SQL//Java'
	print(lenguaje.split('//')) # ESPACIO

	lenguaje = ['Python', 'SQL', 'Java']
	string_lenguaje = '-'.join(lenguaje) # SE VAN UNIR MEDIANTE UN -	
	print(string_lenguaje)

	![[Pasted image 20231018141726.png]]
JUSTIFICAR O ALINEAR

	mensaje = 'HOLA MUNDO'
	print(mensaje.ljust(20)) # JUSTIFICAR A  LA IZQUIERDA con 20 espacios
	print(mensaje.rjust(20)) # JUSTIFICAR A  LA IDERECHA con 20 espacios
	print(mensaje.center(20)) # CENTRAR con 20 espacios a la izquierda y derecha

	![[Pasted image 20231018143320.png]]
# LISTAS

LISTAS

	tipo_lista = list([15, 23, "Juan", 2.0])
	lista = [20, 1.67,"Jose", "Romero"] 
	print(lista)
	
	![[Pasted image 20231018144000.png]]

	print(len(lista)) # CONTAR LARGO DE LA LISTA
	print(type(lista)) # TIPO DE DATO
	
	![[Pasted image 20231018144043.png]]

	print(lista[0]) # BUSCAR LA POSICION 0	
	print(lista[1]) # BUSCAR LA POSICION 1
	print(lista[-1]) # BUSCAR LA POSICION -1
	
	![[Pasted image 20231018144138.png]]
	  
	print(lista.count(20)) # CONTAR CUANTOS 20 HAY
	age, height, name, surname = lista #VARIABLES CON ORDEN DE LISTA
	print(name)
	
	![[Pasted image 20231018144316.png]]

	tipo_lista.extend(lista) # UNIR LISTAS
	print(tipo_lista)
	print(lista + tipo_lista) # UNIR LISTAS
	
	![[Pasted image 20231018144459.png]]
	  
	
	lista.append("Quezada") # AGREGAR A LA LISTA
	print(lista)
	
	![[Pasted image 20231018144604.png]]

	lista.insert(1, "Verde") # INSERTAR EN LA POSICION o  INDICE
	print(lista)
	
	![[Pasted image 20231018144644.png]]
	
	lista[1] = "Rojo" # REMPLAZA EL VALOR DE LA POSICION o  INDICE
	print(lista)
	
	![[Pasted image 20231018144725.png]]
	
	lista.remove("Rojo") # ELIMINAR EL VALOR INDICADO
	print(lista)
	
	![[Pasted image 20231018144740.png]]

	print(lista.pop()) # ME RETORNA EL VALOR ELIMINADO
	
	![[Pasted image 20231018144847.png]]	
	
	print(lista.pop(2)) # ELIMINAR EN LA POSICION o  INDICE
	
	![[Pasted image 20231018144908.png]]
	
	print(lista)
	
	![[Pasted image 20231018145042.png]]
	  
	del lista[2] # ELIMINAR EN LA POSICION o  INDICE
	print(lista)
	
	![[Pasted image 20231018145302.png]]
	
	nueva_lista = lista.copy() # COPIAR LISTA
	lista.clear() # BORRAR LA LISTA
	print(lista)
	print(nueva_lista) # NO SE BORRA ESTA LISTA
	
	![[Pasted image 20231018145401.png]]
	  
	nueva_lista.reverse() # ORDENA LOS VALORES ALREVES
	print(nueva_lista)
	nueva_lista.sort() # ORDEN ALFABETICO O DE MENOR A MAYOR
	print(nueva_lista)
	print(nueva_lista[1:2]) # SUBLISTAS
	
	![[Pasted image 20231018145629.png]]
	
	print(min(nueva_lista)) # RETORNA EL VALOR MINIMO
	print(max(nueva_lista)) #RETORNA EL VALOR  MAXIMO
	
	![[Pasted image 20231018145652.png]]
	  
	print(20 in nueva_lista) # EXISTE EN LA  LISTA
	print(20 not in nueva_lista) # NO EXISTE EN LA LISTA
	
	![[Pasted image 20231018145727.png]]
	
	print(nueva_lista.index(20)) # RETORNA EL INDICE
	
	![[Pasted image 20231018145753.png]]
MATRIZ

	columna_a = [10, 20]
	columna_b = [30, 40]
	
	matriz = [columna_a, columna_b] # 2 x 2
	print(matriz[0][1])
	
	![[Pasted image 20231018145846.png]]

	a = [1, 2, 3, 4, 5]
	print(a[-3:])
	
	![[Pasted image 20231018145857.png]]

# TUPLAS

TUPLAS

	tipo_tupla = tuple([15, 23, "Juan", 2.0])
	tupla = (20, 1.67,"Jose", "Romero")
	
	print(tupla)
	print(len(tupla))
	print(type(tupla))
	
	![[Pasted image 20231018153849.png]]
	
	print(tupla[0]) # BUSCAR LA POSICION 0
	print(tupla[1]) # BUSCAR LA POSICION 1
	print(tupla[-1]) # BUSCAR LA POSICION -1
	
	![[Pasted image 20231018153931.png]]

	print(tupla.count(20))  # CONTAR CUANTOS 20 HAY
	print(tupla.index("Jose")) # NOS MUESTRA LA  POSICION o INDICE DEL ELEMENTO
	
	![[Pasted image 20231018154038.png]]
	
	print(tupla[2:6]) #subtupla
	print(tipo_tupla + tupla) # UNIR TUPLAS
	
	![[Pasted image 20231018154315.png]]
	
	tupla = list(tupla) # TRANSFORMAR LA  TUPLA  EN LISTA
	print(type(tupla))
	
	![[Pasted image 20231018154343.png]]
ZIP

	lista = [1,2,3,4,5]
	nueva_tupla = (10.20,30,40,50)
	lista_2 = [100,200,300,400,500]
	
	resultado = zip(lista,nueva_tupla,lista_2) #ZIP
	resultado = tuple(resultado)
	
	print(resultado)
	
	![[Pasted image 20231018154800.png]]

	del tupla # ELIMINA TODA LA TUPLA

# SETS

SETS 

	tipo_set = set()	
	sets = {}
	
	print(type(tipo_set))
	print(type(sets)) # INICIALMENTE ES UN DICCIONARIO
	
	![[Pasted image 20231018155237.png]]
	
	sets = {"Jose", "Romero", 20}
	print(type(sets)) # AHORA LO TRANSFORMA EN SET
	print(len(sets))
	
	![[Pasted image 20231018155252.png]]
	
	sets.add(1.68) #AGREGA PERO UN SET NO  ES UNA ESTRUCTURA ORDENADA
	print(sets)
	sets.add(1.68) # UN SET NO AGREGA REPETIDOS
	print(sets)
	
	![[Pasted image 20231018155346.png]]
	
	print("Jose" in sets) #EXISTE EN EL SET ?
	print("Quezada" in sets) #EXISTE EN EL SET ?
	
	![[Pasted image 20231018155409.png]]
	
	sets.remove(1.68) #ELIMINAR EL VALOR INDICADO
	print(sets)
	sets.clear() # BORRA TODOS LOS ELEMENTOS DEL SET
	print(len(sets))
	
	![[Pasted image 20231018155504.png]]
  
	sets = {"Jose", "Romero", 20}
	otro_sets = {"python", "javascript", "java"} # UNIR SETS
	new_set = sets.union(otro_sets)
	print(new_set)
	
	![[Pasted image 20231018155527.png]]
	
	del sets # ELIMINA INCLUYENDO EL SET
	print(sets)
	
	![[Pasted image 20231018155544.png]]


# DICCIONARIOS

DICCIONARIO

	diccionario = {
	    "Nombre":"jose",
	    "Apellido":"Romero",
	    "edad":20,
	    "lenguajes":{"python", "javascript"}
	    }
	
	print(diccionario)
	print(len(diccionario)) # SON KEY Y CONTENIDO
	
	![[Pasted image 20231018160025.png]]
	
	print(diccionario["Nombre"]) # RETORNAR EL VALOR INDICADO
	diccionario["Nombre"] = "José" # REMPLAZAR DATOS
	print(diccionario["Nombre"])
	
	diccionario["Educacion"] = "Duoc UC" # AGREGAR DATOS
	del diccionario["Educacion"] # ELIMINAR EN LA POSICION o  INDICE
	print(diccionario)
	
	![[Pasted image 20231018160133.png]]
	
	print("José" in diccionario) # EXISTE EN EL DICCIONARIO ? BUSCA POR KEYS
	print("Apellido" in diccionario) #EXISTE EN EL DICCIONARIO ?
	
	![[Pasted image 20231018160357.png]]
	
	print(diccionario.items()) # RETORNA EL DICCIONARIO DE ITEM UN LISTADO
	print(diccionario.keys())  # SOLO RETORNA LAS KEYS
	print(diccionario.values()) # SOLO RETORNA LOS VALORES
	
	![[Pasted image 20231018160420.png]]
	  
	
	new_diccionario = dict.fromkeys(("Nombre", 1)) # PARA CREAR UN DICCIONARIO
	print(new_diccionario)
	
	![[Pasted image 20231018160504.png]]


# CONDICIONALES

CONDICIONALES

	condicional = True
	if condicional:
	    print("Se ejecuta correctamente")
	if condicional == True:
	    print("Se ejecuta correctamente") # ES LO MISMO QUE LA ANTERIOR
	    
	    ![[Pasted image 20231019154000.png]]

ELSE

	condicional = 5 * 2
	if condicional == 10: # SI LA CONDICION CUMPLE  
	    print("Se ejecuta la condicion 1")
	if condicional > 10 and condicional < 20:
	    print("Se ejecuta la condicion 2")
	else:  # SI LA  CONDICION NO CUMPLE
	    print("Es menor oo igual que 10 o mayor o igual que 20")
	    
	   ![[Pasted image 20231019154055.png]]

ELIF 

	condicional = 7
	if condicional == 10: # SI LA CONDICION CUMPLE  
	    print("FELICIDADES APROVASTE TIENES UN 10")
	elif condicional == 9 or condicional == 8:
	    print("FELICIDADES APROVASTE")
	elif condicional == 7 or condicional == 6:
	    print("APROVASTE")
	else:  # SI LA  CONDICION NO CUMPLE
	    print("REPROVASTE")

	![[Pasted image 20231019154221.png]]

NOT 

	string = ""	
	if not string:
	    print("Mi cadena de texto esta vacia")
	if string == "Python":
	    print("Coincide")
	
	![[Pasted image 20231019154238.png]]

TERNAEARIO 

	calificacion = 10
	color = 'verde' if calificacion >= 7 else 'rojo'	
	print(calificacion, color)

	![[Pasted image 20231019154300.png]]




# LOOPS

WHILE
	
	condicion = 0
	while condicion < 10: # REPITE  INFINITAS  VECES LA CONDICION HASTA QUE SEA FALSE
	    print(condicion)
	    condicion += 1 # TERMINA LA EJECUCION CUANDO LLEGUE A 10
	else: # EJECUTA JUSTO CUANDO SE  CUMPLE EL WHILE
	    print("Mi condicion es mayor o igual que 10")

	while condicion < 20:
	    condicion += 1
	    if condicion == 15:
	        print("Se detiene la ejecucion")
	        break # TERMINAR EL PROCESO
	    print("Mi condicion es  menor a 20")

FOR

	lista = [35, 24, 62, 52, 30, 30, 17]
	for elemento in lista:
	    print(elemento)

	tupla = (20, 1.67,"Jose", "Romero")
	for elemento in tupla:
	    print(elemento)

	sets = {"Jose", "Romero", 20}
	for elemento in sets:
	    print(elemento)
	
	  
	
	diccionario = {"Nombre":"jose", "Apellido":"Romero", "edad":20,"lenguajes":{"python", "javascript"}}
	for elemento in diccionario:
	    print(elemento)
	    if elemento == "edad":
	        # break
	        continue # SE SALTA LA  EJECUCION Y PASA A LA SIGUIENTE
	    print("Se ejecuta")
	else:
	    print("El  bucle for para diccionario termino")

  
  

#====== FOR IN RANGE======#

for i in range(10):

    print(i)

  

for i in range(15,20):

    print(i)

  

for i in range(1,10,2):

    print(i)

  

#====== FOR IN ENUMERATE======#

numeros = [10, 20, 30, 40, 50]

for i, numero in enumerate(numeros):

    i += 1

    print(f'{i}) {numero}')