# Practica: Uso de Genericos en Java

### **Objetivo** 

Familiarizarse con el concepto y uso de genericos en Java para crear clases y metodos que puedan manejar diferentes tipos de datos de manera flexible y segura.

### **Descripcion**

En esta practica, exploraremos como utilizar genericos en Java para crear una clase de contenedor generico y un metodo generico que operan en dicho contenedor. Usaremos el concepto de genericos para permitir que nuestra clase y metodo puedan trabajar con diferentes tipos de datos de manera eficiente y sin perder seguridad en tiempo de compilacion.

### Paso 1

1. Declaracion de la Clase Generica

```JAVA
public class Contenedor<T> {
    
}
```

La clase Contenedor se declara como una clase generica al incluir T junto al nombre de la clase. La letra T es un parametro de tipo (o tipo generico) que representa un tipo de dato desconocido. Esto significa que cuando se utiliza la clase Contenedor, se especificara el tipo de dato que se va a almacenar en el contenedor.

2. Declaracion del Campo de Datos

```JAVA
private T contenido;
```

La clase Contenedor tiene un campo de datos llamado contenido de tipo T. La idea aqui es que este campo puede contener un valor de cualquier tipo que se especifique cuando se instancia la clase.

3. Constructor de la Clase

```JAVA
public Contenedor(T contenido) {
    this.contenido = contenido;
}
```
El constructor de la clase Contenedor acepta un argumento de tipo T llamado contenido. Cuando se crea una instancia de Contenedor, el valor que se pase como argumento se almacena en el campo contenido.

4. Metodos get y set:

```JAVA
public T getContenido() {
    return contenido;
}

public void setContenido(T contenido) {
    this.contenido = contenido;
}
```

La clase Contenedor proporciona dos metodos: getContenido() y setContenido(T contenido). El metodo getContenido() devuelve el valor almacenado en el campo contenido, mientras que setContenido(T contenido) permite actualizar ese valor.

### Paso 2

1. Declaracion de la Clase Utilidades

```JAVA
public class Utilidades {

}
```

La clase Utilidades simplemente contiene un metodo generico llamado imprimirContenido.

2. Declaracion del Metodo Generico:

```JAVA
public static <T> void imprimirContenido(Contenedor<T> contenedor) {

}
```

El metodo imprimirContenido es un metodo estatico y generico. La declaracion T antes del tipo de retorno void indica que el metodo utiliza un parametro de tipo T, que se especificara cuando se llame al metodo. El parametro contenedor es de tipo Contenedor T, lo que significa que puede contener cualquier tipo T.

3. Extraccion y Impresion del Contenido:

```JAVA
public static <T> void imprimirContenido(Contenedor<T> contenedor) {
    T contenido = contenedor.getContenido();
    System.out.println("Contenido: " + contenido);
}
```

Dentro del metodo, se utiliza el metodo getContenido() del objeto contenedor para obtener el contenido almacenado en el contenedor. Luego, este contenido se imprime en la consola.

### Paso 3

1. Creacion de los Contenedores en funcion main

```JAVA
Contenedor<Integer> contenedorEntero = new Contenedor<>(42);
Contenedor<String> contenedorCadena = new Contenedor<>("Hola, mundo");
```

Aqui se crean dos objetos de tipo Contenedor utilizando la clase generica Contenedor. Uno contendra un valor entero (42) y el otro contendra una cadena de caracteres ("Hola, mundo"). Los tipos de los contenedores se especifican entre los signos de mayor y menor (< >), lo que indica el tipo de contenido que almacenaran.

2. Uso de las Utilidades

```JAVA
Utilidades.imprimirContenido(contenedorEntero);
Utilidades.imprimirContenido(contenedorCadena);
```

Se llama al metodo estatico imprimirContenido de la clase Utilidades para imprimir el contenido de los contenedores. Se pasa cada uno de los contenedores como argumento. Dado que el metodo imprimirContenido es generico, puede manejar contenedores de diferentes tipos sin problemas.

### Resultado Esperado

Al ejecutar el programa, deberiamos ver en la salida:

```JAVA
Contenido: 42
Contenido: Hola, mundo
```

### Conclusiones

En esta practica, hemos aprendido a como utilizar genericos en Java para crear clases y metodos que pueden trabajar con diferentes tipos de datos sin perder seguridad en tiempo de compilacion. Los genericos nos permiten escribir codigo mas reutilizable y flexible al evitar la necesidad de duplicar codigo para diferentes tipos de datos.




