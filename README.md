# Taller conclusion de arreglos unidimensionales
# Archivo: codigo_python.py
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
