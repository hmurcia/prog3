Vamos a analizar cómo se puede abordar la problemática de calcular el perímetro y el área de una figura poligonal en dos enfoques: uno tradicional (sin uso de programación orientada a objetos) y otro utilizando el paradigma de programación orientada a objetos (POO). Utilizaremos Java para ilustrar estos conceptos.

### Enfoque Tradicional

En un enfoque tradicional, sin utilizar el paradigma de orientación a objetos, podríamos resolver el problema con funciones o procedimientos independientes. Por ejemplo, supongamos que queremos calcular el perímetro y el área de diferentes figuras como un triángulo, un cuadrado y un círculo. Aquí hay una forma de hacerlo en Java:

```java
public class PoligonosTradicional {

    // Método para calcular el perímetro del triángulo
    public static double calcularPerimetroTriangulo(double a, double b, double c) {
        return a + b + c;
    }

    // Método para calcular el área del triángulo
    public static double calcularAreaTriangulo(double base, double altura) {
        return (base * altura) / 2;
    }

    // Método para calcular el perímetro del cuadrado
    public static double calcularPerimetroCuadrado(double lado) {
        return 4 * lado;
    }

    // Método para calcular el área del cuadrado
    public static double calcularAreaCuadrado(double lado) {
        return lado * lado;
    }

    // Método para calcular el perímetro del círculo
    public static double calcularPerimetroCirculo(double radio) {
        return 2 * Math.PI * radio;
    }

    // Método para calcular el área del círculo
    public static double calcularAreaCirculo(double radio) {
        return Math.PI * radio * radio;
    }

    public static void main(String[] args) {
        // Ejemplos de uso
        System.out.println("Perímetro del triángulo: " + calcularPerimetroTriangulo(3, 4, 5));
        System.out.println("Área del triángulo: " + calcularAreaTriangulo(3, 4));
        System.out.println("Perímetro del cuadrado: " + calcularPerimetroCuadrado(5));
        System.out.println("Área del cuadrado: " + calcularAreaCuadrado(5));
        System.out.println("Perímetro del círculo: " + calcularPerimetroCirculo(7));
        System.out.println("Área del círculo: " + calcularAreaCirculo(7));
    }
}
```

**Ventajas del enfoque tradicional:**
- Simplicidad para casos específicos y procedimientos directos.
- No requiere el uso de clases adicionales.

**Desventajas del enfoque tradicional:**
- Código menos modular y difícil de extender.
- No encapsula los datos y comportamientos relacionados, lo que puede llevar a la repetición de código.
- Cambios en la fórmula o en la lógica de cálculo requieren cambios en múltiples lugares.

### Enfoque Orientado a Objetos

En el paradigma de orientación a objetos, se utilizan clases para representar entidades y sus comportamientos. Esto permite una estructura más modular y extensible. Aquí está el mismo problema resuelto utilizando POO en Java:

```java
abstract class Figura {
    abstract double calcularPerimetro();
    abstract double calcularArea();
}

class Triangulo extends Figura {
    private double a, b, c, base, altura;

    public Triangulo(double a, double b, double c, double base, double altura) {
        this.a = a;
        this.b = b;
        this.c = c;
        this.base = base;
        this.altura = altura;
    }

    @Override
    double calcularPerimetro() {
        return a + b + c;
    }

    @Override
    double calcularArea() {
        return (base * altura) / 2;
    }
}

class Cuadrado extends Figura {
    private double lado;

    public Cuadrado(double lado) {
        this.lado = lado;
    }

    @Override
    double calcularPerimetro() {
        return 4 * lado;
    }

    @Override
    double calcularArea() {
        return lado * lado;
    }
}

class Circulo extends Figura {
    private double radio;

    public Circulo(double radio) {
        this.radio = radio;
    }

    @Override
    double calcularPerimetro() {
        return 2 * Math.PI * radio;
    }

    @Override
    double calcularArea() {
        return Math.PI * radio * radio;
    }
}

public class TestFiguras {
    public static void main(String[] args) {
        Figura triangulo = new Triangulo(3, 4, 5, 3, 4);
        Figura cuadrado = new Cuadrado(5);
        Figura circulo = new Circulo(7);

        System.out.println("Perímetro del triángulo: " + triangulo.calcularPerimetro());
        System.out.println("Área del triángulo: " + triangulo.calcularArea());
        System.out.println("Perímetro del cuadrado: " + cuadrado.calcularPerimetro());
        System.out.println("Área del cuadrado: " + cuadrado.calcularArea());
        System.out.println("Perímetro del círculo: " + circulo.calcularPerimetro());
        System.out.println("Área del círculo: " + circulo.calcularArea());
    }
}
```

**Ventajas del enfoque orientado a objetos:**
- **Modularidad:** Cada figura es una clase separada con sus propios datos y métodos.
- **Extensibilidad:** Se pueden añadir nuevas figuras fácilmente sin modificar el código existente.
- **Encapsulamiento:** Los datos y comportamientos relacionados están agrupados en la misma clase.
- **Reusabilidad:** Las clases pueden ser reutilizadas y extendidas según sea necesario.

**Desventajas del enfoque orientado a objetos:**
- **Complejidad adicional:** Puede ser excesivo para problemas simples.
- **Curva de aprendizaje:** Requiere entender conceptos como clases, herencia y polimorfismo.

### Comparación y Conclusión

**Enfoque Tradicional:**
- **Ventajas:** Directo y simple para problemas pequeños y específicos.
- **Desventajas:** Escalable, menos modular, y difícil de mantener y extender.

**Enfoque Orientado a Objetos:**
- **Ventajas:** Más organizado, modular, y extensible; facilita la mantenibilidad y reutilización del código.
- **Desventajas:** Puede ser más complejo y requerir una mayor comprensión del paradigma.

La orientación a objetos proporciona una manera más estructurada y mantenible de manejar la complejidad, especialmente cuando el sistema crece o se vuelve más complejo.
