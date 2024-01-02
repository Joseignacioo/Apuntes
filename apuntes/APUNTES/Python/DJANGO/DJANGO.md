
# ENTORNO VIRTUAL

1- Crear Carpeta
2- CNTRL + Ñ (abrir consola en visual)
3- Creamos entorno virtual (python -m venv nombre al entorno)
	![[Pasted image 20231121004423.png]]
4- Ingresamos a la ruta de Scripts y escribir #(./activate)
5- Volvemos a la ruta de la carpeta instalar django (pip install django)
6- Ver las intalaciones del django (pip freeze)
	![[Pasted image 20231121004844.png]]

# EMPEZAMOS

1- Creamos el proyecto (django-admin startproject nombre_proyecto)
	![[Pasted image 20231121005713.png]]
2- Entramos a la carpeta (cd seguridad)
3- Creamos una app (python manage.py startapp nombre_app)
	![[Pasted image 20231121005855.png]]
4- Iniciamos el proyecto (python manage.py runserver)
	![[Pasted image 20231121010211.png]]

# PARTE 1

1- Creamos un home nos vamos a views.py
	![[Pasted image 20231121011025.png]]
2- Creamos un urls.py en la carpeta app, generamos las rutas path 
	![[Pasted image 20231121011305.png]]
	![[Pasted image 20231121012050.png]]
3- Cargaremos las urls.py de la app al urls main
	![[Pasted image 20231121012021.png]]
4-	Instalamos la app en settings.py 
	![[Pasted image 20231121012431.png]]
5- Creamos la carpeta templates en la carpeta app para los archivos html
	![[Pasted image 20231121040348.png]]
6- Creamos la carpeta static en la carpeta app para los archivos CSS, IMG, JS
	![[Pasted image 20231121040435.png]]
7- Creamos en settings el siguiente codigo
	![[Pasted image 20231121040848.png]]
	8- 

8- En el html tendremos que colocar {% load static %} para poder llamar los archivos staticos como el CSS
	![[Pasted image 20231121042005.png]]

# PARTE 2

- IMPORTANTE:
	- CharFiled: Este campo se utiliza para almacenar cadenas de texto de longitud variable.
	- IntegerField: Este campo se utiliza para almacenar numeros enteros.
	- FloatField: este campo se utiliza para almacenar numeros decimales.
	- BooleanField: Este campo se utiliza para almacenar valores booleanos (True o False).
	- DateTimeField: Este campo se utiliza para almacenar fechas y horas.
	- DateField: Este campo se utiliza para almacenar fechas.
	- TimeField: Este campo se utiliza para almacenar horas
	Dentro de los parentesis: 
	- null: Si se establece en True, el campo permitira. valores nulos en la base de datos.
	- blank: Si se establece en True, el campo permitira valores en blanco (es decir, cadenas vacias) en los formularios.
	- default: Este parametro permite establecer un valor predeterminado para el campo.
	- choices: este parametro permite establecer una lisyta de opciones disponibles para el campo.
	PARA MIGRACION:
	-python manage.py migrate
	-python manage.py makemigrations

1- EJEMPLO:
	
	class Usuario(models.Model):

	# Campos de texto
    nombre_usuario = models.CharField(max_length=30, unique=True)
    nombre = models.CharField(max_length=50)
    apellidos = models.CharField(max_length=50)
    email = models.EmailField(unique=True)

    # Campos numéricos
    edad = models.PositiveIntegerField()
    peso = models.DecimalField(max_digits=5, decimal_places=2)
    altura = models.FloatField()

    # Campos de fechas
    fecha_nacimiento = models.DateField()
    ultimo_login = models.DateTimeField(auto_now=True)

    # Campos booleanos
    esta_activa = models.BooleanField(default=True)
    es_personal = models.BooleanField(default=False)

    # Campos con opciones
    OPCIONES_ROL = [
        ('usuario', 'Usuario normal'),
        ('admin', 'Administrador'),
    ]
    roles = models.CharField(max_length=7, choices=OPCIONES_ROL, default='usuario'
2- Registro

	<form method="POST" class="formulario">
                    {% csrf_token %}
                    <div class="entrada">
                        <label for="nombre_usuario">Nombre de usuario:</label>
                        <input type="text" name="nombre_usuario" required>
                    </div>
                    <div class="entrada">
                        <label for="nombre">Nombre:</label>
                        <input type="text" name="nombre" required>
                    </div>
                    <div class="entrada">
                        <label for="apellidos">Apellidos:</label>
                        <input type="text" name="apellidos" required>
                    </div>
                    <div class="entrada">
                        <label for="email">Email:</label>
                        <input type="email" name="email" required>
                    </div>
                    <div class="entrada">
                    <label for="fecha_nacimiento">Fecha de nacimiento:</label>
                    <input type="date" name="fecha_nacimiento" required>
                    </div>
                    <div class="entrada">
                        <div class="columna">
                            <div class="caja-select">
                            <select name="roles" required>
                                <option hidden>Tipo de usuario</option>
                                <option value="usuario">Usuario normal</option>
                            <option value="admin">Administrador</option>
                            </select>
                            </div>
                        </div>
                    </div>
                    <button type="submit">Enviar</button>
                </form>
                
	![[Pasted image 20231121053637.png]]
3- Creamos en la carpeta app forms.py 
	![[Pasted image 20231121054243.png]]
	![[Pasted image 20231121054550.png]]
4- ya vinculado el modelo con el formulario generamos la vista en views.py
	![[Pasted image 20231121055446.png]]
	![[Pasted image 20231121055813.png]]
5- login
![[Pasted image 20231121061249.png]]
![[Pasted image 20231121061712.png]]
nos vamos a settings 
![[Pasted image 20231121061637.png]]
crear super usuario python manage.py createsuperuser
