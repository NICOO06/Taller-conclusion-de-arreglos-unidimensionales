# Taller conclusion de arreglos unidimensionales
# Carpeta del repositorio
repositorio/
│-- codigo_python.py  # Código en Python para manejar vértices y caras
│-- codigo_cpp.cpp    # Código en C++ para manejar vértices y caras
│-- README.md         # Instrucciones detalladas sobre el código y su ejecución

# Archivo: codigo_python.py

vertices = []
caras = []

num_vertices = int(input("¿Cuántos vértices hay? "))
for i in range(num_vertices):
    x = input(f"Vértice {i+1} - X: ")
    y = input(f"Vértice {i+1} - Y: ")
    z = input(f"Vértice {i+1} - Z: ")
    vertices.append((x, y, z))

num_caras = int(input("¿Cuántas caras hay? "))
for i in range(num_caras):
    cara = input(f"Índices de la cara {i+1} (separados por espacio): ")
    caras.append(cara)

print("\nVértices:")
for i in range(num_vertices):
    print(f"V{i+1}: {vertices[i]}")

print("\nCaras:")
for i in range(num_caras):
    print(f"F{i+1}: {caras[i]}")

# Archivo: codigo_cpp.cpp

#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<string> vertices;
    vector<string> caras;
    int num_vertices, num_caras;

    cout << "¿Cuántos vértices hay? ";
    cin >> num_vertices;

    for (int i = 0; i < num_vertices; i++) {
        string x, y, z;
        cout << "Vértice " << i+1 << " - X: ";
        cin >> x;
        cout << "Vértice " << i+1 << " - Y: ";
        cin >> y;
        cout << "Vértice " << i+1 << " - Z: ";
        cin >> z;
        vertices.push_back(x + " " + y + " " + z);
    }

    cout << "¿Cuántas caras hay? ";
    cin >> num_caras;
    cin.ignore();

    for (int i = 0; i < num_caras; i++) {
        string cara;
        cout << "Índices de la cara " << i+1 << " (separados por espacio): ";
        getline(cin, cara);
        caras.push_back(cara);
    }

    cout << "\nVértices:\n";
    for (int i = 0; i < num_vertices; i++) {
        cout << "V" << i+1 << ": " << vertices[i] << endl;
    }

    cout << "\nCaras:\n";
    for (int i = 0; i < num_caras; i++) {
        cout << "F" << i+1 << ": " << caras[i] << endl;
    }
    return 0;
}

# Archivo: README.md

# Proyecto de Vértices y Caras

Este repositorio contiene dos programas en **Python** y **C++** que permiten ingresar y visualizar una estructura 3D basada en vértices y caras.

## Instrucciones de uso

### Python
1. Ejecuta el archivo con:
   ```
   python codigo_python.py
   ```
2. Ingresa la cantidad de vértices.
3. Ingresa las coordenadas **X, Y, Z** de cada vértice.
4. Ingresa la cantidad de caras.
5. Ingresa los índices de los vértices que forman cada cara.
6. Se imprimirá la estructura 3D.

### C++
1. Compila el código con:
   ```
   g++ codigo_cpp.cpp -o programa
   ```
2. Ejecuta el programa:
   ```
   ./programa
   ```
3. Sigue los mismos pasos que en Python.
