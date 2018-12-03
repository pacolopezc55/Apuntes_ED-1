# ÍNDICE
![CODE](https://azardata.net/wp-content/uploads/2018/05/code-512.png)
* [INTRODUCCION](#introduccion)
   * [CONCEPTOS](#conceptos)
* [HERRAMIENTAS BÁSICAS](#herramientas-básicas)
   * [LO BÁSICO](#lo-básico)
   * [BIBLIOTECAS (O LIBRERÍAS)](#bibliotecas-o-librerías)
      * [Biblioteca estándar del lenguaje C](#biblioteca-estándar-del-lenguaje-c)
      * [Biblioteca estándar del lenguaje Java](#biblioteca-estándar-del-lenguaje-java)
   * [ENTORNO NECESARIO EN JAVA](#entorno-necesario-en-java)
   * [CONSTRUIR (BUILD)](#construir-build)
* [ENTORNOS INTEGRADOS DE DESARROLLO (IDE)](#entornos-integrados-de-desarrollo-ide)
   * [EJEMPLOS](#ejemplos)
* [BUILD(CODE)](#buildcode)
   * [JAR](#jar)
   * [ANT](#ant)
   * [MAVEN](#maven)
   * [GRADLE](#gradle)

## INTRODUCCION
### CONCEPTOS
* Codigo fuente
* Codigo intermedio u objeto
* Codigo binario
* Bibliotecas (librerías)
* Compilar
* Enlazar (Link)
* Interpretar

## HERRAMIENTAS BÁSICAS
### LO BÁSICO
* Editor de texto: permite escribir código fuente
* Compilador: genera código objeto a partir del código fuente
* Enlazador: agrupa varios archivos objeto en uno binario
* Interprete: lee código fuente y genera código binario para su ejecución

### BIBLIOTECAS (O LIBRERÍAS)
_Conjunto de archivos objeto que extienden la funcionalidad del lenguaje_
* Biblioteca estándar del lenguaje
* Bibliotecas adicionales

#### Biblioteca estándar del lenguaje C
* Entrada y salida por terminal
* Manejo de archivos
* Funciones matemáticas
#### Biblioteca estándar del lenguaje Java
* Entrada y salida por terminal
* Manejo de archivos
* Funciones matemáticas
* Interfaz gráfica
* Red
* Bases de datos
* Gráficos (sólo 2D)
   
_Cada biblioteca está compuesta por varios archivos objeto_
* Tipos:
   * bibliotecas dinámicas (.DLL o .so) (.jar en Java)
   * bibliotecas estáticas (.LIB o .a)
* Partes de una biblioteca:
   * Especificación (ofrece una API)  _(API = Interfaz de Programación de Aplicaciones)_
   * Implementación
  
### ENTORNO NECESARIO EN JAVA
* JRE: necesario para ejecutar programas
   * JVM (inteprete java)
   * Biblioteca estándar
* JDK: necesario para desarrollar programas
   * Herramientas: javac, jar, javadoc, ...

### CONSTRUIR (BUILD) 
_Construir (Build) = Compilar + Enlazar_
* Opciones:
   * Equipo local
   * Servidor de construcción
* Equipo local - Herramientas de construcción
   * make, ninja (C, C++)
   * ant, maven, gradle (Java)
   * grunt, gulp (Javascript)
   * rake (ruby)
* Buildfiles
   * make: Makefile
   * ninja: build.ninja
   * ant: build.xml
   * maven: pom.xml
   * gradle: build.gradle
   * grunt: Gruntfile.js
   * gulp: gulpfile.js
   * rake: Rakefile
* Gneradores de buildfile - Herramienta y archivo asociado
   * CMake: CMakeLists.txt
   * Meson: meson.build
* Servidores de construcción - Integración continua (CI)
   * Jenkins
   * Bamboo
   * TravisCI
   * CircleCI
   * TeamCity
## ENTORNOS INTEGRADOS DE DESARROLLO (IDE)
### EJEMPLOS
* Destinados principalmente a C++:
   * DevC++
   * Microsoft Visual Studio
   * QtCreator
* Destinados principalmente a Java:
   * Netbeans
   * Eclipse
   * IntelliJ IDEA
   * Oracle JDeveloper

## BUILD(CODE)
### JAR
1. Creamos una carpeta:
`# mkdir proyect_name`

2. Crea con cualquier editor el script_name.java y compila: 
`# javac  proyect_name/script_name.java`

3. Creamos el paquete jar:
`# jar  cvf  package_name.jar  proyect_name/*.class`

4. Lo instalamos en la biblioteca del sistema: 
`# mv  package_name.jar  /usr/lib/jvm/default-java/jre/lib/ext/aritm.jar`

5. Creamos y compilamos el archivo Main.java: 
`# javac -cp package_name:. Main.java`
   > **_Nota:_** _package_name:._ refieriendose a la ubicación de los archivos class, en este caso en ese mismo directorio
   
   > Si preferimos usar el código del sistema simplemente compila he importa la librería en tu script:
     
   1. `# javac Main.java`     
     
6. Ejecutamos Main: 
`# java  Main`
 
   > _Si prefieres crear un **programa autocontenido**:_
   1. Crea el paquete jar con todas las clases anteriores:
   `# jar cvfe  main  Main  Main.class  package_name/*.class`
   
   2. Ejecutalo 
   `# java -jar main`
   
#### script_name.java
```java
class script_name {
   public static void main(String[] args) {
      System.out.println("Im the imported class");
   }
}
```

#### Main.java
```java
//Uncomment the following line if you want to link this class with your system package (step 4) 
//import package_name.script_name;

class script_name {
   public static void main(String[] args) {
      System.out.println("Im the main class!");
   }
}
```


### ANT
1. Creamos una carpeta:
`# mkdir proyect_name`

2. Ve a tu carpeta proyect_name y crea con cualquier editor script_name.java, puedes utilizar el codigo anterior: 
`# mkdir proyect_name`

3. Ejecuta ant en tu proyecto:
`# cd proyect_name`
`# ant`

4. Ejecuta el proyecto:
`# ant run`


### MAVEN
1. Creamos una carpeta:
`# mkdir proyect_name`

2. Ve a tu carpeta proyect_name y ejecuta:
`#cd proyect_name`
`# mvn archetype:generate -DgroupId=com.miempresa.app -DartifactId=myapp -Dversion=1.0.0 \
      -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false`
      
3. Edita el archivo pom.xml generado con cualquier editor de texto plano:
`# nano pom.xml` OR `# code pom.xml` OR `# gedit pom.xml`
#### pom.xml
> Modificar lo que esta entre asteriscos para que concuerde con tu proyecto

```xml
<project>

  <modelVersion>4.0.0</modelVersion>
  <groupId>**com.miempresa.app**</groupId>
  <artifactId>**mi-app**</artifactId>
  <version>**1.0.0**</version>
  <name>**mi-app**</name>

  <build>
    <plugins>
      <plugin>
        <!-- Para construir un JAR ejecutable -->
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <version>3.0.2</version>
        <configuration>
          <archive>   
            <manifest>
              <addClasspath>true</addClasspath>
              <classpathPrefix>./</classpathPrefix>
              <mainClass>**com.miempresa.app**.**script_name**</mainClass>
            </manifest>
          </archive>
        </configuration>
      </plugin>

      <plugin>
        <!-- Para ejecutar el JAR creado --> 
        <groupId>org.codehaus.mojo</groupId>
          <artifactId>exec-maven-plugin</artifactId>
          <version>1.2.1</version>
          <configuration>
            <mainClass>**com.miempresa.app**.**script_name**</mainClass>
          </configuration>
       </plugin>
    </plugins>
  </build>

  <dependencies>
    <dependency>
      <!-- Prueba de unidades -->
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
      <scope>test</scope>
    </dependency>
  </dependencies>

</project>
```

4. Compilamos:
`# mvn  compile`

5. Para ejecutar el bytecode:
`# cd target/classes  &&  java com.miempresa.app.**script_name**  &&  cd ../..`

6. Empaquetamos el jar:
`# mvn package`

7. Lo ejecutamos:
`# mvn  exec:java`

8. Para ejecutar las pruebas unitarias:
`# mvn test`


### GRADLE
1. Creamos nuestra carpeta de proyecto:
`# mkdir  proyect_name  &&  cd  proyect_name`

2. Creamos la estructura:
`# gradle  init  --type  java-library`

3. Edita a tu gusto las clases que vienen por defecto poniendo atención al nombre que les das para el siguiente caso, llamemoslas script_name

4. Modifica el archivo build.gradle:
`# sudo nano build.gradle`
#### build.gradle
> Modificar lo que esta entre asteriscos para que concuerde con tu proyecto

```gradle
apply plugin: 'java'
apply plugin: 'application'

repositories {
    jcenter()  
}

dependencies {
    testCompile 'junit:junit:4.12'         
}

jar {
    manifest {
       attributes ('Main-Class': '**script_name**')
    }
}

mainClassName = '**script_name**'
```

#### script_test.java
```java
import org.junit.Test;
import static org.junit.Assert.*;

public class MainTest {

  @Test
  public void testMain() {
      // Prueba vacía
  }
}
```

5. Compilamos:
`# ./gradlew  assemble`

6. Ejecutar el bytecode(opcional):
`# cd build/classes/main  &&  java Main  &&  cd ../../..`

7. Ejecutar el jar:
`# java  -jar  build/libs/**miapp**.jar`

8. Ejecutar las pruebas unitarias:
`# ./gradlew  test`

9. Para ver el informe de las pruebas:
`# firefox build/reports/tests/index.html`
