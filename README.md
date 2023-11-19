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




