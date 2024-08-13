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

#### Ejercicio 2.2. Definición de atributos de una clase con tipos primitivos de datos
```
/**
 * Esta clase define objetos de tipo Planeta con un nombre, cantidad de
 * satélites, masa, volumen, diámetro, distancia al sol, tipo de planeta y si es
 * observable o no.
 * @version 1.2/2020
 */
public class Planeta {
    // Atributo que define el nombre de un planeta
    String nombre = null;
    // Atributo que define la cantidad de satélites que tiene un planeta
    int cantidadSatélites = 0;
    // Atributo que define la masa de un planeta
    double masa = 0;
    // Atributo que define el volumen de un planeta
    double volumen = 0;
    // Atributo que define el diámetro de un planeta
    int diámetro = 0;
    // Atributo que define la distancia al sol de un planeta
    int distanciaSol = 0;
    // Atributo que define el tipo de planeta como un valor enumerado
    enum tipoPlaneta { GASEOSO, TERRESTRE, ENANO }
    // Atributo que define el tipo de planeta
    tipoPlaneta tipo;
    // Atributo que define si el planeta es observable o no
    boolean esObservable = false;
    /**
     * Constructor de la clase Planeta
     * @param nombre Parámetro que define el nombre del planeta
     * @param cantidadSatélites Parámetro que define la cantidad de
     * satélites del planeta
     * @param masa Parámetro que define la masa del planeta (en
     * kilogramos)
     * @param volumen Parámetro que define el volumen del planeta
     * (en kilómetros cúbicos)
     * @param diámetro Parámetro que define el diámetro del planeta
     * (en kilómetros)
     * @param distanciaSol Parámetro que define la distancia media del
     * planeta al sol (en kilómetros)
     * @param tipo Parámetro que define el tipo de planeta (puede ser
     * GASEOSO, TERRESTRE o ENANO)
     * @param esObservable Parámetro que define si el planeta es
     * observable o no
     */
    Planeta(String nombre, int cantidadSatélites, double masa, double volumen, int diámetro,
            int distanciaSol, tipoPlaneta tipo, boolean esObservable) {
        this.nombre = nombre;
        this.cantidadSatélites = cantidadSatélites;
        this.masa = masa;
        this.volumen = volumen;
        this.diámetro = diámetro;
        this.distanciaSol = distanciaSol;
        this.tipo = tipo;
        this.esObservable = esObservable;
    }
    /**
     * Método que imprime en pantalla los datos de un planeta
     */
    void imprimir() {
        System.out.println("Nombre del planeta = "+nombre);
        System.out.println("Cantidad de satélites = "+cantidadSatélites);
        System.out.println("Masa del planeta = "+masa);
        System.out.println("Volumen del planeta = "+volumen);
        System.out.println("Diámetro del planeta = "+diámetro);
        System.out.println("Distancia al sol = "+distanciaSol);
        System.out.println("Tipo de planeta = "+tipo);
        System.out.println("Es observable = "+esObservable);
    }
    /**
     * Método que calcula y devuelve la densidad de un planeta
     * @return La densidad calculada del planeta
     */
    double calcularDensidad() {
        return masa / volumen;
    }
    /**
     * Método que determina y devuelve si un planeta es exterior o no
     * @return Valor booleano que indica si el planeta es exterior o no
     */
    boolean esPlanetaExterior() {
        float límite = (float)(149597870 * 3.4);
        /* Un planeta exterior está situado más allá del cinturón de
        asteroides */
        /* El cinturón se encuentra entre 2,1 y 3,4 UA (UA =
        149.597.870 Km) */
        if (distanciaSol > límite) {
            return true;
        } else {
            return false;
        }
    }
    /**
     * Método main que crea dos planetas, imprime sus datos en pantalla,
     * determina su densidad y si son planetas exteriores
     */
    public static void main(String args[]) {
        Planeta p1 = new Planeta("Tierra", 1, 5.9736E24, 1.08321E12, 12742, 150000000, tipoPlaneta.TERRESTRE, true);
        p1.imprimir();
        System.out.println("Densidad del planeta = "+
            p1.calcularDensidad());
        System.out.println("Es planeta exterior = "+
            p1.esPlanetaExterior());
        System.out.println();
        Planeta p2 = new Planeta("Júpiter", 79, 1.899E27, 1.4313E15, 139820, 750000000, tipoPlaneta.GASEOSO, true);
        p2.imprimir();
        System.out.println("Densidad del planeta = "+
            p2.calcularDensidad());
        System.out.println("Es planeta exterior = "+
            p2.esPlanetaExterior());
    }
}
```
