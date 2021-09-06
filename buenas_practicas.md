# Documento de Buenas Prácticas para la Programación


## ¿Qué son las buenas prácticas en programación?

Cuando hablamos de buenas prácticas nos referimos a un conjunto de técnicas, metodologías y principios que debemos implementar en nuestro software para que se vuelva sencillo, rápido, seguro de desarrollar y fácil de mantener y desplegar.

Un buen código no es aquel que *ya funciona*. Debe cumplir una serie de requisitos para considerarse un software de calidad:

* Funcionar en cualquier dispositivo preparado para ello, de forma sencilla y **automatizada**
* Tener un estilo **legible** (recuerda que el software habitualmente se escribe una vez pero se lee muchas veces)
* Estar **probado**. Debe tener tests que verifiquen su correcto funcionamiento (un software sin testear no se puede considerar terminado)
* Ser sencillo de modificar. Ser **refactorizado** con frecuencia.


Es por eso que las buenas prácticas son fundamentales para avanzar mejorando tu metodología de programación, independientemente del lenguaje en el que estés trabajando.

## ¿Qué beneficios aportan las buenas prácticas a un programador?
Con la implementación de buenas prácticas obtendremos como resultado un **código limpio**, **reutilizable**, **escalable** y más **adaptable al cambio**, el cual nos ayudará a disminuir el tiempo de dedicación en las tareas, a prevenir y sortear errores comunes durante las diferentes etapas de realización que puede tener nuestro proyecto. 

Las buenas prácticas también facilitan la tarea a la hora de trabajar en forma **colaborativa** con otro desarrollador o con **nuevas incorporaciones** al equipo, ya que permite que éstos puedan entender fácilmente nuestro código e incluso desarrollar nuevos avances sobre el proyecto siguiendo una metodología específica para solucionar un problema.

Aplicar mejores prácticas para programar código limpio y eficiente nos ayudará a **reducir o eliminar errores** de compatibilidad entre las diferentes etapas del diseño, por lo que evitaremos retrasos o incluso el fracaso total de un proyecto. 

Es decir que con esta metodología de trabajo estaremos eliminando de raíz la gran mayoría de problemas de desarrollo de software que nuestros proyectos puedan presentar.

> **«Código limpio, reutilizable, y escalable»**


## Principios del Código Limpio

Los principios del Código Limpio [Clean Code; Robert C. Martin; Prentice Hall, 2009] son aquellos que:
>  Generan un código elegante y eficiente. La lógica debe ser sencilla para dificultar la ocultación de errores, las dependencias deben ser mínimas para facilitar el mantenimiento, la gestión de errores debe ser completa de acuerdo con una estrategia articulada, y el rendimiento debe estar cerca del óptimo para no tentar a la gente a ensuciar el código con optimizaciones imprudentes. El código limpio hace una sola cosa y la hace bien. (Bjarne Stroustrup, inventor de C++)

Algunos de los medios para llegar a un Código Limpio son:

* **Nombres significativos**
    * Que revelen la intención de la variable/función/clase...
    * Que se puedan pronunciar y buscar (`pqr` es peor que `pending_queue_requests`). 
    * Sin abreviaturas (hoy en día tenemos pantallas lo bastante grandes!).
    * Sensibles al contexto (ej: la variable `motor` de la clase `Coche` no necesita llamarse `motorCoche`, ¡ya sabemos que pertenece al coche!).

* **Funciones pequeñas**
    * Deben hacer sólo una cosa y hacerla bien.
    * En pocas líneas, que cuenten una historia de forma transparente (llamando a más funciones si es necesario).
    * Con un nombre significativo.
    * Número controlado de argumentos (el número ideal de argumentos para una función es 0).
    * Usar excepciones antes que devolver códigos de error

* **Comentarios**
    * No comentes código malo, ¡re-escríbelo!
    * Intenta que el código sea lo más autoexplicativo posible.  
    Es mejor esto?  
    
    ```java
    // Check to see if the employee is eligible for full benefits
     if ((employee.flags & HOURLY_FLAG) &&
         (employee.age > 65))
    ```  
    O esto?
    
    ```java
    if (employee.isEligibleForFullBenefits())
    ```
    * Si abusas de comentarios es más probable que los tengas desactualizados.
    * Cuidado con los comentarios que son más largos que el código que comentan.
    * No comentes las llaves de cierre, ¡indenta bien! (y pregúntate si el bloque es demasiado largo)

* **Tests**
    * Piensa primero en el test y luego en el código (TDD)
    * Escribe primero el test que falle y luego el código que supere el test.
    * Los tests también deben ser legibles y limpios.
    * Un test unitario prueba una única cosa.

* **Clases**
    * Deben tener una única responsabilidad (Principio de Responsabilidad Única)
    * Las clases deben ser pequeñas!
    * Minimizar el acoplamiento (Principio de Inversión de Dependencia) para que las clases dependan de abstracciones y no de detalles concretos.

* **Refinamientos sucesivos**
    * Refactorizar y limpiar contínuamente.
    * Solventar los *malos olores* [Refactoring: Improving the Design of Existing Code; Martin Fowler et al.; Addison-Wesley, 1999]:
        * Comentarios obsoletos o redundantes
        * Funciones que nunca se llaman
        * Demasiados argumentos
        * Clases base que dependen de sus derivadas
        * Demasiada separación vertical
        * Responsabilidad equivocada
        * Invadir la intimidad de otra clase
        * Y muchos más! (lectura recomendada del libro "Refactoring" de Martin Fowler)

## Estilo de comentarios

Los comentarios son necesarios e importantes, pero no deben sustituir a un código legible.  
Seguir un estándar ayuda a utilizar generadores de documentación (javadoc, doxygen sphinx...).  
Se deberán seguir estos estándares de documentación. Todos ellos se basan en la misma estructura (cambia la sintaxis según el lenguaje:

```javascript
var my_function = $(function(){
  /**
   * La descripción de my_function. Usar la sintaxis del documento de diseño
   *
   * @param {String} param1 - Descripcion de param1.
   * @param {Number} param2 - Descripcion de param2.
   * 
   * @returns {Number} Descripcion del valor devuelto.
   */
```

```java
  /**
   * La descripción de my_function. Usar la sintaxis del documento de diseño
   *
   * @param param1 Descripcion de param1.
   * @param param2 Descripcion de param2.
   * 
   * @returns Descripcion del valor devuelto.
   */
   public int my_function(String param1, int param2) {
```

```c++
    /**
     * La descripción de my_function. Usar la sintaxis del documento de diseño
     * 
     * @param param1 Descripcion de param1.
     * @param param2 Descripcion de param2.
     * 
     * @return Descripcion del valor devuelto.
     */
     int my_function(string param1, int param2) {
```

```python
    def my_function(param1, param2):
    """
    La descripción de my_function. Usar la sintaxis del documento de diseño
    
    Args:
        param1 (str): Descripcion de param1.
        param2 (int): Descripcion de param2.
        
    Returns:
        int: Descripcion del valor devuelto.
    """
```

## Estrategia de Control de Versiones
TODO

### Gitflow
TODO


## Gestión de sprints
TODO