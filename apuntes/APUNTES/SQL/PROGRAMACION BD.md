PRIMER BOQUE ANONIMO
		
	declare 
	
	v_nombre varchar2(45);
	v_salario varchar2(25);
	n_depart varchar2(20);
	
	begin
	    select concat(first_name,concat(' ',last_name)),
	           to_char(salary,('$999g999')) ,
	           department_name
	    into v_nombre,v_salario,n_depart
	    from employees join departments
	    using (department_id)
	    where employee_id=110;
	        DBMS_OUTPUT.put_line('Mi nombre es: '||v_nombre||
	                            ' mi sueldo es: '||v_salario||
	                            ' y trabajo en: '||n_depart);
	end;