
> [!important]
> 	alter user hr account unlock;
> 	alter user HR identified by hr;
> 	
> 	drop user alumno cascade;
> 	create user alumno identified by duoc
> 	quota unlimited on users;
> 	grant create session, resource to alumno;

---
# COMANDOS BASICOS

> [!NOTE]
> **SELECT**: Se utiliza para recuperar datos de una o más tablas
> 
> 	SELECT employee_id, first_name, last_name
> 	FROM employees;
> 
>  ![[Pasted image 20231012152529.png]]	

> [!NOTE]
> **LOWER**: Convierte todo en minúscula
> 
> 	select employee_id,
> 	      lower(first_name) as Nombre_con_minuscula,
> 	      First_name,
> 	      Last_name
> 	from employees;
>   
>   ![[Pasted image 20231012153554.png]]

> [!NOTE]
> **UPPER**: Convierte todo en mayúscula
> 
> 	 select employee_id,
> 		  upper(first_name) as Nombre_con_mayuscula,
> 	      First_name,
> 	      Last_name
> 	 from employees;
> 
>   ![[Pasted image 20231012153624.png]]  

> [!NOTE]
> **CONCAT**: Concatenar (unir) dos o más cadenas de texto en una sola cadena
> 
> 	select first_name,
>          last_name,
>          CONCAT(first_name,last_name) as Nombre_apellido,
>          email
> 	from employees ;
> 
>  ![[Pasted image 20231012154014.png]]

> [!NOTE]
> **CONCAT + SUBSTR**: Extraer una subcadena de una cadena de texto
> 
> 	select first_name,
>          last_name,
>          CONCAT(first_name,last_name) as Nombre_apellido,
>          substr (first_name ,1) as ultima_letra_nombre
> 	  from employees ;
> 
>  ![[Pasted image 20231012154311.png]]

> [!NOTE]
> **LENGTH**: Longitud (número de caracteres) de una cadena de texto 
> 
> 	 select first_name,
>          length(FIRST_NAME) as caracteres
> 	 from employees ;
> 
>   ![[Pasted image 20231012154440.png]]
> 
> 	  select first_name,last_name,email,
>          concat(email,last_name),
>          length(FIRST_NAME) as caracteres,
>          substr (email,-2) as ultimas_letras_email
> 	  from employees 
> 	  where length(first_name)<=8
> 	  order by length(first_name) asc;
>  
>   ![[Pasted image 20231012154536.png]]

> [!NOTE]
> **INSTR**: Encontrar la posición de la primera ocurrencia de una subcadena en una cadena de texto
> 
> 	  select first_name,
>          instr(FIRST_NAME,'n') as caracteres
> 	  from employees ;
> 
>   ![[Pasted image 20231013190645.png]]

> [!NOTE]
> **LPAD OR RPAD**: Rellenar una cadena de texto a la izquierda o a la derecha, respectivamente, con un carácter específico hasta alcanzar una longitud deseada.
> 
>     select first_name,
>          rpad(first_name,8,'-')
> 	from employees ;
> 
>  ![[Pasted image 20231013190809.png]]

> [!NOTE]
> **TRIM**: Eliminar espacios en blanco u otros caracteres específicos del principio y/o final de una cadena de texto
> 
> 	 select first_name||' '||last_name,
>         trim(first_name||last_name) as eliminada       
> 	 from employees ;
>  
>  ![[Pasted image 20231013190915.png]]

> [!NOTE]
> 
> **REPLACE**: Reemplazar todas las apariciones de una subcadena con otra subcadena en una cadena de texto.
> 
> 	  select first_name,
>          replace(first_name,'e','-') as sustituye_letra
> 	  from employees ;
> 
>  ![[Pasted image 20231013190959.png]]
> 

---
# FUNCIONES NUMERICAS

> [!NOTE]
> **ROUND**: Redondear un número a un número específico de decimales.
> 
> 	  select 44.5,ROUND(44.5)  
> 	  from dual;
> 
>   ![[Pasted image 20231013191221.png]]

> [!NOTE]
> **TRUNC**: Truncar (eliminar) la parte decimal de un número, dejando solo la parte entera.
> 
> 	   select 44.55687561321378,
> 	   trunc( 44.55687561321378,5 )  
> 	   from dual;
> 
>   ![[Pasted image 20231013191314.png]]

> [!NOTE]
> **MOD**: Calcular el residuo de la división de un número por otro
> 
> 	   select mod (23,2)
> 	   from dual;
> 
>   ![[Pasted image 20231013191354.png]]

---
# FUNCIONES FECHAS

> [!NOTE]
> **MONTHS BETWEEN**: Calcular la diferencia en meses entre dos fechas
> 
> 	select hire_date ,sysdate,
> 	    round( months_between (sysdate,hire_date))
>     from employees;
>    
>  ![[Pasted image 20231013191553.png]]

> [!NOTE]
> **ADD MONTHS**: Agregar un número específico de meses a una fecha.
> 
> 	select hire_date ,
>       add_months(hire_date, 1) as meses_agregados
>     from employees;
>   
>  ![[Pasted image 20231013191700.png]]

> [!NOTE]
> **ROUND**: Redondear la fechas al día siguiente
> 
> 	select hire_date , sysdate,
> 	    round(sysdate) as dia_sig   
> 	from employees;
> 
>  ![[Pasted image 20231013192058.png]]

> [!NOTE]
> **TRUNC**
> 
> 	select sysdate,
> 	    trunc(sysdate,'day') as dia_sig   
> 	from dual;
> 	
>  ![[Pasted image 20231013192150.png]]

---
# FUNCIONES TIPO DATOS

> [!NOTE]
> **TO_DATE**: Cambiar el formato a fecha
> 
> 	select '01-02-2016',
> 		to_date('01-02-2016','DD/MM/YYYY') 
> 	from dual;
> 	
>  ![[Pasted image 20231013192328.png]]

> [!NOTE]
> **NVL** : Proporcionar un valor predeterminado si una expresión es nula (null)
> 
> 	select last_name,first_name,commission_pct*salary,manager_id,
> 		NVL(commission_pct,0),
> 		salary,
> 	    salary+(salary*commission_pct),
> 	    NVL (to_char(manager_id),'No tiene jefe') as Jefe
> 	from employees
> 	order by 3 asc;
> 	
>  ![[Pasted image 20231013192535.png]]

> [!NOTE]
> **DESCRIBE**: Obtener información sobre la estructura de una tabla
> 
> 	describe employees;
> 	
>  ![[Pasted image 20231013192948.png]]

> [!NOTE]
> **NVL2**: Proporcionar un valor alternativo basado en si una expresión es nula o no
> 
> 	select first_name,salary, commission_pct,
> 		nvl2(commission_pct,'salario + comision','solo tu  salario') as "Salario Mensual"
> 	from employees;
> 	
>  ![[Pasted image 20231013193248.png]]

> [!NOTE]
> **NULLIF**: Comparar si son iguales = NULL
> 
> 	select first_name,last_name,
> 		 length(first_name)largo_nombre,
> 		 length(last_name)largo_apellido, 
> 		 nullif(length(first_name),length(last_name)) as resultado_funcion_nullIf
> 	from employees;
> 	
>  ![[Pasted image 20231013193425.png]]

> [!NOTE]
> **COALESCE**:  
> 	- si ambos son nulos, devuelve nulo
> 	- si una no es nula, se muestra
> 	- si ambas tienen valor, devuelve la primera expresión que se solicite
> 
> 	select first_name,commission_pct,manager_id,
> 		coalesce(commission_pct,manager_id,999) as resultado_funcion
> 	from employees;

---

# EXPRESIONES

> [!NOTE]
> **CASE**: Realizar evaluaciones condicionales en las consultas
> 
> 	select EMPLOYEE_ID,job_id,DEPARTMENT_ID,salary,
> 		CASE job_id when 'PR_REP' then 1.15*salary
>             when 'MK_MAN' then 1.20*salary
>             else salary
>             end as "Salario final"
> 	from employees
> 	where department_id in (70,20,110);
> 	
>  ![[Pasted image 20231013193831.png]]

> [!NOTE]
> **DECODE**: Realizar evaluaciones condicionales en SQL de manera similar a la expresión CASE
> 
> 	select EMPLOYEE_ID,job_id,DEPARTMENT_ID,salary,
> 		decode (job_id, 'PR_REP' , 1.15*salary,
>                   'MK_MAN' , 1.20*salary
>                   ,salary) as salario_aumentado
> 	from employees
> 	where department_id in (20,70,110);
> 	
>  ![[Pasted image 20231013193958.png]]

---
# FUNCIONES DE GRUPO

> [!NOTE]
> **AVG**: Calcular el promedio (media aritmética)
> 
> 	select department_id,avg(salary)
> 	from employees
> 	group by department_id
> 	order by 1 asc;
> 	
>  ![[Pasted image 20231013194155.png]]

> [!NOTE]
> **COUNT**: Contar el número de filas que cumplen con ciertos criterios en una consulta
> 
> 	select department_id,count(department_id)
> 	from employees
> 	group by department_id
> 	order by 1 asc;
> 	
>  ![[Pasted image 20231013194259.png]]

> [!NOTE]
> **MAX**: Valor máximo en un conjunto de valores
> 
> 	select max(salary),min(salary)
> 	from employees;
> 	select salary
> 	from employees
> 	order by salary asc;
> 	
>  ![[Pasted image 20231013194350.png]]

> [!NOTE]
> **MIN**: valor mínimo en un conjunto de valores
> 
> 	select department_id,min(salary)
> 	from employees
> 	group by department_id
> 	order by 1 asc;
> 	
>  ![[Pasted image 20231013194504.png]]

> [!NOTE]
> *SUM**: Calcular la suma de los valores en una columna numérica
> 
> 	select department_id,sum(salary)
> 	from employees
> 	group by department_id
> 	order by 1 asc;
> 	
>  ![[Pasted image 20231013195022.png]]

> [!NOTE]
> **STDDEV**: Calcular la desviación estándar de un conjunto de valores en una columna.
> 
> 	select department_id,stddev(salary)
> 	from employees
> 	group by department_id
> 	order by 1 asc;
> 	
>  ![[Pasted image 20231013195124.png]]

> [!NOTE]
> **VARIANCE**: Calcular la varianza de un conjunto de valores en una columna
> 
> 	select variance(salary)
> 	from employees;
> 	
>  ![[Pasted image 20231013195225.png]]

> [!NOTE]
> **DISTINCT**: Eliminar duplicados de los resultados de una consulta

---
# SENTENCIA JOIN

> [!NOTE]
> **JOIN SIMPLE**: Unión entre dos tablas en una consulta
> 
> 	select a.first_name ,
>     a.last_name,
>     b.job_id,
>     b.job_title
>     from employees a , jobs b
>     where a.job_id=b.job_id;
>     
>  ![[Pasted image 20231016154337.png]]

> [!NOTE]
>**JOIN NORMAL** (PRIMERA TABLA)
> 
> 	   select a.first_name,
>        a.last_name,
>        b.job_id,
>        b.job_title
>        from employees a join jobs b on (a.job_id=b.job_id)
>        order by 1 asc;
>        
>  ![[Pasted image 20231016154555.png]]

> [!NOTE]
> **NATURAL JOIN**: Unión que se realiza automáticamente basándose en las columnas con nombres coincidentes entre dos tablas
> 
> 	select employee_id,
> 	       last_name,
> 	       first_name,
> 	       job_title,
> 	       job_id
> 	from employees  natural join JOBS ;
> 
>  ![[Pasted image 20231016154721.png]]
> 
> 	select employee_id "ID EMPLEADO",
> 	       first_name"NOMBRE",
> 	       last_name"APELLIDO",
> 	       department_id"ID DEPARTAMENTO",
> 	       department_name"NOMBRE DEL DEPARTAMENTO"
> 	from employees natural join  DEPARTMENTS ;
> 	
>  ![[Pasted image 20231016154738.png]]

> [!NOTE]
> **USING**: La cláusula `USING` en SQL se utiliza en conjunto con operaciones de unión, como `INNER JOIN` o `NATURAL JOIN`, para especificar las columnas que se deben utilizar para realizar la unión entre dos tablas. La diferencia principal entre `USING` y `ON` es que `USING` permite especificar directamente las columnas que deben coincidir sin tener que repetir el nombre de la tabla.
> 
> 	select employee_id,
> 	       last_name,
> 	       first_name,
> 	       job_title,
> 	       job_id
> 	from employees join jobs 
> 	using (job_id);
> 	
>  ![[Pasted image 20231016154853.png]]
>    
> 	select employee_id "ID EMPLEADO",
> 			first_name"NOMBRE",
> 		       last_name"APELLIDO",
> 		       department_id"ID DEPARTAMENTO",
> 		       department_name"NOMBRE DEL DEPARTAMENTO"
> 	from employees join  DEPARTMENTS 
> 	using(department_id);
> 	
>  ![[Pasted image 20231016154936.png]]

> [!NOTE]
> **Clausula ON**: Para especificar las condiciones de unión entre dos o más tablas
> 
> 	select a.first_name,
> 	       a.last_name,
> 	       b.job_id,
> 	       b.job_title
> 	from employees a join jobs b on (a.job_id=b.job_id)
> 	where a.employee_id in(205,206,110) and b.job_id = 'AC_MGR'
> 	order by 1 asc;
> 
>  ![[Pasted image 20231016155110.png]]

> [!NOTE]
> **LEFT OUTER JOIN**: Combinar dos tablas basándose en una condición de unión, y devuelve todas las filas de la tabla izquierda (la primera mencionada en la cláusula `FROM`), y las filas coincidentes de la tabla derecha (la segunda mencionada en la cláusula `JOIN`). Si no hay coincidencias, las columnas de la tabla derecha contendrán valores nulos.
> 
> 	select a.EMPLOYEE_ID,
> 	       a.department_id,
> 	       b.department_name       
> 	from employees a LEFT OUTER join departments b 
> 		on (a.department_id=b.department_id)
> 	order by employee_id ;
> 
>  ![[Pasted image 20231016155456.png]]

> [!NOTE]
> **RIGHT OUTER JOIN**: Combinar dos tablas basándose en una condición de unión, y devuelve todas las filas de la tabla derecha (la segunda mencionada en la cláusula `FROM`), y las filas coincidentes de la tabla izquierda (la primera mencionada en la cláusula `JOIN`). Si no hay coincidencias, las columnas de la tabla izquierda contendrán valores nulos.
> 
> 	select a.EMPLOYEE_ID,
> 	       b.department_id,
> 	       b.department_name       
> 	from employees a RIGHT OUTER join departments b 
> 	on (a.department_id=b.department_id)
> 	order by employee_id ;
> 	
>  ![[Pasted image 20231016155514.png]]

> [!NOTE]
> **FULL OUTER JOIN**: Combinar dos tablas basándose en una condición de unión, y devuelve todas las filas de ambas tablas, incluyendo aquellas que no tienen coincidencias en la otra tabla. Si no hay coincidencias, las columnas de la tabla sin coincidencias contendrán valores nulos.
> 
> 	select a.EMPLOYEE_ID,
> 	       b.department_id,
> 	       b.department_name       
> 	from employees a FULL OUTER join departments b 
> 	on (a.department_id=b.department_id)
> 	order by employee_id ;
> 
>  ![[Pasted image 20231016155627.png]]

---
# SUBCONSULTAS

> [!NOTE]
> **SUBCONSULTA**: Se utiliza para realizar operaciones más complejas o para proporcionar valores a la consulta principal 
> 
> 	select employee_id"Id.Empleado",
> 	       concat(first_name,concat(' ',last_name)) as nombre_completo,
> 	       email,
> 	       salary"Salario",
> 	       job_id"ID.Trabajo",
> 	       job_title"Nombre Trabajo"
> 	from employees  join jobs 
> 	using (job_id)
> 	where salary between (select round(avg(salary))
> 				                            from employees) 
> 				                            and
> 					                     (select sum(salary)
> 	                               from employees)
> 	order by 1;
> 	
>  ![[Pasted image 20231016160209.png]]

> [!NOTE]
> **SUBCONSULTA (HAVING)**: Combinación con la cláusula `GROUP BY` para filtrar los resultados de una consulta agregada basándose en una condición
> 
> 	select department_ID, min(salary)
> 	from employees
> 	group by department_id
> 	having min(salary) > (select min(salary)
> 	from employees
> 	where department_id = 60)
> 	order by 1;
> 	
>  ![[Pasted image 20231016160328.png]]

---
# SENTENCIAS PARA WHERE

> [!NOTE]
> **IN**: Verificar si un valor se encuentra dentro de un conjunto de valores o resultados de una subconsulta
> 
> 	select department_id,job_id,salary
> 	from employees
> 	where salary in(select min(salary)
> 	from employees
> 	group by department_id)
> 	order by 1;
> 
>  ![[Pasted image 20231016160510.png]]

---
# VISTAS

> [!NOTE]
> **CREAR UNA VISTA**: Las vistas son útiles para simplificar consultas complejas, proporcionar una capa de abstracción sobre las tablas subyacentes y mejorar la seguridad al limitar el acceso directo a las tablas.
> 
> 	create or replace view informe_de_salarios_emp_204 
> 	as
> 	( 
> 	select employee_id"Identificacion Empleado",
> 	       concat(first_name,concat(' ',Last_name))"Empleado",
> 	       job_id"ID_Trabajo",
> 	       concat('$',(to_char(Salary,'99g999')))"Salario"
> 	from employees
> 	where salary = (select salary
> 	from employees
> 	where employee_id=204)
> 	);
> 	
>  ![[Pasted image 20231016160812.png]]
>  ![[Pasted image 20231016160840.png]]
>  ![[Pasted image 20231016160905.png]]

> [!NOTE]
> **DESC**: Mostrar descripción de la vista
> 
> 	desc INFORME_DE_SALARIOS_EMP_204
> 	
>  ![[Pasted image 20231016161038.png]]

> [!NOTE]
> **SELECCIONANDO VISTA**
> 
> 	select *
> 	from informe_de_salarios_emp_204;
> 	
>  ![[Pasted image 20231016160905.png]]

> [!NOTE]
> **ELIMINAR VISTA**
> 
> 	drop view informe_de_salarios_emp_204;
> 	
>  ![[Pasted image 20231016161338.png]]
>  ![[Pasted image 20231016161351.png]]


