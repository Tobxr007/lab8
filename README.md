par o impar 

#include <iostream>
using namespace std;

void mostrarParidad(int numero) {
    if (numero % 2 == 0) {
        cout << "Par\n";
    } else {
        cout << "Impar\n";
    }
}

int main() {
    int numero;

    cout << "Ingresa un numero entero: ";
    if (!(cin >> numero)) {
        return 1;
    }

    mostrarParidad(numero);
    return 0;
}

conversor de temp.

#include <iostream>
using namespace std;

float celsiusAFahrenheit(float celsius) {
    return celsius * 9.0f / 5.0f + 32.0f;
}

int main() {
    float celsius;

    cout << "Ingresa la temperatura en Celsius: ";
    if (!(cin >> celsius)) {
        return 1;
    }

    cout << "Temperatura en Fahrenheit: "
         << celsiusAFahrenheit(celsius) << '\n';

    return 0;
}

mayor de 3 num.

#include <iostream>
using namespace std;

int mayor(int a, int b, int c) {
    int resultado = a;

    if (b > resultado) {
        resultado = b;
    }
    if (c > resultado) {
        resultado = c;
    }

    return resultado;
}

int main() {
    int a, b, c;

    cout << "Ingresa tres numeros enteros: ";
    if (!(cin >> a >> b >> c)) {
        return 1;
    }

    cout << "El mayor es: " << mayor(a, b, c) << '\n';
    return 0;
}

calcu con menu

#include <iostream>
using namespace std;

float sumar(float a, float b) {
    return a + b;
}

float restar(float a, float b) {
    return a - b;
}

float multiplicar(float a, float b) {
    return a * b;
}

float dividir(float a, float b) {
    return a / b;
}

int main() {
    int opcion;
    float a, b;

    cout << "1. Sumar\n"
         << "2. Restar\n"
         << "3. Multiplicar\n"
         << "4. Dividir\n"
         << "Elige una opcion: ";

    if (!(cin >> opcion) || opcion < 1 || opcion > 4) {
        cout << "Opcion invalida.\n";
        return 1;
    }

    cout << "Ingresa dos numeros: ";
    if (!(cin >> a >> b)) {
        return 1;
    }

    float resultado;

    switch (opcion) {
        case 1:
            resultado = sumar(a, b);
            break;
        case 2:
            resultado = restar(a, b);
            break;
        case 3:
            resultado = multiplicar(a, b);
            break;
        case 4:
            if (b == 0.0f) {
                cout << "Error: no se puede dividir entre cero.\n";
                return 1;
            }
            resultado = dividir(a, b);
            break;
        default:
            return 1;
    }

    cout << "Resultado: " << resultado << '\n';
    return 0;
}


factorial y tabla de resultados 

#include <iostream>
#include <limits>
using namespace std;

int factorial(int n) {
    int resultado = 1;

    for (int i = 2; i <= n; i++) {
        resultado *= i;
    }

    return resultado;
}

void mostrarFactoriales(int limite) {
    for (int i = 1; i <= limite; i++) {
        cout << i << "! = " << factorial(i) << '\n';
    }
}

int main() {
    int limite;

    cout << "Ingresa el limite: ";
    if (!(cin >> limite) || limite < 1) {
        cout << "Ingresa un entero mayor o igual a 1.\n";
        return 1;
    }

    // Calcula hasta donde se puede llegar sin desbordar un int.
    int maximo = 1;
    int producto = 1;

    while (producto <= numeric_limits<int>::max() / (maximo + 1)) {
        maximo++;
        producto *= maximo;
    }

    if (limite > maximo) {
        cout << "El limite maximo es " << maximo << ".\n";
        return 1;
    }

    mostrarFactoriales(limite);
    return 0;
}
