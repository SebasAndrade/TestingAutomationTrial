# TestingAutomationTrial
Ejercicio N°1
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



---
---

Ejercicio n°2

Caso de prueba N°1
Nombre: Validación respuesta "http 200".

Descripción: Se hará una consulta al servidor con válores válidos, los que deberán generar una respuesta positiva.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/posts
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request exitoso"
* La respuesta contiene un codigo http 200.


---
Caso de prueba N°2
Nombre: Validación respuesta "http 404".

Descripción: Se hará una consulta al servidor con válores inválidos, los que deberán generar un error "http 404: Not found".

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/post
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request failed: 404 not found"
* La respuesta contiene un codigo "http 404: Not found".


---
Caso de prueba N°3
Nombre: Validación acceso a un objeto.

Descripción: Se hará una consulta al servidor con válores válidos, que deberán permitir el acceso a los parámetros del objeto.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/posts/5
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request exitoso"
* La respuesta contiene un codigo http 200.


---
Caso de prueba N°4
Nombre: Validación acceso a un objeto.

Descripción: Se hará una consulta al servidor con válores inválidos, que deberá devolver un error "http 404 not found" ya que el objeto no será accesible.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/posts/150
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request failed: 404 not found"
* La respuesta contiene un codigo "http 404: Not found".


---
Caso de prueba N°5
Nombre: Validación respuesta "http 200".

Descripción: Se hará una consulta al servidor con válores válidos, los que deberán generar una respuesta positiva.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/albums
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request exitoso"
* La respuesta contiene un codigo http 200.


---
Caso de prueba N°6
Nombre: Validación respuesta "http 404".

Descripción: Se hará una consulta al servidor con válores inválidos, los que deberán generar un error "http 404: Not found".

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/albumes
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request failed"
* La respuesta contiene un codigo "http 404: Not found".


---
Caso de prueba N°7
Nombre: Validación acceso a un objeto.

Descripción: Se hará una consulta al servidor con válores válidos, que deberán permitir el acceso a los parámetros del objeto.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/album/3
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request exitoso"
* La respuesta contiene un codigo http 200.


---
Caso de prueba N°8
Nombre: Validación acceso a un objeto.

Descripción: Se hará una consulta al servidor con válores inválidos, que deberá devolver un error "http 404 not found" ya que el objeto no será accesible.

Pasos:
* Se genera un request GET de la siguiente forma: "GET https://jsonplaceholder.typicode.com/albums/499
* Se ejecuta el request GET, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Request failed: 404 not found"
* La respuesta contiene un codigo "http 404: Not found".


---
Caso de prueba N°9
Nombre: Validación de creación de un objeto

Descripción: Se hará una consulta al servidor con válores válidos, que deberá devolver un código http "201 created".

Pasos:
* Se genera un request POST de la siguiente forma: "POST https://jsonplaceholder.typicode.com/posts
* Se ejecuta el request POST, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Created Succesfully: 201 code"
* La respuesta contiene un codigo "http 201: Created".


---
Caso de prueba N°10
Nombre: Validación de creación de un objeto

Descripción: Se hará una consulta al servidor con válores válidos, que deberá devolver un código http "404 not found created".

Pasos:
* Se genera un request POST de la siguiente forma: "POST https://jsonplaceholder.typicode.com/postss
* Se ejecuta el request POST, enviando el objeto anteriormente generado.
* Se comprueba que se recibe una respuesta por parte del servidor.

Resultado esperado:
* La descripcion de la respuesta contiene el siguiente string: "Cannot create object: 404 not found"
* La respuesta contiene un codigo "http 404: Not found".



---
---
Ejercicio N°3

Para el ejercicio número uno, tomé como parámetros a realizar el objetivo del microservicio. Desde ese objetivo, primeramente definido, fuí desglosando de la consigna los distintos requerimientos y cosas que no podían fallar tanto del servidor como del request que se estaría realizando. Al no tener un ambiente de prueba real, fue imposible realizar un código pues no hay un endpoint al cual pegarle con los request. Por lo tanto dediqué a generar los casos de pruebas precisos y necesarios para cubrir el scope limitado que se dio en el ejercicio. Para el server error si fue o es necesario utilizar un stub (a nivel código back end) o un mock (a nivel herramienta de testeo) del servidor. Esto es debido a que las pruebas sobre errores del servidor son inesperadas y por lo tanto intesteables de manera controlada. Por supuesto, la elección de la tecnología a utilizar dependerá de en que estado se encuentre el proyecto.

Por otro lado, para el ejercicio número 2, decidí utilizar postman por su sencilles para este ejercicio en particular. Al no tener un scope definido ni una user story que me permita definirlo por mi cuenta (como por ejemplo que me indiquen que x key puede recibir un máximo x de carácteres), solo se pueden hacer testeos básicos, tanto manuales como automatizados, los cuales se basarían en las respuestas 200 y 400 de los request ejecutados y los accesos a los distintos objetos. Cabe destacar que los recursos de la api brindada están en forma de "nest" o anidados entre ellos. Por ejemplo: Posts contiene comments, albums contiene a photos, todos contienen users. Por esto mismo fue necesario realizar dos testeos sobre el request en cuestión, uno de respuesta del servidor y otro de acceso exitoso al objeto o recurso solicitado. En los ejemplos utilicé ID por ser un recurso común a la hora de identificar objetos, pero puede filtrarse de otras formas según lo requiera el scope o la story. Realmente utilicé postman porque para el scope limitado que se nos presenta es una herramienta mucho más eficaz. Cypress es más potente en algunos factores, da más posibilidades y mayor robustes, por lo que podía ser un exceso de recursos para el trabajo solicitado. Explico este punto ya que considero un aptitud importante de un tester saber elegir que herramienta o tecnología le será más útil según la situación, para así optimizar tiempo y obtener mejores resultados.

Por último, intenté que las tareas no sean muy repetitivas. Es decir: al haber realizado 6 test cases y notar que los siguientes 6 serían iguales pero cambiando un parámetro o unas letras decidí obviarlos, dando por sobre entendido que es continuar con el proceso previamente realizado.

Para finalizar, dejo el link con el con la colección de postman dónde se pueden correr los casos de pruebas: https://www.getpostman.com/collections/b4bc1e655468aace37cc

Atte, Sebastián Andrade.
