# CRUD API con Spring Boot y MySQL

Esta es una aplicación de ejemplo que proporciona una API RESTful para gestionar un sistema CRUD básico de usuarios, construida con **Spring Boot** y **Maven**, con conexión a una base de datos **MySQL**.

## Características

La API permite realizar las siguientes operaciones CRUD:

- **Crear** un usuario.
- **Obtener** la lista de todos los usuarios.
- **Obtener** un usuario por su ID.
- **Actualizar** un usuario existente.
- **Eliminar** un usuario por su ID.

## Requisitos

Antes de ejecutar la aplicación, asegúrate de tener los siguientes programas instalados:

- [Java 11 o 17](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Maven](https://maven.apache.org/)
- [MySQL](https://www.mysql.com/)

## Configuración de la Base de Datos

1. Crea una base de datos en MySQL:

   ```sql
   CREATE DATABASE demo;

## Configuración del Proyecto

2. En el archivo src/main/resources/application.properties, configura los detalles de tu conexión a la base de datos:
    
    ```java
   spring.datasource.url=jdbc:mysql://localhost:3306/crud_database
   spring.datasource.username=tu_usuario
   spring.datasource.password=tu_contraseña
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

3. Estructura del Proyecto
    ```cmd
   src/
   ├── main/
   │   ├── java/com/example/crudspringmysql/
   │   │   ├── model/User.java                # Entidad de usuario
   │   │   ├── repository/UserRepository.java # Repositorio de usuario
   │   │   ├── service/UserService.java       # Lógica de negocio para usuarios
   │   │   └── controller/UserController.java # Controlador REST
   │   └── resources/application.properties   # Configuración de la base de datos

## Ejemplos de Uso

### Obtener usuarios

```cmd
GET /api/users
```

### Crear un usuario

```json
POST /api/users
Content-Type: application/json

{
    "name": "Carlos Ruiz",
    "email": "carlos.ruiz@example.com"
}
```

### Actualizar un usuario

```json
POST /api/users
Content-Type: application/json

{
    "id":1,    
    "name": "Marcos Orihuela",
    "email": "marcos@example.com"
}
```

### Eliminar un usuario

```cmd
DELETE /api/users/3
```

## Autor
[vHc05](https://github.com/vHc05)