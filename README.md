import java.util.LinkedList;
import java.util.Queue;

class Cliente {
    private Queue<String> colaClientes;

    public Cliente() {
        this.colaClientes = new LinkedList<>();
    }

    // Método para insertar un elemento en la cola
    public void push(String cliente) {
        colaClientes.offer(cliente);
    }

    // Método para extraer y devolver el primer elemento de la cola
    public String pop() {
        if (isEmpty()) {
            throw new IllegalStateException("La cola está vacía. No se puede realizar pop.");
        }
        return colaClientes.poll();
    }

    // Método para imprimir la cola
    public void imprimirCola() {
        if (isEmpty()) {
            System.out.println("La cola está vacía.");
            return;
        }

        System.out.println("Contenido de la cola:");

        for (String cliente : colaClientes) {
            System.out.println(cliente);
        }
    }

    // Método para verificar si la cola está vacía
    public boolean isEmpty() {
        return colaClientes.isEmpty();
    }
}

public class PruebaCliente {
    public static void main(String[] args) {
        Cliente colaClientes = new Cliente();

        // Prueba de inserción
        colaClientes.push("Cliente1");
        colaClientes.push("Cliente2");
        colaClientes.push("Cliente3");

        // Prueba de impresión
        colaClientes.imprimirCola();

        // Prueba de extracción
        System.out.println("Cliente atendido: " + colaClientes.pop());

        // Prueba de impresión después de la extracción
        colaClientes.imprimirCola();
    }
}
