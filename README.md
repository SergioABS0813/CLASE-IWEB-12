# CLASE-IWEB-12
Session, Cifrado de datos y DTO


## Qués es una cookie?
Con session nosotros podemos crear cookies, estas guardan información y en JAVA se llaman JSESSIONID.

El servidor es el que reparte las cookies (proveedor de Cookies).

Google para identificarnos utiliza cookies, pero si yo entro en privado se crea otra cookie.

Por ejemplo, en la página del profesor en donde creó la hoja de cálculo, se puede ver en la esquina mi nombre de usuario, mi foto usada en google. Esto se manda por Session:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/8ae730b7-1be8-45b0-8095-51d283179abd)

Sirve para compras por internet y "agregar cosas al carrito". Eso solamente se puede hacer por Session:

## ----------------------- Cómo usar Session en JAVA?  ----------------------- 

Sirve para **logueos** (inicios de sesión) o también para mandar parámetros que existen temporalmente y luego se borran.

## HTTPSession
Las sesiones son objetos de clase **HttpSession**. La información de las sesiones se almacena en las **cookies** y estas son enviadas entre cliente y servidor.

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/c0b47c3f-5168-4eb6-9142-58a91dc97481)

## Sesión para envío de mensajes únicos
Queremos que aparezca un mensaje de "trabajo creado correctamente", sin embargo, ese mensaje se manda y podemos cambiarle de esta manera:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/4c6f7cff-538f-45de-9dbf-724072b2ded8)

Ahora no mandaremos por arriba sino por Session para que no pase dicho error con el mensaje único:

Ahora en JobServlet sería:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/d01025f4-57ca-4233-ab66-925aff3f8568)

Luego vamos al jsp de listaJob para que aparezaca el mensaje de de "trabajo creado correctamente" y luego vemos que le damos a refrescar y el mensaje desaparece por el remove hecho al último:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/e247e0b2-2ed9-415e-be6e-e2f95a500f69)

## Sesión para logueo de usuarios
Para ello **se coloca un parámetro para indicar que el usuario esté logueado** porque no siempre esatrá activo cuando **cierre sesión**.

Recomendación del Profe: **Crear un Servlet para el login**

Creamos Servlet y que en GET (obvio) nos dirija a un jsp de login:

**-------------------- A partir de este punto e manejo de HTML empieza --------------------**

-Buscamos en bootstrap:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/12c73064-0ad8-4ebc-9e1d-bc530dca95af)

-Copiamos el body y luego pegamos en el body del jsp de login:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/9fbf0937-7000-4318-804b-34000d771359)

(OJO **incluir la cabecera de bootstrap siempre**) **La dirección va a depender de dónde esté situado el jsp (ver video IWEB clase 12 48:50)**

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/effab603-b676-4cca-a2cb-dbf304530fdb)

Luego hacemos los cambios necesarios para que el login quede bien.

Entre ellos colocar nuestro propio footer ya que el que copiamos se conecta al servidor de bootstrap:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/23c40d17-ade4-4d59-b49a-89579d035210)

Notamos que nos aparece feo y no como lo copiamos: (**ver clase de IWEB 12 51:30**)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/22cc9de6-be45-44f7-881e-a594b1476720)

Inspeccionamos:

Copiamos el Style porque es necesario. --> todavía no está como queremos

Copiamos el link sign-in.css, para eso primero tenemos que tener el archivo css empleado por bootstrap:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/6e6d4e61-c9dd-4577-b111-efe74f93687b)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/a8d9ba8d-21e3-4588-ac56-72515ae5acff)

Movemos a la carpeta css en el proyecto: 

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/48514f17-d641-4c2f-8a1d-0f2721edc4aa)

El orden tal cual está en bootstrap tenemos que seguir en nuestro jsp en cuanto al link:

Además, el **link del css en el jsp debe estar sí o sí, si no, no hay enlace con el css sing-in (Copiamos y pegamos de bootstrap)**

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/a7e6ca2d-ad46-4955-b1d5-9dbcd2285159)

Luego de copiarlo, le hacemos la modificación:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/aa613e3d-0df1-4d40-be7d-676359b8f868)

OJO: El type email valida que siempre esté en "@"

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/568ba712-8fc0-4993-87e0-f2568fdba090)


**-------------------- A partir de este punto e manejo de HTML finaliza --------------------**

Recordamos los parámetros necesarios para enviar por POST al Servlet:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/281527a6-be01-4fa7-b291-6a9240fc3cee)

**Recordar que no se debe dejar el password en base de datos como texto plano:**

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/b6b9fc4b-908d-42fc-92f4-e23ed3c6061a)

Hacemos el método para que valide al usuario y contraseña:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/51da5302-c410-4560-9376-837dda6bb990)

En LoginServlet:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/925d66c2-004b-4760-9f14-aeea378e9aea)

Luego de iniciar la sesión, vamos a guardar las credenciales del usuario para que puedan ser vistas o usadas en la página web como en google, facebook, etc:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/f2f06354-237b-4e8c-b3f7-2be50f8320a6)

En el login jsp en caso exista error en el logueo de usuario:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/77be8bf1-dab2-4514-bd23-8a44a2edcaa6)

Ahora luego de que ya exista el session (**Implementación NavBar con Credenciales**): (si se loguea el usuario, en el navbar se podrá visualizar el nombre del usuario)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/e2d6a920-bc7e-4383-890e-aae5f4a5aa82)

Ahora hacemos el **flujo de cierre de sesión**

Creamos el botón de cierre de sesión:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/6ce55e6a-5780-42e5-a7dd-092329b3da7c)

En el LoginServlet: (**La redirección puede ser a cualquier lado, de preferencia al loginform**)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/eb37f1e3-fe41-446a-a89e-6b657d45e1a4)

Si bien hemos trabajado con el session, podemos hacerlo de una manera más legible: (**Usando UseBean**)

Se coloca el class = "Employee" para que siempre exista y no tenga un valor de nulo el usuario logueado (Cuando no hay usuario logueado)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/d4f28eee-36d3-40d6-ba72-301d829578e5)

Colocamos en el jsp la nueva lógica (Ahora si el id = 0 entonces no se logró loguear, si es diferente de cero entonces se logueó)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/86287a3e-6f72-4e70-9157-4604efc45da5)

## Duración de una sesión
Le asignamos un tiempo determinado a la sesión

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/9c394f71-d21f-478d-bb66-d55d25e2a0e4)

## Validación si es que un usuario ya está logueado
Cuando estamos logueados en facebook y luego abrimos otra pestaña y entramos nuevamente a facebook, nos redirije a nuestra sesión iniciada en facebook.

Antes de validar el action, validamos el login em LoginServlet:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/44099ad8-5ad1-4c0b-a461-b0eb6bc7a115)

Ocurre un problema con la memoria Caché de la información cuando retrocedo luego de cerrar sesión:



## Ejercicio: Solo los logueados podrán editar y borrar

En la lista de empleados

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/eb100f39-8cf8-4ce2-980f-c7e0759ab0bd)

Para que no se descuadre:

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/ad083e9b-8c6f-4a8e-8b5c-805230dd0a99)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/72969553-6976-4e7f-b668-58bec7016482)

Si cerramos sesión pero antes de ello copiamos el url del editar usuario, luego de cerrar sesión pego esa url, me redirije al editar usuario (SE TIENE QUE VALIDAR LAS ACCIONES SOLO PERMITIDAS CUANDO SE LOGUEE)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/9a89fd3f-64d6-4381-863d-916a7ab1708a)

Dicha validación se hace en el Servlet (En este caso EmployeeServlet)

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/6e6615e0-46f0-402f-b5f6-3aa1299b5f49)

## HASH CONTRASEÑA
En base de datos se guardan las contraseñas únicamente de forma hasheada.

El hash no es cifrado, sino que es una función Matemática en donde entra una determinada 




## Funcionamiento de las "Cookies"

PC (Cliente )------> Servidor (entre ambos hay un identificador para la sesión y ese es el cookie)

Cualquiera de los dos puede borrar la cookie. El primero cuando cierre sesión o el segundo cuando se reinicia (el servidor). 

## Inicio de sesión con link (manejo de html con bootstrap)
Podemos hacerle cambios con inspeccionar para luego copiar y pegarlos en el jsp

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/7fda852f-34d4-432f-bfb2-53429816865d)

Si nos sale errores cuando colocamos palabras que lleven tilde **colocamos el pageEncoding utf-8** (cabecera hardcodeada):

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/72d6ff20-a7ef-4f3e-b2ed-06c615adb84e)













