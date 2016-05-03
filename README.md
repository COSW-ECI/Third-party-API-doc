
#Servicios externos
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

##API Cámara de comercio

Recurso:
https://damp-dusk-55729.herokuapp.com/rest/peticiones/camaracomercio/NIT

Donde NIT es de la modalidad xxxxxxxxx-x, siendo x cualquier número entre 0 y 9.

