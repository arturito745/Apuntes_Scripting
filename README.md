# Apuntes_Scripting
FORCE_Richi
# Manipulacion de bases de datos

# Arreglos o Array

### Declaracion de ARRAY 
```
tipo[] nombreArreglo;

```
Tipo: es el tipo de datos que vas a colocar en ese array, ejemplo int o string, no se puede mezclar de tipo de datos 

## Inicializado 
```
1. int[] numeros = new int[5]; // Arreglo de 5 enteros // este arreglo puede alamacenar 5 datos, lo rellena el usuario 
```
```
2. tipo[] nombreArreglo = { valor1, valor2, valor3, ... };// este arreglo ya esta inicializado con ciertos valores adentro que los colocamos nosotros.
```
## Como se accede a los valores dentro del array ?

1.
```
int[] numeros = { 10, 20, 30, 40, 50 };
Console.WriteLine(numeros[0]); // Imprime 10 (primer elemento) // los arreglo empiezan desde 0 en si es el tamaño real del array -1 porque se cuenta desde 0  
Console.WriteLine(numeros[2]); // Imprime 30 (tercer elemento)
```
## Modificacion del array y sus valores 
```
1. int[] numeros = { 10, 20, 30, 40, 50 };
numeros[1] = 25; // Cambia el segundo elemento de 20 a 25 deprimero se coloca la posicion a cambiar y luego se iguala al valor requerido
Console.WriteLine(numeros[1]); // Imprime 25 esto prueba que si se halla echo bien
```
## Recorrer el array 
```
1. int[] numeros = { 10, 20, 30, 40, 50 };
for (int i = 0; i < numeros.Length; i++)
{
    Console.WriteLine(numeros[i]);
}
```
2.
```
int[] numeros = { 10, 20, 30, 40, 50 };
foreach (int numero in numeros) //recorre el array sin indices de i
{
    Console.WriteLine(numero);
}
```
## Metodos utilez 
1.
```
 int[] numeros = { 10, 20, 30, 40, 50 };
Console.WriteLine(numeros.Length); // Imprime 5 que es el total de caracteres del array 
```
2.
```
int[] numeros = { 50, 20, 40, 10, 30 };
Array.Sort(numeros); // Ordena el arreglo de menor a mayor 
Console.WriteLine(string.Join(", ", numeros)); // Imprime "10, 20, 30, 40, 50"
```
4.
 ```
int[] numeros = { 10, 20, 30, 40, 50 };
Array.Reverse(numeros); // Invierte el arreglo
Console.WriteLine(string.Join(", ", numeros)); // Imprime "50, 40, 30, 20, 10"
```

# Pilas 

Una pila es una estructura de datos que sigue el principio LIFO (Last In, First Out), es decir, el último elemento en entrar es el primero en salir. Imagina una pila de platos: el último plato que pones en la pila es el primero que sacas.

## Declaracion de pila
```
Stack<T> nombrePila = new Stack<T>();
```
En c# se usa las pilas con Stack la T dentro de esos corchetes es el tipo de dato de la pila int o string
```
Stack<int> pilaEnteros = new Stack<int>(); // Pila de enteros
Stack<string> pilaCadenas = new Stack<string>(); // Pila de cadenas
```
## Operaciones importantes con pilas 

### 1. Push: sirve para añadir un elemento nuevo a la pila
```
pilaEnteros.Push(10); // Añade 10 a la pila
pilaEnteros.Push(20); // Añade 20 a la pila
pilaEnteros.Push(30); // Añade 30 a la pila

```
Estado de la pila: [30, 20, 10] (el último elemento añadido es 30).

### 2. Pop: Sirve para eliminar y devolver el elemnto superior de la pila, 
## importante: tenemos que crear un variable para poder devolver el numero, esta variable la vamos a igualar con el metodo.pop
```
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main()
    {
        // Crear una pila de strings (para representar los platos)
        Stack<string> pilaPlatos = new Stack<string>();

        // Añadir platos a la pila
        pilaPlatos.Push("Rojo");   // Plato rojo
        pilaPlatos.Push("Verde");  // Plato verde
        pilaPlatos.Push("Azul");   // Plato azul

        // Estado de la pila: ["Azul", "Verde", "Rojo"]

        // Hacer Pop para eliminar y obtener el plato superior
        string platoEliminado = pilaPlatos.Pop();

        // Mostrar el plato eliminado
        Console.WriteLine("Plato eliminado: " + platoEliminado); // Imprime "Azul"

        // Estado de la pila después del Pop: ["Verde", "Rojo"]
    }
}
```

### 3. peck 

Devuelve el elemento superior de la pila sin eliminarlo y No modifica el tamaño de la pila.
```
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main()
    {
        // 1. Declarar una pila de enteros
        Stack<int> pilaNumeros = new Stack<int>();

        // 2. Añadir elementos a la pila usando Push
        pilaNumeros.Push(10); // Añade 10
        pilaNumeros.Push(20); // Añade 20
        pilaNumeros.Push(30); // Añade 30

        // Estado de la pila: [30, 20, 10] (30 es el elemento superior)

        // 3. Usar Peek para obtener el elemento superior sin eliminarlo
        int elementoSuperior = pilaNumeros.Peek();

        // 4. Mostrar el elemento superior
        Console.WriteLine("Elemento superior: " + elementoSuperior); // Imprime 30

        // 5. Verificar que la pila no ha cambiado
        Console.WriteLine("Cantidad de elementos en la pila: " + pilaNumeros.Count); // Imprime 3
    }
}

```

### 4. ¿Cómo puedo vaciar una pila usando Pop?

Puedes usar un bucle while:
```
while (pila.Count > 0)
{
    int elemento = pila.Pop();
    Console.WriteLine("Elemento eliminado: " + elemento);
}
```
## Colas 

Una cola es la en la que el primer elemnto entrar es el primero en salir. 

### Declaracion de cola 

```
Queue<T> nombreCola = new Queue<T>();

``` 
T es el tipo puede ser int o string 

```
Queue<int> colaEnteros = new Queue<int>(); // Cola de enteros
Queue<string> colaCadenas = new Queue<string>(); // Cola de cadenas

```

### Operaciones basicas con colas 


#### 1. Añadir un elemnto 
```
colaEnteros.Enqueue(10); // Añade 10 a la cola
colaEnteros.Enqueue(20); // Añade 20 a la cola
colaEnteros.Enqueue(30); // Añade 30 a la cola
```

#### 2. Dequeue: Eliminar y Obtener el Elemento del Frente

Elimina y devuelve el elemento del frente de la cola. al decir devolver es que lo guarda y puede imprimir el elemnto 

```
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main()
    {
        // 1. Declarar una cola de enteros
        Queue<int> cola = new Queue<int>();

        // 2. Añadir elementos a la cola usando Enqueue
        cola.Enqueue(10); // Añade 10
        cola.Enqueue(20); // Añade 20
        cola.Enqueue(30); // Añade 30

        // Estado de la cola: [10, 20, 30]

        // 3. Declarar la variable elementoEliminado
        int elementoEliminado;

        // 4. Usar Dequeue para eliminar y obtener el elemento del frente
        elementoEliminado = cola.Dequeue();

        // 5. Mostrar el elemento eliminado
        Console.WriteLine("Elemento eliminado: " + elementoEliminado); // Imprime 10

        // 6. Mostrar el nuevo estado de la cola
        Console.WriteLine("Elementos restantes en la cola:");
        foreach (int elemento in cola)
        {
            Console.WriteLine(elemento); // Imprime 20 y 30
        }
    }
}
```
#### 3. Peek: Obtener el Elemento del Frente sin Eliminarlo
Devuelve el elemento del frente sin eliminarlo.
```
int elementoFrente = colaEnteros.Peek(); // Devuelve 20
Console.WriteLine(elementoFrente); // Imprime 20

```
#### 4. Count: Obtener el Número de Elementos
```
int cantidad = colaEnteros.Count; // Devuelve 2
Console.WriteLine(cantidad); // Imprime 2
```
#### Ejemplo completo 
```
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main()
    {
        // 1. Declarar una cola de enteros
        Queue<int> cola = new Queue<int>();

        // 2. Añadir elementos a la cola usando Enqueue
        cola.Enqueue(10); // Añade 10
        cola.Enqueue(20); // Añade 20
        cola.Enqueue(30); // Añade 30

        // Estado de la cola: [10, 20, 30]

        // 3. Usar Dequeue para eliminar y obtener el elemento del frente
        int elementoEliminado = cola.Dequeue();

        // 4. Mostrar el elemento eliminado
        Console.WriteLine("Elemento eliminado: " + elementoEliminado); // Imprime 10

        // 5. Mostrar el nuevo estado de la cola
        Console.WriteLine("Elementos restantes en la cola:");
        foreach (int elemento in cola)
        {
            Console.WriteLine(elemento); // Imprime 20 y 30
        }
    }
}

```
## Listas 
Las listas tienen un almacenamiento dinamico esto significa que podemos sumar y restar elementos en tiempo de ejecucion, asi mismo podemos eliminar agregar y ordenar elemntos guiandonos por su indice que empieza en 0 y tambien con este podemos buscar.

### Declaracion 












