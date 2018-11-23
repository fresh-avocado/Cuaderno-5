# Cuaderno-5
Desarrollaremos el cuaderno 5 con código.

#include <iostream>
using namespace std;

unsigned int factorial(unsigned int n) {
    if(n > 1)
        return n * factorial(n - 1);
    else
        return 1;
}

int main() {
    
    unsigned int n;
    cout << "Ingrese un n: ";
    cin >> n;
    
    // CREAR GRAFO CON "N" PARTICULAR
    
    unsigned int fact_of_n = factorial(n);
    
    int graph[fact_of_n][n];
    
    int myints[n];
    for (int i = 0; i < n; i++){
        myints[i] = i+1;
    }
    
    sort (myints,myints+n);
    
    int i = 0;
    
    do {
        for (int j = 0; j < n; j++) {
            graph[i][j] = myints[j];
        }
        i++;
    } while (next_permutation(myints,myints+n));
    
    for (int i = 0; i < fact_of_n; i++) {
        for (int j = 0; j < n; j++) {
            cout << graph[i][j] << " ";
        }
        cout << endl;
    }
    
    // ARISTAS TOTALES
    
    int aristas_totales = 0;
    int grado_mayor = 0;
    
    for (int i = 0; i < fact_of_n; i++) {
        for (int j = i+1; j < fact_of_n;) {
            for (int k = 0; k < n; k++) {
                if (graph[i][k] == graph[j][k]) {
                    aristas_totales++;
                    j++;
                    break;
                }
                else {
                    j++;
                    continue;
                }
            }
        }
    }
    
    aristas_totales--;
    
    cout << "Aristas totales : " << aristas_totales << endl;
    
    // GRADO MAYOR DEL GRAFO
    
    for (int j = 1; j < fact_of_n; j++) {
        for (int k = 0; k < n; k++) {
            if (graph[0][k] == graph[j][k]) {
                grado_mayor++;
                break;
            }
            else
                continue;
        }
    }
    
    cout << "Mayor grado: " << grado_mayor << endl;
    
    return 0;
    
}

