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

## AWS Amplify - Alojamiento Web Estático
	Para este laboratorio, AWS Amplify permitirá aojar los recursos web estáticos como
	HTML, CSS, JavaScript y archivos de imagen que se cargan en el navegador.
	AWS AMplify permite conectar repositorios con GitHub, para ellos se ha creado una página
	descargada de AWS en el siguiente repositorio: https://github.com/JuanPabloArevalo/AYGOFrontEndAWS
	Conectamos nuestro AWS Amplify con github:
	
![Alt text](img/ConectarConGit1.JPG)

![Alt text](img/ConectarConGit2.JPG)	

![Alt text](img/ConectarConGit3.JPG)	

![Alt text](img/ConectarConGit4.JPG)	

	Cada cambio que se realice en el repositorio,  será desplegado y se actualizará 
	automaticamente
	
![Alt text](img/ConectarConGit5.JPG)	

	Cuando termine el despliegue, se podrá llamar la página por medio de la URL creada
	
![Alt text](img/tituloAntes.JPG)	

	Para validar el despliegue, se cambia el título de la página en github:

![Alt text](img/CambioGit.JPG)	

	Se despliega automaticamente y ya queda disponible el nuevo título.
	
![Alt text](img/Rebuild.JPG)
	
![Alt text](img/NuevoTitulo.JPG)
	
		
## Amazon Cognito - Administración de usuarios
	Amazon Cognito proporciona funciones de administración y autenticación de usuarios para proteger la 
	API de backend.
	
![Alt text](img/cognito1.JPG)	

	Para iniciar se crea un grupo de usuarios
	
![Alt text](img/GrupoUsuario1.JPG)	

	Se crea un cliente de aplicación
	
![Alt text](img/CreacionCLienteApp.JPG)
	
![Alt text](img/ClienteApp2.JPG)	

	Se actualiza en el código para que se conecte con la aplicación
	
![Alt text](img/ConfigJS.JPG)	

	Para realizar la validación se crea un usuario por medio de la página web y el resultado se ve en
	Amazon cognito1
	
![Alt text](img/UsuarioCreado.JPG)	
	
![Alt text](img/AutenticaciónOK.JPG)	

		
## Amazon DynamoDB - Backend sin servidor
	Amazon DynamoDB proporciona una capa de persistencia donde los datos se pueden almacenar mediante la 
	función Lambda de la API.
	
	Creación de una tabla dentro de dynamoDB
	
![Alt text](img/CreacionDynamoDB.JPG)	

![Alt text](img/DynamoDB.JPG)

	Se debe crear un rol IAM, para otorgar permisos a Lambda.
	
![Alt text](img/CreacionRolIAM.JPG)	
	
	Luego se otrogan los permisos

![Alt text](img/PermisosRolAIM.JPG)	

![Alt text](img/PermisosRolAIMCreacion.JPG)	

![Alt text](img/ResumenPolitica.JPG)	

	El siguiente paso será la creación de la función Lambda. Para ello se utiliza un código generado por el 
	laboratorio de AWS
	
![Alt text](img/FuncionLambda1.JPG)

![Alt text](img/FuncionLambda2.JPG)	

	Se valida la implementación
	
![Alt text](img/PruebaFuncionLamdba.JPG)	


## Amazon API Gateway - API RESTFul
	JavaScript ejecutado en el navegador envía y recibe datos de una API de backend pública creada mediante 
	Lambda y API Gateway.
	
	Lo primero será crear el API
	
![Alt text](img/APIGateway.JPG)	

	Se creará un autorizador para controlar los accesos al API, así solo aquellos usuario de amazon cognito
	serán los autorizados a realizar las solicitudes.
	
![Alt text](img/APIGatewayAutorization.JPG)	

![Alt text](img/APIGatewayPrueba.JPG)

	Se debe crear un nuevo recurso y un método.
	
![Alt text](img/APIGatewayRecurso.JPG)	

![Alt text](img/APIGatewayMetodo.JPG)		

	Y se le asigna la autorización
	
![Alt text](img/APIGatewayAutorizacion.JPG)	

	Se implementa el API
	
![Alt text](img/ImplementacionAPI.JPG)	

![Alt text](img/ImplementacionAPI2.JPG)		

	Se cambia la configuración del sitio web:
	
![Alt text](img/ConfigJS2.JPG)		

	Se suben los cambios a github, para que se despliegue automaticamente en AWS Cognito
	
![Alt text](img/cambiosGitJS.JPG)	

	Y con esto ya quedaría toda la implementación lista.
	Se valida con la siguiente imagen:
	
![Alt text](img/PruebaOk!.JPG)	
	
	
	