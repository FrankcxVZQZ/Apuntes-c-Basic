**APUNTES LOGICA**
- Arreglos
- Matrices
- Índices
- Cadenas
- String
- Struct

**Arreglos**

Un arreglo es una colección de elementos del mismo tipo almacenados en posiciones de memoria contiguas.
Cada elemento de un arreglo se puede acceder a través de un índice numérico.

Sintaxis

    tipo_de_dato nombre_del_arreglo[tamaño];

Ejemplo,para declarar un arreglo de 10 enteros, se podría utilizar el siguiente código:

    int numeros[10];

**Matrices**

Una matriz es un arreglo bidimensional, es decir, una colección de elementos del mismo tipo almacenados
en filas y columnas. Cada elemento de una matriz se puede acceder a través de dos índices, uno para la fila
y otro para la columna.

La sintaxis básica para declarar una matriz es la siguiente:

    tipo_de_dato nombre_de_la_matriz[filas][columnas];

Ejemplo con codigo

```c++
    #include <iostream>

    using namespace std;

    int main() {

    // Declaramos una matriz de 3 filas y 4 columnas aqui se puede modifica con define o constant
    int matriz[3][4];

    // Pedimos al usuario que ingrese los valores de la matriz
    for (int fila = 0; fila < 3; fila++) {
        for (int columna = 0; columna < 4; columna++) {
        cout << "Ingrese el valor para la fila " << fila + 1 << " columna " << columna + 1 << ": ";
        cin >> matriz[fila][columna];
        }
    }

    // Imprimimos la matriz
    for (int fila = 0; fila < 3; fila++) {
        for (int columna = 0; columna < 4; columna++) {
        cout << matriz[fila][columna] << " ";
        }
        cout << endl;
    }

    return 0;
    }
```

Este código funciona de la siguiente manera:

Primero, declaramos una matriz de 3 filas y 4 columnas.

Luego, usamos un ciclo for anidado para pedir al usuario que ingrese los valores de la matriz. El ciclo interno itera sobre las columnas y el ciclo externo itera sobre las filas.

Finalmente, usamos otro ciclo for anidado para imprimir la matriz.

salida seria asi

    Ingrese el valor para la fila 1 columna 1: 1

    Ingrese el valor para la fila 1 columna 2: 2
    ...
    Ingrese el valor para la fila 3 columna 4: 12

    1 2 3 4
    5 6 7 8
    9 10 11 12

**Indice**

Un índice en una matriz es un número entero que se utiliza para acceder a un elemento específico de la matriz.
El índice comienza en 0 y se incrementa hasta el tamaño de la matriz - 1.

Ejemplo:

```c++
    #include <iostream>

    using namespace std;

    int main() {

    // Declara la lista
    int list[] = {1, 5, 3, 2, 4};

    // calcula el tamaño de la lista
    int listSize = sizeof(list) / sizeof(list[0]);

    // Sort the list from largest to smallest
    for (int i = 0; i < listSize - 1; i++) {
        for (int j = 0; j < listSize - i - 1; j++) {
            if (list[j] < list[j + 1]) {
                // Swap the list elements
                int temp = list[j];
                list[j] = list[j + 1];
                list[j + 1] = temp;
            }
        }
    }

    // Print the sorted list
    for (int i = 0; i < listSize; i++) {
        cout << list[i] << " ";
    }

    return 0;

}
```

***Nota:***
sizeof es un operador en C++ que se utiliza para obtener el tamaño, en bytes,
de un tipo de dato o de un objeto específico. La sintaxis general es:

    sizeof(tipo_de_dato_o_variable);

Calcula el tamaño del array dividiendo el tamaño total del array (sizeof(list))
por el tamaño de un elemento del array (sizeof(list[0])). Esto proporciona el número
total de elementos en el array y almacena ese valor en la variable listSize.

_Cadenas_

1.  Arreglos de caracteres (char[]):
    En C++, una cadena de caracteres es un arreglo de caracteres terminado por un carácter nulo ('\0').
    Ejemplo:

```c++
         #include <iostream>

        using namespace std;

        int main() {
        // Declaración e inicialización de una cadena de caracteres
        char cadena[] = "Hola, mundo!";

        // Imprimir la cadena de caracteres
        cout << "Cadena: " << cadena << std::endl;

        return 0;
        }
```

Clase String:
La clase string de la biblioteca estándar de C++ proporciona una forma más flexible y fácil de trabajar con cadenas de caracteres.
Ejemplo

```c++
    #include <iostream>
    #include <string>

    using namespace std;

    int main() {
    // Declaración e inicialización de objetos string
    string nombre = "Juan";
    string apellido = "Pérez";

    // Concatenar cadenas
    string nombreCompleto = nombre + " " + apellido;

    // Imprimir el resultado
    cout << "Nombre completo: " << nombreCompleto << endl;

    // Obtener la longitud de la cadena
    cout << "Longitud del nombre completo: " << nombreCompleto.length() << " caracteres" << endl;

    // Acceder a caracteres individuales
    cout << "Primer caracter: " << nombreCompleto[0] << endl;

    return 0;
    }
```

El método length() se utiliza para obtener la longitud de una cadena en C++.
Aquí hay más detalles sobre cómo funciona en el contexto del ejemplo

La función length() es solo una de las varias formas de obtener la longitud de una cadena en C++.
Otras opciones incluyen size(), que hace lo mismo que length(), y std::strlen(), que se utiliza para cadenas de estilo C (terminadas en \0).

Ejemplo

```c++
    #include <iostream>
    #include <cstring>

    using namespace std;

    int main() {

    const char cadena[] = "Hola, mundo!";

    // Obtener la longitud de la cadena
    cout << "Longitud de la cadena: " << strlen(cadena) << " caracteres" << endl;

    return 0;
    }
```

Ejemplo de llenado por medio de un usuario con char

```c++
    #include <iostream>
    #include <cstring>

    using namespace std;

    int main() {
    // Solicitar al usuario que ingrese una palabra
    cout << "Ingrese una palabra: ";

    // Declarar una cadena de caracteres para almacenar la palabra
    char palabra[100];  // Se asume que la palabra no excede los 99 caracteres

    // Leer la palabra desde la entrada estándar
    cin >> palabra;

    // Obtener la longitud de la palabra utilizando strlen
    cout << "Longitud de la palabra: " << strlen(palabra) << " caracteres" << endl;

    return 0;
    
    }
```
Ejemplo con String
    
```c++
    #include <iostream>
    #include <string>

    using namespace std;

    int main() {
    // Solicitar al usuario que ingrese una palabra
    cout << "Ingrese una palabra: ";

    // Declarar un objeto std::string para almacenar la palabra
    string palabra;

    // Leer la palabra desde la entrada estándar
    cin >> palabra;

    // Obtener la longitud de la palabra utilizando length()
    cout << "Longitud de la palabra: " << palabra.length() << " caracteres" << endl;

    return 0;
    }
```

**Struct**

Un struct (estructura) es un tipo de dato que permite agrupar diferentes tipos de datos bajo un solo nombre. Es similar a una clase, pero con la diferencia fundamental de que, por defecto, todos los miembros de un struct son públicos.

Ejemplo básico de cómo funciona un struct en C++:

```c++
    struct Persona {
    string nombre;
    int edad;
    };

    int main() {
    // Declaramos una variable de tipo Persona
    Persona persona;

    // Asignamos valores a los miembros de la estructura
    persona.nombre = "Juan Pérez";
    persona.edad = 30;

    // Imprimimos los valores de los miembros de la estructura
    cout << "El nombre de la persona es: " << persona.nombre << endl;
    cout << "La edad de la persona es: " << persona.edad << endl;

    return 0;
    }
```

Se define un struct llamado Persona que tiene tres miembros públicos: nombre, edad y altura.

Se crea una instancia de Persona llamada persona1.

Se asignan valores a los miembros de persona1.

Se accede y se imprime la información de la persona usando la notación de punto (.) para acceder a los miembros de la estructura.

Ahora si hacemos un poco mas interactivo el programa quedaria asi

```c++
    #include <iostream>
    #include <string>

    using namespace std;

    // Definición de un struct llamado Persona
    struct Persona {
    // Miembros públicos
    string nombre;
    int edad;
    double altura;
    };

    int main() {
    // Creación de una instancia de Persona
    Persona persona1;

    // Solicitar al usuario que ingrese los datos
    cout << "Ingrese el nombre: ";
    cin >> persona1.nombre;

    cout << "Ingrese la edad: ";
    cin >> persona1.edad;

    cout << "Ingrese la altura en metros: ";
    cin >> persona1.altura;

    // Imprimir la información de la persona
    cout << "\nInformación de la persona:\n";
    cout << "Nombre: " << persona1.nombre << endl;
    cout << "Edad: " << persona1.edad << " años" << endl;
    cout << "Altura: " << persona1.altura << " metros" << endl;

    return 0;
    }
```


La ejecución del programa sería algo así:

    Ingrese el nombre: Juan
    Ingrese la edad: 25
    Ingrese la altura en metros: 1.75

    Información de la persona:
    Nombre: Juan
    Edad: 25 años
    Altura: 1.75 metros


**Funciones**

Una función es un bloque de código que se puede llamar para realizar una tarea específica. Las funciones se utilizan para organizar el código en unidades más pequeñas y manejables, y para reutilizar código en diferentes partes de un programa.

Ejemplo

```c++
     #include <iostream>

    using namespace std;

    // Declaración de la función
    int suma(int a, int b);

    int main() {
    // Llamada a la función desde la función principal
    int resultado = suma(3, 4);

    // Imprimir el resultado
    cout << "La suma es: " << resultado << endl;

    return 0;
    }

    // Definición de la función
    int suma(int a, int b) {
    return a + b;
    }
```

En C++, existen diferentes tipos de funciones, según su comportamiento o el tipo de valor que devuelven.

**Funciones sin valor de retorno**

Las funciones sin valor de retorno son aquellas que no devuelven ningún valor. Estas funciones se utilizan a menudo para realizar tareas que no requieren un valor de retorno.

Por ejemplo, la siguiente función imprime un mensaje en la pantalla:

 ```c++
    void imprimirMensaje(const char* mensaje) {
    cout << mensaje << endl;
    }

    int main() {
    imprimirMensaje("Hola, mundo!");
    }
 ```

**Funciones con valor de retorno**

Las funciones con valor de retorno son aquellas que devuelven un valor. El tipo de valor que devuelve la función se especifica en la declaración de la función.

Por ejemplo, la siguiente función devuelve la suma de dos números:

  ```c++
 int sumar(int x, int y) {
    return x + y;
    }

    int main() {
    int x = 10;
    int y = 20;

    int resultado = sumar(x, y);

    cout << "El resultado es: " << resultado << endl;
    }
```

**Funciones con parámetros**

Las funciones con parámetros son aquellas que reciben valores como entrada. Los parámetros se especifican en la declaración de la función, y se pueden utilizar en el cuerpo de la función para realizar cálculos o tareas.

Por ejemplo, la siguiente función devuelve la suma de dos números recibidos como parámetros:

  ```c++
  int sumar(int x, int y) {
    return x + y;
    }

    int main() {
    int x = 10;
    int y = 20;

    int resultado = sumar(x, y);

    cout << "El resultado es: " << resultado << endl;
    }
```

**Funciones recursivas**

Las funciones recursivas son aquellas que se llaman a sí mismas. Las funciones recursivas se utilizan a menudo para resolver problemas que se pueden dividir en subproblemas más pequeños.

Por ejemplo, la siguiente función calcula el factorial de un número:

   ```c++
 int factorial(int n) {
    if (n == 0) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
    }

    int main() {
    int n = 5;

    int factorial = factorial(n);

    cout << "El factorial de " << n << " es: " << factorial << endl;
    }
```

**Funciones miembro**

Las funciones miembro son aquellas que pertenecen a una clase. Las funciones miembro se utilizan para realizar tareas que afectan a un objeto de la clase.

Por ejemplo, la siguiente clase define una función miembro para imprimir el nombre de un objeto:

```c++
  class Persona {
    public:
    Persona(const string& nombre) : nombre_(nombre) {}

    void imprimirNombre() {
        cout << nombre_ << endl;
    }

    private:
    string nombre_;
    };

    int main() {
    Persona persona("Juan Pérez");

    persona.imprimirNombre();
    }
```

**Funciones lambda**

Las funciones lambda son funciones anónimas que se pueden utilizar como parámetros o valores de retorno. Las funciones lambda se utilizan a menudo para simplificar el código.

Por ejemplo, la siguiente función utiliza una función lambda para calcular el factorial de un número:

   ```c++
 int factorial(int n) {
    return [](int n) {
        if (n == 0) {
        return 1;
        } else {
        return n * factorial(n - 1);
        }
    }(n);
    }

    int main() {
    int n = 5;

    int factorial = factorial(n);

    cout << "El factorial de " << n << " es: " << factorial << endl;
    }
```

