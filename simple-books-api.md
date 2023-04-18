# Simple Books API #

Esta API te permite interactuar con una base de datos de libros. Puedes ver una lista de libros, ver los detalles de un libro, y añadir, actualizar y eliminar libros.

## Endpoints ##

### Status ###

GET `/status`

Regresa el Status de la API.

### Lista de libros ###

GET `/`

Regresa una lista de los libros.

### Ver los detalles de un libro específico ###

GET `/:bookId`

Regresa información detallada de un libro.

### Submit an order ###

POST `/`

Permite añadir un nuevo libro.

El cuerpo del request necesita estar en formato JSON y debe incluir las siguientes propiedades:

- `title` - String - Required
- `author` - String - Required
- `finished` - bool - Not required (default: false)

#### **Ejemplo POST request** ####

    ```
    POST /
    {
    "title": "The Lord of the Rings",
    "author": "J.R. Tolkien",
    "finished": false
    }
    ```

El cuerpo del response regresará información detallada del libro añadido.

### Actualizar un libro ###

PUT `/:bookId`

Este endpoint permite actualizar un libro existente.

El cuerpo del request necesita estar en formato JSON y debe incluir las siguientes propiedades:

- `title` - String - Required
- `author` - String - Required
- `finished` - bool - Not required (default: false)

#### **Ejemplo PUT request** ####

    ```
    PUT /:bookId
    {
    "title": "The Lord of the Rings",
    "author": "J.R.R. Tolkien",
    "finished": true
    }
    ```

### Eliminar un libro ###

DELETE `/:bookId`

Este endpoint permite eliminar un libro existente.

El cuerpo del request necesita estar vacío.

The request body needs to be empty.

#### **Ejemplo DELETE request** ####

    ```
    DELETE /:bookId
    ```
