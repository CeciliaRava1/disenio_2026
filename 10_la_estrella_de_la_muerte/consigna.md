Rediseño necesario para modelar una solución que "resuelva en forma flexible el cálculo de ejecución de las órdenes de Reubicación de acuerdo con el método seleccionado por el actor". - STRATEGY

A. Vista de diseño de la estructura utilizando un diagrama de clases que incluya la signatura completa de los métodos utilizados y la especificación completa de los atributos, que muestre el rediseño resultante de la aplicación del patrón que resuelve el problema de diseño.
B. Vista dinámica utilizando un diagrama de secuencia, que modele el comportamiento resultante al rediseño aplicando el patrón.
C. La especificación del comportamiento de los métodos utilizados en la dinámica con una descripción textual o pseudocódigo.



APRENDIZAJE
1. En (DS) estamos representando una ejecución real e individual. Como las interfaces son abstractas y no se pueden instanciar con new(), en el DS ponés la clase concreta de la opción que eligió el usuario (por ejemplo: :EstrategiaEjecucionSatisfactoria).

2. En (DC), mostrás la estructura general completa: la interfaz IEstrategiaCalculo y las 3 clases concretas que la implementan mediante la relación de realización (línea punteada con triángulo).

3. Algunos ejemplos de argumentos y retornos para tomar de referencia.
esDeBaseMilitar(baseMilitar: BaseMilitar): Boolean
estaEnPeriodo(fechaDesde: DateTime, fechaHasta: DateTime): Boolean
calcularEjecucionesOR(basesSeleccionadas: List<BaseMilitar>, fechaDesde: DateTime, fechaHasta: DateTime): Float

4. La estrategia concreta es la que va a buscar todas las cosas que necesita, para encapsular en ella esto y no tener que modificar al gestor si hubiera alguna modificacion en cuando a los datos que necesita para realizar sus calculos