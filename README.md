
#Servicios externos

Dudas o solicitudes por favor contactar a Andrés Barrero: [andres.barrero@mail.escuelaing.edu.co](mailto:andres.barrero@mail.escuelaing.edu.co)

## API Pasarela de pagos


####Consulta transacciones realizadas:

GET http://paymentsgateway.herokuapp.com/rest/payments/transactions

####Realización de pagos:
POST con un objeto jSON:

```javascript
{"numeroTarjeta":"XXXXXXXXXXXXXXX",
"codigoSeguridad":"XXX",
"tipo":"AMEX",
"nombreCliente":"aaaaaaaa",
"cuentaDestino":"2789817823-bancolombia",
"descripcion":"Descripcion del pago",
"montoTransaccion":10000}
```

Al recurso:

http://paymentsgateway.herokuapp.com/rest/payments
 
__NOTA__:
En caso de que la respuesta sea exitosa (código 202), se retornará el código de la transacción.
En caso de error (404), se incluirá un mensaje que describe la causa del mismo.
  
=============================
Datos disponibles para pruebas:


| TIPO        | Número           | Cupo  | Pin |
| ------------- |:-------------:| -----:|-----:|
| AMEX      | 378282246310005 | $2000000  | Cualquiera | 
| MASTER      | 5105105105105100      |   $2342343 | Cualquiera     |
| VISA | 4111111111111111      |    $0 |  Cualquiera    |



##API INVIMA

Recurso: 

https://damp-dusk-55729.herokuapp.com/rest/peticiones/invima/NIT

Donde NIT es de la modalidad xxxxxxxxx-x, siendo x cualquier número entre 0 y 9.

Ejemplos:
 * Caso exitoso con NIT 123456789-8.

##API Cámara de comercio

Recurso:
https://damp-dusk-55729.herokuapp.com/rest/peticiones/camaracomercio/NIT

Donde NIT es de la modalidad xxxxxxxxx-x, siendo x cualquier número entre 0 y 9.

Los casos en los cuales de NIT no es válido, es cuando los dígitos colocados en las posiciones 1, 2, 3, 8, 10, no son números pares; claro trabajando una escala de 0<=x<n, siendo “n” la longitud del NIT, exceptuando la posición 9, ya que esta posición está reservada para el símbolo "-".

Ejemplos:
  * Caso exitoso con NIT 222222222-2.
  * Caso exitoso con NIT 124635798-8.
  * Caso fallido con NIT 135222227-9.
  * Caso fallido con NIT 444226667-9.


##API Productos (Supermercados/Almacenes deportivos)

Recursos:

* https://damp-dusk-55729.herokuapp.com/rest/peticiones/proveedoresysupermecados/232151289-0
* https://damp-dusk-55729.herokuapp.com/rest/peticiones/proveedoresysupermecados/132551289-0
* https://damp-dusk-55729.herokuapp.com/rest/peticiones/proveedoresysupermecados/332351289-0

Los anteriores recursos usan dentro de su representación, además de los productos, los clientes afiliados:

```javascript
{"nombre":"Sociedad Colectiva 22","productos":[{"nombre":"Pantalon 494","precio":1990182,"cantidad":97736,"codigo":5104500,"ganancia":12,"peso":26},{"nombre":"Sandalia 695","precio":1579908,"cantidad":84188,"codigo":464262,"ganancia":7,"peso":328},{"nombre":"Pantalon 624","precio":1550056,"cantidad":24032,"codigo":2143806,"ganancia":16,"peso":486},{"nombre":"Pantalon 66","precio":1652725,"cantidad":26096,"codigo":9425665,"ganancia":11,"peso":1},{"nombre":"Camisa 552","precio":1928106,"cantidad":24581,"codigo":4184684,"ganancia":27,"peso":398}],"clientes":[{"nombre":"Boris","tipo":"Frecuente","gastoAcumulado":22687170,"codigo":7764365},{"nombre":"Estefania","tipo":"Normal","gastoAcumulado":243465,"codigo":9603287},{"nombre":"Hugo","tipo":"Frecuente","gastoAcumulado":65178544,"codigo":8364984},{"nombre":"Catalina","tipo":"Normal","gastoAcumulado":600668,"codigo":8590727},{"nombre":"Gisell","tipo":"Normal","gastoAcumulado":277956,"codigo":3909413},{"nombre":"Fabiola","tipo":"Normal","gastoAcumulado":525989,"codigo":2603743},{"nombre":"German","tipo":"Frecuente","gastoAcumulado":5189928,"codigo":6985848},{"nombre":"Carlos","tipo":"Normal","gastoAcumulado":307325,"codigo":115708},{"nombre":"Hugo","tipo":"Frecuente","gastoAcumulado":70238750,"codigo":9354289},{"nombre":"German","tipo":"Normal","gastoAcumulado":866863,"codigo":5761622},{"nombre":"Helena","tipo":"Frecuente","gastoAcumulado":58872236,"codigo":9464049},{"nombre":"Boris","tipo":"Normal","gastoAcumulado":443883,"codigo":1075779},{"nombre":"Fernando","tipo":"Normal","gastoAcumulado":368929,"codigo":77897},{"nombre":"Gisell","tipo":"Frecuente","gastoAcumulado":27669913,"codigo":8144607},{"nombre":"Boris","tipo":"Frecuente","gastoAcumulado":8644287,"codigo":1590025},{"nombre":"Fernando","tipo":"Frecuente","gastoAcumulado":38648719,"codigo":2409659},{"nombre":"German","tipo":"Normal","gastoAcumulado":732093,"codigo":3743027},{"nombre":"Diana","tipo":"Frecuente","gastoAcumulado":64137247,"codigo":2328875}],"ubicacion":"Manizales","nit":"222456789-0"}

```javascript

