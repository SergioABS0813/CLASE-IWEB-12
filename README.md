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


## Inicio de sesión con link (manejo de html con bootstrap)
Podemos hacerle cambios con inspeccionar para luego copiar y pegarlos en el jsp

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/7fda852f-34d4-432f-bfb2-53429816865d)

Si nos sale errores cuando colocamos palabras que lleven tilde **colocamos el pageEncoding utf-8** (cabecera hardcodeada):

![image](https://github.com/SergioABS0813/CLASE-IWEB-12/assets/134556600/72d6ff20-a7ef-4f3e-b2ed-06c615adb84e)













