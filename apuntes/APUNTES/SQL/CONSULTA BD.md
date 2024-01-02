	alter user hr account unlock;
	alter user HR identified by hr;
	
	drop user alumno cascade;
	create user alumno identified by duoc
	quota unlimited on users;
	grant create session, resource to alumno;

| ORDEN (SELECT(COLUMNAS) |
| FROM (DE QUE TABLA PROVIENE LOS DATOS) |
| WHERE (CONDICION) |
| GROUP BY (AGRUPAR POR ALGO EN PARTICULAR) |
| ORDER BY (FORMA DE ORDENAR) |

SELECT 

	select employee_id, first_name,LAST_NAME
	from employees;

 ![[Pasted image 20231012152529.png]]	
LOWER

	select employee_id,
	      lower(first_name) as Nombre_con_minuscula,
	      First_name,
	      Last_name
	from employees;
  
  ![[Pasted image 20231012153554.png]]
UPPER

	 select employee_id,
		  upper(first_name) as Nombre_con_minuscula,
	      First_name,
	      Last_name
	 from employees;

  ![[Pasted image 20231012153624.png]]  
CONCAT

	select first_name,
         last_name,
         CONCAT(first_name,last_name) as Nombre_apellido,
         email
	from employees ;

 ![[Pasted image 20231012154014.png]]
CONCAT + SUBSTR

	select first_name,
         last_name,
         CONCAT(first_name,last_name) as Nombre_apellido,
         substr (first_name ,1) as ultima_letra_nombre
	  from employees ;

 ![[Pasted image 20231012154311.png]]
LENGTH  

	 select first_name,
         length(FIRST_NAME) as caracteres
	 from employees ;

  ![[Pasted image 20231012154440.png]]

	  select first_name,last_name,email,
         concat(email,last_name),
         length(FIRST_NAME) as caracteres,
         substr (email,-2) as ultimas_letras_email
	  from employees 
	  where length(first_name)<=8
	  order by length(first_name) asc;
 
  ![[Pasted image 20231012154536.png]]
INSTR

	  select first_name,
         instr(FIRST_NAME,'n') as caracteres
	  from employees ;

  ![[Pasted image 20231013190645.png]]
LPAD OR RPAD

    select first_name,
         rpad(first_name,8,'-')
	from employees ;

 ![[Pasted image 20231013190809.png]]
TRIM

	 select first_name||' '||last_name,
        trim(first_name||last_name) as eliminada       
	 from employees ;
 
 ![[Pasted image 20231013190915.png]]
REPLACE

	  select first_name,
         replace(first_name,'e','-') as sustituye_letra
	  from employees ;

 ![[Pasted image 20231013190959.png]]

# ⟪⟪⟪⟪⟪⟪[FUNCIONES NUMERICAS]⟫⟫⟫⟫⟫⟫⟫

ROUND

	  select 44.5,ROUND(44.5)  
	  from dual;

  ![[Pasted image 20231013191221.png]]
TRUNC

	   select 44.55687561321378,
	   trunc( 44.55687561321378,5 )  
	   from dual;

  ![[Pasted image 20231013191314.png]]
MOD

	   select mod (23,2)
	   from dual;

  ![[Pasted image 20231013191354.png]]
# ⟪⟪⟪⟪⟪⟪⟪⟪⟪[FUNCIONES FECHAS]⟫⟫⟫⟫⟫⟫⟫⟫⟫

MONTHS BETWEEN

	select hire_date ,sysdate,
    round( months_between (sysdate,hire_date))
    from employees;
   
 ![[Pasted image 20231013191553.png]]
ADD MONTHS

	select hire_date ,
      add_months(hire_date, 1) as meses_agregados
    from employees;
  
 ![[Pasted image 20231013191700.png]]
ROUND

	select hire_date , sysdate,
    round(sysdate) as dia_sig   
	from employees;

 ![[Pasted image 20231013192058.png]]
TRUNC

	select sysdate,
    trunc(sysdate,'day') as dia_sig   
	from dual;
	
 ![[Pasted image 20231013192150.png]]

# ⟪⟪⟪⟪⟪⟪[FUNCIONES TIPO DATOS]⟫⟫⟫⟫⟫⟫

TO_DATE

	select '01-02-2016',to_date('01-02-2016','DD/MM/YYYY') 
	from dual;
	
 ![[Pasted image 20231013192328.png]]
NVL

	select last_name,first_name,commission_pct*salary,manager_id,
	NVL(commission_pct,0),
	salary,
    salary+(salary*commission_pct),
    NVL (to_char(manager_id),'No tiene jefe') as Jefe
	from employees
	order by 3 asc;
	
 ![[Pasted image 20231013192535.png]]
DESCRIBE

	describe employees;
	
 ![[Pasted image 20231013192948.png]]
NVL2

	select first_name,salary, commission_pct,
		nvl2(commission_pct,'salario + comision','solo tu  salario') as "Salario Mensual"
	from employees;
	
 ![[Pasted image 20231013193248.png]]
NULLIF (comparar si son iguales =nulo)

	select first_name,last_name,
	 length(first_name)largo_nombre,
	 length(last_name)largo_apellido, 
	 nullif(length(first_name),length(last_name)) as resultado_funcion_nullIf
	from employees;
	
 ![[Pasted image 20231013193425.png]]
COALESCE (si ambos son nulos devuelve nulo///si una no es nula se muestra/// si ambas tienen valor, devuelve la primera expresión que se solicite)

	select first_name,commission_pct,manager_id,
	coalesce(commission_pct,manager_id,999) as resultado_funcion
	from employees;
# ⟪⟪⟪⟪⟪⟪⟪⟪⟪[EXPRESIONES]⟫⟫⟫⟫⟫⟫⟫⟫⟫

CASE

	select EMPLOYEE_ID,job_id,DEPARTMENT_ID,salary,
		CASE job_id when 'PR_REP' then 1.15*salary
            when 'MK_MAN' then 1.20*salary
            else salary
            end as "Salario final"
	from employees
	where department_id in (70,20,110);
	
 ![[Pasted image 20231013193831.png]]
DECODE

	select EMPLOYEE_ID,job_id,DEPARTMENT_ID,salary,
	decode (job_id, 'PR_REP' , 1.15*salary,
                  'MK_MAN' , 1.20*salary
                  ,salary) as salario_aumentado
	from employees
	where department_id in (20,70,110);
	
 ![[Pasted image 20231013193958.png]]

# ⟪⟪⟪⟪⟪⟪⟪[FUNCIONES DE GRUPO]⟫⟫⟫⟫⟫⟫⟫

AVG (promedio)

	select department_id,avg(salary)
	from employees
	group by department_id
	order by 1 asc;
	
 ![[Pasted image 20231013194155.png]]
COUNT (cantidad del grupo)

	select department_id,count(department_id)
	from employees
	group by department_id
	order by 1 asc;
	
 ![[Pasted image 20231013194259.png]]
MAX (numero mayor)

	select max(salary),min(salary)
	from employees;
	select salary
	from employees
	order by salary asc;
	
 ![[Pasted image 20231013194350.png]]
MIN (numero menor)

	select department_id,min(salary)
	from employees
	group by department_id
	order by 1 asc;
	
 ![[Pasted image 20231013194504.png]]
SUM (suma del grupo)

	select department_id,sum(salary)
	from employees
	group by department_id
	order by 1 asc;
	
 ![[Pasted image 20231013195022.png]]
STDDEV (diferencia)

	select department_id,stddev(salary)
	from employees
	group by department_id
	order by 1 asc;
	
 ![[Pasted image 20231013195124.png]]
VARIANCE(diferencia)

	select variance(salary)
	from employees;
	
 ![[Pasted image 20231013195225.png]]
DISTINCT (ELIMINA AQUELLOS VALORES QUE SEAN REPETIDOS)

# ⟪⟪⟪⟪⟪⟪⟪⟪⟪[SENTENCIA JOIN]⟫⟫⟫⟫⟫⟫⟫⟫⟫

JOIN SIMPLE

	select a.first_name ,
    a.last_name,
    b.job_id,
    b.job_title
    from employees a , jobs b
    where a.job_id=b.job_id;
    
 ![[Pasted image 20231016154337.png]]
JOIN NORMAL (PRIMERA TABLA)

	   select a.first_name,
       a.last_name,
       b.job_id,
       b.job_title
       from employees a join jobs b on (a.job_id=b.job_id)
       order by 1 asc;
       
 ![[Pasted image 20231016154555.png]]
NATURAL JOIN (APG!)

	select employee_id,
	       last_name,
	       first_name,
	       job_title,
	       job_id
	from employees  natural join JOBS ;

 ![[Pasted image 20231016154721.png]]

	select employee_id "ID EMPLEADO",
	       first_name"NOMBRE",
	       last_name"APELLIDO",
	       department_id"ID DEPARTAMENTO",
	       department_name"NOMBRE DEL DEPARTAMENTO"
	from employees natural join  DEPARTMENTS ;
	
 ![[Pasted image 20231016154738.png]]
USING

	select employee_id,
	       last_name,
	       first_name,
	       job_title,
	       job_id
	from employees join jobs 
	using (job_id);
	
 ![[Pasted image 20231016154853.png]]
   
	select employee_id "ID EMPLEADO",
			first_name"NOMBRE",
		       last_name"APELLIDO",
		       department_id"ID DEPARTAMENTO",
		       department_name"NOMBRE DEL DEPARTAMENTO"
	from employees join  DEPARTMENTS 
	using(department_id);
	
 ![[Pasted image 20231016154936.png]]

Clausula ON

	select a.first_name,
	       a.last_name,
	       b.job_id,
	       b.job_title
	from employees a join jobs b on (a.job_id=b.job_id)
	where a.employee_id in(205,206,110) and b.job_id = 'AC_MGR'
	order by 1 asc;

 ![[Pasted image 20231016155110.png]]
LEFT OUTER JOIN(A--->B)

	select a.EMPLOYEE_ID,
	       a.department_id,
	       b.department_name       
	from employees a LEFT OUTER join departments b 
		on (a.department_id=b.department_id)
	order by employee_id ;

 ![[Pasted image 20231016155456.png]]
RIGHT OUTER JOIN(A<----B)

	select a.EMPLOYEE_ID,
	       b.department_id,
	       b.department_name       
	from employees a RIGHT OUTER join departments b 
	on (a.department_id=b.department_id)
	order by employee_id ;
	
 ![[Pasted image 20231016155514.png]]
FULL OUTER JOIN(A<----->B)

	select a.EMPLOYEE_ID,
	       b.department_id,
	       b.department_name       
	from employees a FULL OUTER join departments b 
	on (a.department_id=b.department_id)
	order by employee_id ;

 ![[Pasted image 20231016155627.png]]

# ⟪⟪⟪⟪⟪⟪⟪⟪⟪[SUBCONSULTAS]⟫⟫⟫⟫⟫⟫⟫⟫⟫

SUBCONSULTA

	select employee_id"Id.Empleado",
	       concat(first_name,concat(' ',last_name)) as nombre_completo,
	       email,
	       salary"Salario",
	       job_id"ID.Trabajo",
	       job_title"Nombre Trabajo"
	from employees  join jobs 
	using (job_id)
	where salary between (select round(avg(salary))
				                            from employees) 
				                            and
					                     (select sum(salary)
	                               from employees)
	order by 1;
	
 ![[Pasted image 20231016160209.png]]
SUBCONSULTA (HAVING)

	select department_ID, min(salary)
	from employees
	group by department_id
	having min(salary) > (select min(salary)
	from employees
	where department_id = 60)
	order by 1;
	
 ![[Pasted image 20231016160328.png]]

# ⟪⟪⟪⟪[SENTENCIAS PARA WHERE]⟫⟫⟫⟫
IN

	select department_id,job_id,salary
	from employees
	where salary in(select min(salary)
	from employees
	group by department_id)
	order by 1;

 ![[Pasted image 20231016160510.png]]

# ⟪⟪⟪⟪⟪⟪⟪⟪⟪[VISTAS]⟫⟫⟫⟫⟫⟫⟫⟫⟫
CREAR UNA VISTA

	create or replace view informe_de_salarios_emp_204 
	as
	( 
	select employee_id"Identificacion Empleado",
	       concat(first_name,concat(' ',Last_name))"Empleado",
	       job_id"ID_Trabajo",
	       concat('$',(to_char(Salary,'99g999')))"Salario"
	from employees
	where salary = (select salary
	from employees
	where employee_id=204)
	);
	
 ![[Pasted image 20231016160812.png]]
 ![[Pasted image 20231016160840.png]]
 ![[Pasted image 20231016160905.png]]
DESC (MOSTRAAR DESCRIPCION DE LA VISTA)

	desc INFORME_DE_SALARIOS_EMP_204
	
 ![[Pasted image 20231016161038.png]]
SELECCIONANDO VISTA
	
	select *
	from informe_de_salarios_emp_204;
	
 ![[Pasted image 20231016160905.png]]
ELIMINAR VISTA

	drop view informe_de_salarios_emp_204;
	
 ![[Pasted image 20231016161338.png]]
 ![[Pasted image 20231016161351.png]]


