# Taller conclusion de arreglos unidimensionales
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
