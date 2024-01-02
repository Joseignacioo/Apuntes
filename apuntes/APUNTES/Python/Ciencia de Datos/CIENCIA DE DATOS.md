pd.set_option('display.max_rows', 1000)

IMPORTACIONES

	import pandas as pd
	import numpy as np
CREAR DF

	data = [[1,2], [2,3],[4,3]]
	df= pd.DataFrame(data, index= ['fila 1', 'fila 2', 'fila 3'],
                 columns=["columna 1", "columna 2"])
	df
	
	![[Pasted image 20231013215242.png]]
CREAR DF CON DICCIONARIO
	
	paises = ['chile','argentina','brazil']
	personas = [999999,44444,55555555]
	dict_data = {'Paises':paises,'Personas':personas}
	df1 = pd.DataFrame(dict_data)
	df1
ARCHIVOS CSV

	df_exams = pd.read_csv('StudentsPerformance.csv')
HEAD

	df_exams.head()
	
	![[Pasted image 20231013223041.png]]
TAIL

	df_exams.tail()
	
	![[Pasted image 20231013223158.png]]

# ATRIBUTOS

SHAPE
	
	df_exams.shape
	
	![[Pasted image 20231013223509.png]] 
INDEX

	df_exams.index
	
	![[Pasted image 20231013223621.png]]
