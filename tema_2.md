# ÍNDICE
* INTRODUCCION
* HERRAMIENTAS BÁSICAS
* ENTORNOS INTEGRADOS DE DESARROLLO (IDE)
* BUILD(CODE)


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

### Biblioteca estándar del lenguaje C
* Entrada y salida por terminal
* Manejo de archivos
* Funciones matemáticas
### Biblioteca estándar del lenguaje Java
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
     
     Si preferimos usar el código del sistema simplemente compila he importa la librería en tu script:
     `# javac Main.java`     
     
6. Ejecutamos Main: 
`# java  Main`
 
   > _Si prefieres crear un **programa autocontenido**:_
   1. Crea el paquete jar con todas las clases anteriores:
   `# jar cvfe  main  Main  Main.class  package_name/*.class`
   
   2. Ejecutalo 
   `# java -jar main`
