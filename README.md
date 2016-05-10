
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

