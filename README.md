# TestingAutomationTrial

Caso de prueba 1

Nombre: Validación de fecha en header de request

Descripción: Se ingresará una cadena no válida al campo "date", el cual no debe permitir el ingreso de un formato distinto a DD-MM-AAAA

Pasos:
* Se genera un request para pais-ciudad validos y contendra la siguiente fecha: 1996-12-25.
    {
      date:1996-12-25,
      Country: "Argentina",
      City: "BuenosAires",
    }

* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request invalido - Formato de fecha incorrecto"
* La respuesta contiene un codigo de error 400 "Bad request".

---
Caso de prueba 2

Nombre: Validación respuesta "http 200".

Descripción: Se hará una consulta al servidor con válores válidos, los que deberán generar una respuesta positiva.

Pasos:
* Se genera un request con par de valores validos 
      date:06-12-2001,
      Country: "Chile",
      City:    "Arica",
    }

* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request exitoso: *objeto*"
* La respuesta contiene un codigo http 200.


---
Caso de prueba 3

Nombre: Validación respuesta "http 404: client error"

Descripción: Se hará una consulta al servidor, el objetivo de las pruebas a realizar es verificar la respuesta "http 404: Not found" cuando el contenido o recurso. no esté disponible.

Pasos:
* Se genera un request con parámetros pais-ciudad inválidos.
    {
      date:06-12-2013,
      Country: "Brasil",
      City:    "Curitiba",
    }

* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "El contenido solicitado no está disponible"
* La respuesta contiene un codigo de error 404 "not found".


---
Caso de prueba 4

Nombre: Validación respuesta "http 500: Server error"

Descripción: Se hará una consulta al servidor, el objetivo de las pruebas a realizar es verificar la respuesta "http 500: Server error" cuando el servidor no esté disponible.

Pasos:
* Se genera un request.
    {
      date:25-05-2015,
      Country: "Brasil",
      City:    "Curitiba",
    }

* Se ejecuta el request GET, agregando el metodo stub o mockeando el estado del servidor, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "El servidor al que está intentando acceder no está disponible"
* La respuesta contiene un codigo de error 500 "not found".


---
Caso de prueba 5

Nombre: Validación respuesta "http 404: Not found" Sensitive Case

Descripción: Se hará una consulta al servidor, el objetivo de las pruebas a realizar es verificar la respuesta "http 404: Not found" cuando la solicitud no cumpla con el parámetro "sensitive case".

Pasos:
* Se genera un request con parámetros pais-ciudad válidos, estos mismos estarán escritos alterando el orden se las mayúsculas y minúsculas.
    {
      date:06-12-2013,
      Country: "arGentina",
      City:    "sanjuan",
    }

* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "El contenido solicitado no está disponible"
* La respuesta contiene un codigo de error 404 "not found".
