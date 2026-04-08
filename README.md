🧪 Práctica: Pruebas Unitarias con JUnit 5 en VS Code
📌 Objetivo

Configurar un entorno de desarrollo en Visual Studio Code para proyectos Java utilizando Maven, y aprender a crear y ejecutar pruebas unitarias con JUnit 5.

🛠️ Tecnologías utilizadas
Java
Maven
JUnit 5
Visual Studio Code

📁 Estructura del proyecto

test-vscode/

├── pom.xml

├── src/

│   ├── main/

│   │   └── java/

│   │       └── entornos/

│   │           └── CalculadoraRiesgo.java

│   └── test/

│       └── java/

│           └── entornos/

│               └── CalculadoraRiesgoTest.java


⚙️ Configuración del proyecto
Abrir VS Code
Pulsar F1 o Ctrl + Shift + P
Ejecutar: Java: Create Java Project
Seleccionar:
Maven
maven-archetype-quickstart
Introducir:
GroupId: entornos
ArtifactId: test-vscode
Finalizar la creación del proyecto


📦 Configuración de Maven (pom.xml)

Asegúrate de incluir la dependencia de JUnit 5:

<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.10.0</version>
    <scope>test</scope>
</dependency>
💻 Código principal
CalculadoraRiesgo.java
package entornos;

public class CalculadoraRiesgo {
    public String evaluarEdad(int edad) {
        if (edad < 0 || edad > 120) return "Error";
        if (edad < 18) return "Joven";
        if (edad <= 65) return "Adulto";
        return "Senior";
    }
}
🧪 Tests unitarios
CalculadoraRiesgoTest.java
package entornos;

import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

class CalculadoraRiesgoTest {
    CalculadoraRiesgo calc = new CalculadoraRiesgo();

    @Test
    void testEdadNegativa() {
        assertEquals("Error", calc.evaluarEdad(-5));
    }

    @Test
    void testAdulto() {
        assertEquals("Adulto", calc.evaluarEdad(25));
    }

    @Test
    void testSenior() {
        assertEquals("Senior", calc.evaluarEdad(70));
    }

    @Test
    void testLimite18() {
        assertEquals("Adulto", calc.evaluarEdad(18));
    }
}


▶️ Ejecución de tests en VS Code
🔬 Testing Explorer (Matraz)
Icono en la barra lateral izquierda
Permite ejecutar todos los tests

<img width="1757" height="710" alt="image" src="https://github.com/user-attachments/assets/ff47d6f9-ee8b-41f8-9a56-dd392ce5b4f5" />

▶️ CodeLens
Aparece a la izquierda de cada @Test
Opciones:
Run: ejecutar test
Debug: depurar test

<img width="1808" height="708" alt="image" src="https://github.com/user-attachments/assets/58f0e7e2-a280-4300-9c6c-17a1d072ab4c" />

🐞 Depuración
Añadir breakpoint (punto rojo)
Ejecutar en modo Debug
Permite ver la ejecución paso a paso
<img width="1857" height="661" alt="image" src="https://github.com/user-attachments/assets/81e159e3-029d-4b07-9999-e81d28c42789" />

