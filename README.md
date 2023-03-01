# PilasyColas
Tarea de Generador de Números para Pilas y Colas

/**
 *
 * @author caste
 */

package pilasycolas;

 import java.util.*;

public class PilasyColas {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int opcion;
        Stack<Integer> pila = new Stack<>();
        Queue<Integer> cola = new LinkedList<>();
        
        // Generar un millón de números aleatorios y almacenarlos en un ArrayList
        ArrayList<Integer> numeros = new ArrayList<>();
        for (int i = 0; i < 1000000; i++) {
            numeros.add((int)(Math.random() * 20000001) - 10000000);
        }
        
        do {
            // Mostrar el menú de opciones
            System.out.println("\n--- Pilas y Colas UMG ---");
            System.out.println("1. Insertar números en una pila");
            System.out.println("2. Extraer números de la pila");
            System.out.println("3. Insertar números en una cola");
            System.out.println("4. Extraer números de la cola");
            System.out.println("5. Salir");
            System.out.print("Seleccione una opción: ");
            opcion = input.nextInt();
            
            switch (opcion) {
                case 1:
                    // Insertar números en la pila
                    System.out.println("Insertando números en la pila...");
                    for (int num : numeros) {
                        pila.push(num);
                    }
                    System.out.println("Se han insertado " + numeros.size() + " números en la pila.");
                    break;
                case 2:
                    // Extraer números de la pila
                    System.out.println("Extrayendo números de la pila...");
                    int count = 0;
                    while (!pila.empty()) {
                        int num = pila.pop();
                        count++;
                    }
                    System.out.println("Se han extraído " + count + " números de la pila.");
                    break;
                case 3:
                    // Insertar números en la cola
                    System.out.println("Insertando números en la cola...");
                    for (int num : numeros) {
                        cola.add(num);
                    }
                    System.out.println("Se han insertado " + numeros.size() + " números en la cola.");
                    break;
                case 4:
                    // Extraer números de la cola
                    System.out.println("Extrayendo números de la cola...");
                    count = 0;
                    while (!cola.isEmpty()) {
                        int num = cola.remove();
                        count++;
                    }
                    System.out.println("Se han extraído " + count + " números de la cola.");
                    break;
                case 5:
                    // Salir del programa
                    System.out.println("Saliendo del programa...");
                    break;
                default:
                    // Opción inválida
                    System.out.println("Opción inválida. Por favor, seleccione otra opción.");
                    break;
            }
        } while (opcion != 5);
    }

}

// COMENTARIO: En lo personal creo que el metodo mas eficiente en este caso son las Colas por el hecho de ser FIFO,
// aunque las pilas tambien lo son, ambos metodos son de gran utilidad y funcionalidad mas en el caso de las listas 
// enlasadas y los arrays al momento de implementarlas.
    
    
    
    
    
