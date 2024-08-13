## Ejercicios de programación orientada a objetos con Java y UML
#### Leonardo Bermón Angarita

#### Ejercicio 2.1. Definición de clases
```
/**
 * Esta clase define objetos de tipo Persona con un nombre, apellidos,
 * número de documento de identidad y año de nacimiento.
 * @version 1.2/2020
 */
public class Persona {
    String nombre; // Atributo que identifica el nombre de una persona
    String apellidos; // Atributo que identifica los apellidos de una persona
    /* Atributo que identifica el número de documento de identidad de una persona */
    String númeroDocumentoIdentidad;
    int añoNacimiento;
    /* Atributo que identifica el año de nacimiento de una persona */
    /**
     * Constructor de la clase Persona
     * @param nombre Parámetro que define el nombre de la persona
     * @param apellidos Parámetro que define los apellidos de la persona
     * @param númeroDocumentoIdentidad Parámetro que define el
     * número del documento de identidad de la persona
     * @param añoNacimiento Parámetro que define el año de nacimiento
     * de la persona
     */
    Persona(String nombre, String apellidos, String númeroDocumentoIdentidad, int añoNacimiento) {
        this.nombre = nombre;
        this.apellidos = apellidos;
        this.númeroDocumentoIdentidad = númeroDocumentoIdentidad;
        this.añoNacimiento = añoNacimiento;
    }
    /**
     * Método que imprime en pantalla los datos de una persona
     */
    void imprimir() {
        System.out.println("Nombre = " + nombre);
        System.out.println("Apellidos = " + apellidos);
        System.out.println("Número de documento de identidad = " +
            númeroDocumentoIdentidad);
        System.out.println("Año de nacimiento = " + añoNacimiento);
        System.out.println();
    }
    /**
     * Método main que crea dos personas e imprime sus datos en pantalla
     */
    public static void main(String args[]) {
        Persona p1 = new Persona("Pedro", "Pérez", "1053121010", 1998);
        Persona p2 = new Persona("Luis", "León", "1053223344", 2001);
        p1.imprimir();
        p2.imprimir();
    }
}
```
