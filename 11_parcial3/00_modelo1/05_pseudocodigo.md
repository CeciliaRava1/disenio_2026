Realizar el redisenio necesario para modelar una solucion que resuelva en forma flexible el calculo del recargo 
por mora del prestamo, teniendo en cuenta su definicion de mora asociada

Aprendizajes
1. Si estoy trabajando con una entidad seleccionada, no tengo que pasarle en los argumentos a si misma porque una entidad conoce a sus propios atributos
2. No es necesario plantear nuevamente el flujo de busqueda de datos en los patrones, puede asumirse que el gestor ya los tiene almacenados de antes
3. Las flechas new y retorno son punteadas
4. Todo lo que conoce el gestor es con flechas punteadas
5. Las relaciones estas de herencia con la interfaz tienen flecha punteada

Pseudocodigo
1. Metodo de enganche: "calcularMontoAAbonar(montoBase: float, prestamo: Prestamo): float". Metodo invocado por "PantallaRegistrarPagoCuota" hacia "GestorRegistrarPagoCuota", que sirve para calcular el monto que debe abonar el cliente. Pasa los parametros montoBase y prestamo.
2. Interfaz Estrategia: "IEstrategiaCalculoMora" Clase de fabricacion pura que contiene el metodo polimorfico "calcularMontoAAbonar(montoBase: float, prestamo: Prestamo): float". El "GestorRegistrarPagoCuota" llama a la estrategia adecuada segun la seleccion del usuario
3. Estrategia concreta: "EstrategiaCalculoPorcentual" Implementa el metodo polimorfico de la interfaz estrategia para realizar el calculo
4. Metodo polimorfico: "calcularMontoAAbonar(montoBase: float, prestamo: Prestamo): float"
1. Recibe como parametros "montoBase" y "Prestamo"
2. Obtiene desde "DefinicionMora" el "porcentajeRecargo" y desde "PrestamoSel" los "diasAtraso"
3. Realiza el calculo del recargo y lo suma al montoBase para obtener el monto total a abonar
4. Retorna a la pantalla un valor flotante del monto a abonar