# TPGestionPeliculas

Este proyecto sirve para guardar películas en una base de datos y realizar consultas sobre ellas a través de una API REST. Está desarrollado en Java y utiliza MySQL como base de datos.

# Requisitos

Java (JDK 17 o superior)

IntelliJ IDEA 

MySQL (servidor local o remoto)

Postman 

Maven 

# Instrucciones de instalación y ejecución

Abrir el proyecto en IntelliJ IDEA.

Asegurarse de tener una base de datos MySQL corriendo y crear una base llamada TPGestionPelicula.

Configurar las credenciales de base de datos en el archivo application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/TPGestionPelicula
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña

Ejecutar la aplicación desde IntelliJ .

La API estará disponible en http://localhost:8080.

# Endpoints disponibles

Crear una nueva película
POST http://localhost:8080/peliculas

- Body (JSON):

{
"titulo": "Matrix",
"director": "Wachowski",
"anio": 1999,
"genero": "Ciencia Ficción"
}

- Respuesta esperada:

{
"id": 1,
"titulo": "Matrix",
"director": "Wachowski",
"anio": 1999,
"genero": "Ciencia Ficción"
}

- Obtener todas las películas
GET http://localhost:8080/peliculas

- Respuesta esperada:

[
{
"id": 1,
"titulo": "Matrix",
"director": "Wachowski",
"anio": 1999,
"genero": "Ciencia Ficción"
},
{
"id": 2,
"titulo": "Inception",
"director": "Christopher Nolan",
"anio": 2010,
"genero": "Ciencia Ficción"
}
]

Obtener una película por su ID
GET http://localhost:8080/peliculas/1

Respuesta esperada:

{
"id": 1,
"titulo": "Matrix",
"director": "Wachowski",
"anio": 1999,
"genero": "Ciencia Ficción"
}

Obtener películas por año
GET http://localhost:8080/peliculas/anio/1999

Respuesta esperada:

[
{
"id": 1,
"titulo": "Matrix",
"director": "Wachowski",
"anio": 1999,
"genero": "Ciencia Ficción"
}
]
