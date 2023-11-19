Apunte 2do parcial

-Arreglos
-Matrices
-indices
-Cadenas
-String
-Struct


*Arreglos*

Un arreglo es una colección de elementos del mismo tipo almacenados en posiciones de memoria contiguas. 
Cada elemento de un arreglo se puede acceder a través de un índice numérico.

Sintaxis

tipo_de_dato nombre_del_arreglo[tamaño];

Ejemplo,para declarar un arreglo de 10 enteros, se podría utilizar el siguiente código:

    int numeros[10];
    

*Matrices*

Una matriz es un arreglo bidimensional, es decir, una colección de elementos del mismo tipo almacenados 
en filas y columnas. Cada elemento de una matriz se puede acceder a través de dos índices, uno para la fila 
y otro para la columna.

La sintaxis básica para declarar una matriz es la siguiente:

    tipo_de_dato nombre_de_la_matriz[filas][columnas];

Ejemplo con codigo 


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

 *Indice*
 Un índice en una matriz es un número entero que se utiliza para acceder a un elemento específico de la matriz. 
 El índice comienza en 0 y se incrementa hasta el tamaño de la matriz - 1.
 
 Ejemplo:



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


Nota:
sizeof es un operador en C++ que se utiliza para obtener el tamaño, en bytes, 
de un tipo de dato o de un objeto específico. La sintaxis general es:

    sizeof(tipo_de_dato_o_variable);

Calcula el tamaño del array dividiendo el tamaño total del array (sizeof(list)) 
por el tamaño de un elemento del array (sizeof(list[0])). Esto proporciona el número 
total de elementos en el array y almacena ese valor en la variable listSize.

*Cadenas*

1. Arreglos de caracteres (char[]):
En C++, una cadena de caracteres es un arreglo de caracteres terminado por un carácter nulo ('\0'). 
Ejemplo:

        #include <iostream>
        
        using namespace std;

        int main() {
        // Declaración e inicialización de una cadena de caracteres
        char cadena[] = "Hola, mundo!";

        // Imprimir la cadena de caracteres
        cout << "Cadena: " << cadena << std::endl;

        return 0;
    }

2. Clase String:
La clase string de la biblioteca estándar de C++ proporciona una forma más flexible y fácil de trabajar con cadenas de caracteres.
Ejemplo

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

 El método length() se utiliza para obtener la longitud de una cadena en C++. 
 Aquí hay más detalles sobre cómo funciona en el contexto del ejemplo

 La función length() es solo una de las varias formas de obtener la longitud de una cadena en C++. 
 Otras opciones incluyen size(), que hace lo mismo que length(), y std::strlen(), que se utiliza para cadenas de estilo C (terminadas en \0).

Ejemplo 


    #include <iostream>
    #include <cstring>

    using namespace std;

    int main() {

    const char cadena[] = "Hola, mundo!";
    
    // Obtener la longitud de la cadena
    cout << "Longitud de la cadena: " << strlen(cadena) << " caracteres" << endl;

    return 0;
    }

Ejemplo de llenado por medio de  un usuario con char

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

Ejemplo con String

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

*Struct*

Un struct (estructura) es un tipo de dato que permite agrupar diferentes tipos de datos bajo un solo nombre. Es similar a una clase, pero con la diferencia fundamental de que, por defecto, todos los miembros de un struct son públicos.

Ejemplo básico de cómo funciona un struct en C++:

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

    // Acceso y asignación de valores a los miembros
    persona1.nombre = "Juan";
    persona1.edad = 25;
    persona1.altura = 1.75;

    // Imprimir información de la persona
    cout << "Nombre: " << persona1.nombre << endl;
    cout << "Edad: " << persona1.edad << " años" << endl;
    cout << "Altura: " << persona1.altura << " metros" << endl;

    return 0;
    }

Se define un struct llamado Persona que tiene tres miembros públicos: nombre, edad y altura.

Se crea una instancia de Persona llamada persona1.

Se asignan valores a los miembros de persona1.

Se accede y se imprime la información de la persona usando la notación de punto (.) para acceder a los miembros de la estructura.

Ahora si hacemos un poco mas interactivo el programa quedaria asi 

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

La ejecución del programa sería algo así:

    Ingrese el nombre: Juan
    Ingrese la edad: 25
    Ingrese la altura en metros: 1.75

    Información de la persona:
    Nombre: Juan
    Edad: 25 años
    Altura: 1.75 metros

*Funciones*

Una función es un bloque de código que se puede llamar para realizar una tarea específica. Las funciones se utilizan para organizar el código en unidades más pequeñas y manejables, y para reutilizar código en diferentes partes de un programa.
 
Ejemplo

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
