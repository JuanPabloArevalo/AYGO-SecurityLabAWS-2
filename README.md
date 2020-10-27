# AYGO Laboratorio Seguridad - AWS

## Objetivos
	1. Desarrollas taller propuesto. Se ha seleccionado Aplicación Web Sin Servidor.
	2. La aplicación web sin servidor, deberá:
		a) Alojar una página erb (HTML, CSS, JAVASCRIPT, etc) en AWS Amplify
		b) Deberá tener el componente de autentiación. Implementado con Amazon Cognito.
		c) Deberá realizar peticiones con HTTP. Para ello deberá utilizar Amazon API
		   para recibir las peticiones. Este deberá llamar una función lambda, la cuál
		   deberá almacenar información en Amazon DynamoDB.
		   
## Solución implementada
	La arquitectura que tendrá la solución será la siguiente:
	
![Alt text](img/Arquitectura.JPG)	

## AWS Amplify
	Para este laboratorio, AWS Amplify permitirá aojar los recursos web estáticos como
	HTML, CSS, JavaScript y archivos de imagen que se cargan en el navegador.
	AWS AMplify permite conectar repositorios con GitHub, para ellos se ha creado una página
	descargada de AWS en el siguiente repositorio: https://github.com/JuanPabloArevalo/AYGOFrontEndAWS
	Conectamos nuestro AWS Amplify con github:
	
![Alt text](img/ConectarConGit1.JPG)

![Alt text](img/ConectarConGit2.JPG)	

![Alt text](img/ConectarConGit3.JPG)	

![Alt text](img/ConectarConGit4.JPG)	

	Cada cambio que se realice en el repositorio, automaticamente será desplegado y se actualizará automaticamente
	
![Alt text](img/ConectarConGit5.JPG)	

	Cuando termine el despliegue, se podrá llamar la por medio de la URL creada
	
![Alt text](img/tituloAntes.JPG)	

	Para validar el despliegue, se cambia el título de la página en github:

![Alt text](img/CambioGit.JPG)	

	Se despliega automaticamente y ya queda disponible el nuevo título.
	
![Alt text](img/tituloAntes.JPG)
	
![Alt text](img/Rebuild.JPG)		


## Amazon Cognito
	Amazon Cognito proporciona funciones de administración y autenticación de usuarios para proteger la API de backend.
	