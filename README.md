#include <stdio.h>

int main() {
    int piso_actual = 1; // El ascensor comienza en el primer piso
    int piso_destino;
    char opcion;
    
    while(1) { // El programa se ejecuta en un loop infinito hasta que se interrumpe con la tecla 'q'
        printf("El ascensor está en el piso %d.\n", piso_actual);
        printf("Ingrese el piso al que desea ir (1-10) o presione 'q' para salir: ");
        scanf(" %c", &opcion);
        
        if(opcion == 'q') { // Si se presiona la tecla 'q', se termina el programa
            printf("Saliendo del programa.\n");
            break;
        }
        
        piso_destino = opcion - '0'; // Convertimos la opción ingresada en un entero
        
        if(piso_destino < 1 || piso_destino > 10) { // Si el piso ingresado no está entre 1 y 10, se pide otra opción
            printf("Opción inválida. Ingrese un número entre 1 y 10 o presione 'q' para salir.\n");
            continue;
        }
        
        if(piso_destino == piso_actual) { // Si el piso destino es igual al piso actual, no se hace nada
            printf("El ascensor ya se encuentra en el piso %d.\n", piso_actual);
        }
        else if(piso_destino > piso_actual) { // Si el piso destino es mayor al piso actual, se sube
            printf("Subiendo...\n");
            for(int i = piso_actual; i < piso_destino; i++) { // Se utiliza un ciclo for para simular la subida
                printf("Piso %d.\n", i+1);
            }
            printf("Llegamos al piso %d.\n", piso_destino);
            piso_actual = piso_destino;
        }
        else { // Si el piso destino es menor al piso actual, se baja
            printf("Bajando...\n");
            do { // Se utiliza un ciclo do-while para simular la bajada
                printf("Piso %d.\n", piso_actual-1);
                piso_actual--;
            } while(piso_actual > piso_destino);
            printf("Llegamos al piso %d.\n", piso_destino);
        }
    }
    
    return 0;
}

