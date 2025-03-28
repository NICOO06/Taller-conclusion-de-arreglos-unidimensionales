# Taller conclusión de arreglos unidimensionales
### Nicolas A. Vargas Angarita - Sergio Prieto Vargas
## Codigo python
``` python
vertices = []
caras = []

num_vertices = int(input("¿Cuántos vértices hay? "))

for i in range(num_vertices):
    x = float(input(f"Vértice {i+1} - X: "))
    y = float(input(f"Vértice {i+1} - Y: "))
    z = float(input(f"Vértice {i+1} - Z: "))
    vertices.append((x, y, z))

num_caras = int(input("¿Cuántas caras hay? "))

for i in range(num_caras):
    cara = list(map(int, input(f"Índices de la cara {i+1} (separados por espacio): ").split()))
    caras.append(cara)

print("\nVértices:")
for i, v in enumerate(vertices, 1):
    print(f"V{i}: {v}")

print("\nCaras:")
for i, c in enumerate(caras, 1):
    print(f"F{i}: {c}")
```
# Codigo C++
``` C++
#include <iostream>
using namespace std;

int main() {
    float vertices[100][3];
    int caras[100][10], total_vertices, total_caras, cantidad_vertices;

    cout << "Ingrese la cantidad de vértices: ";
    cin >> total_vertices;

    for (int i = 0; i < total_vertices; i++) {
        cout << "Vértice " << i+1 << ":\n";
        cout << "  Coordenada X: "; cin >> vertices[i][0];
        cout << "  Coordenada Y: "; cin >> vertices[i][1];
        cout << "  Coordenada Z: "; cin >> vertices[i][2];
    }

    cout << "Ingrese la cantidad de caras: ";
    cin >> total_caras;

    for (int i = 0; i < total_caras; i++) {
        cout << "Ingrese la cantidad de vértices para la cara " << i+1 << ": ";
        cin >> cantidad_vertices;
        cout << "Ingrese los índices de los vértices de la cara " << i+1 << " (separados por espacio): ";
        for (int j = 0; j < cantidad_vertices; j++) {
            cin >> caras[i][j];
        }
        caras[i][cantidad_vertices] = -1; // Marcador de fin
    }

    cout << "\nLista de Vértices:\n";
    for (int i = 0; i < total_vertices; i++) {
        cout << "V" << i+1 << ": (" << vertices[i][0] << ", " << vertices[i][1] << ", " << vertices[i][2] << ")\n";
    }

    cout << "\nLista de Caras:\n";
    for (int i = 0; i < total_caras; i++) {
        cout << "F" << i+1 << ": ";
        for (int j = 0; caras[i][j] != -1; j++) {
            cout << caras[i][j] << " ";
        }
        cout << "\n";
    }
    return 0;
}
```
# Generador de Vértices y Caras

Este repositorio contiene implementaciones en **Python** y **C++** para ingresar y almacenar vértices y caras que representan un objeto en 3D. Es una herramienta básica para generar y visualizar estructuras geométricas a partir de datos ingresados por el usuario.

## Características
- Permite ingresar vértices con coordenadas (X, Y, Z).
- Define caras mediante índices de los vértices.
- Imprime los datos en un formato legible.
- Implementaciones disponibles en Python y C++.

## Ejemplo de Uso

### Entrada:
```bash
¿Cuántos vértices hay? 3
Vértice 1 - X: 1.0
Vértice 1 - Y: 2.0
Vértice 1 - Z: 3.0
Vértice 2 - X: 4.0
Vértice 2 - Y: 5.0
Vértice 2 - Z: 6.0
Vértice 3 - X: 7.0
Vértice 3 - Y: 8.0
Vértice 3 - Z: 9.0
¿Cuántas caras hay? 1
Índices de la cara 1 (separados por espacio): 0 1 2
```

### Salida:
```bash
Vértices:
V1: (1.0, 2.0, 3.0)
V2: (4.0, 5.0, 6.0)
V3: (7.0, 8.0, 9.0)

Caras:
F1: [0, 1, 2]
```

## Requisitos

- **Python** o un compilador de **C++**.

## Instalación y Ejecución

### Python:
```bash
# Clonar el repositorio
git clone https://github.com/usuario/repo.git
cd repo

# Ejecutar el script en Python
python3 generador_vertices.py
```

### C++:
```bash
# Clonar el repositorio
git clone https://github.com/usuario/repo.git
cd repo

# Compilar y ejecutar en C++
g++ generador_vertices.cpp -o generador
./generador
```

## Referencias

- [Documentación oficial de Python](https://docs.python.org/3/)
- [Referencia de C++](https://en.cppreference.com/)
- [GitHub - Guía básica para principiantes](https://docs.github.com/en/get-started)
- [Visualización de objetos 3D con OpenGL](https://www.youtube.com/watch?v=KsTrG83YZMg)
- [Modelado poligonal - Wikipedia](https://es.wikipedia.org/wiki/Modelado_poligonal)
