' Resolver la problematica de consulta de central de deudores de los clientes de Creditln, asegurando que sera posible interpretar la informacion sin importar su formato.



Aprendizajes:
1. Respetar el nombre del gestor
2. Mirar el diagrama de clases ya armado para poner los nombres de las entidades en el diagrama de secuencia
3. No usar nombres genericos para las entidades, sino el del servicio externo en cuestion
4. En todo el DS los metodossiempre tienen la misma firma
5. Si algo me retorna un JSON, no es una matriz sino un String
6. Los servicios externos solo pueden usar el metodo que tienen declarado ellos, no otros del analisis o que me invente yo
7. Los retornos de resultados del adaptador vuelven a quien los pidio, que es la interfaz
8. "implementar" significa escribir el código dentro de la clase, mientras que "invocar" es enviar la flecha del mensaje)
9. Las interfaces son clases abstractas y no pueden elegir nada, al adaptador lo elige el gestor

Pseudocodigo

1. Invocacion externa: "InterfazConsultaDeudores" invoca al metodo "obtenerCodigoPago()" dirigido hacia la interfaz del adaptador.
2. Interfaz adaptador: "IAdaptadorCentralDeudores". Clase de fabricacion pura que define la firma del metodo polimorfico "obtenerCodigoPago(dni: String, fecha: DateTime): String" que deben implementar todos los adaptadores concretos
3. Adaptador concreto: Para este flujo, usamos el servicio de SENASA, cuyo adaptador es "AdaptadorSENASA". El "GestorRegistrarPagoCuota" es el encargado de seleccionar al adaptador pertinente segun el caso.
4. Metodo polimorfico: Metodo definido en la interfaz adaptador "IAdaptadorCentralDeudores" y que es implementado por el adaptador concreto "AdaptadorSENASA"
5. Invocacion nativa: "AdaptadorSENASA" consulta el servicio, realiza un self "adaptarCodigoPago() y le retorna a la interfaz el codigo de pago brindado por "ServicioSENASA". El endpoint incompatible de la api externa es "ServicioSENASA.consultarDeuda(dni, fechaHora)".