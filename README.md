#include stdio.h

int main() {
    int piso_actual = 1; 
    int piso_destino;
    char opcion;
    
    while(1) { 
        printf("El ascensor está en el piso %d.\n", piso_actual);
        printf("Ingrese el piso al que desea ir (1-10) o presione 'q' para salir: ");
        scanf(" %c", &opcion);
        
        if(opcion == 'q') { 
            printf("Saliendo del programa.\n");
            break;
        }
        
        piso_destino = opcion - '0'; 
        
        if(piso_destino < 1 || piso_destino > 10) { 
            printf("Opción inválida. Ingrese un número entre 1 y 10 o presione 'q' para salir.\n");
            continue;
        }
        
        if(piso_destino == piso_actual) { 
            printf("El ascensor ya se encuentra en el piso %d.\n", piso_actual);
        }
        else if(piso_destino > piso_actual) { 
            printf("Subiendo...\n");
            for(int i = piso_actual; i < piso_destino; i++) { 
                printf("Piso %d.\n", i+1);
            }
            printf("Llegamos al piso %d.\n", piso_destino);
            piso_actual = piso_destino;
        }
        else { 
            printf("Bajando...\n");
            do { 
                printf("Piso %d.\n", piso_actual-1);
                piso_actual--;
            } while(piso_actual > piso_destino);
            printf("Llegamos al piso %d.\n", piso_destino);
        }
    }
    
    return 0;
}
