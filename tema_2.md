# ÍNDICE
* INTRODUCCION
* HERRAMIENTAS BÁSICAS
* ENTORNOS INTEGRADOS DE DESARROLLO (IDE)


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
* _Tipos:_
   * bibliotecas dinámicas (.DLL o .so) (.jar en Java)
   * bibliotecas estáticas (.LIB o .a)
* _Partes de una biblioteca:_
   * Especificación (ofrece una API)  _(API = Interfaz de Programación de Aplicaciones)_
   * Implementación
  
### ENTORNO NECESARIO EN JAVA
* _JRE: necesario para ejecutar programas_
   * JVM (inteprete java)
   * Biblioteca estándar
* _JDK: necesario para desarrollar programas_
   * Herramientas: javac, jar, javadoc, ...

### CONSTRUIR (BUILD) 
_Construir (Build) = Compilar + Enlazar_
* _Opciones:_
   * Equipo local
   * Servidor de construcción
* _Equipo local - Herramientas de construcción_
   * make, ninja (C, C++)
   * ant, maven, gradle (Java)
   * grunt, gulp (Javascript)
   * rake (ruby)
* _Buildfiles_
   * make: Makefile
   * ninja: build.ninja
   * ant: build.xml
   * maven: pom.xml
   * gradle: build.gradle
   * grunt: Gruntfile.js
   * gulp: gulpfile.js
   * rake: Rakefile
* _Gneradores de buildfile - Herramienta y archivo asociado_
   * CMake: CMakeLists.txt
   * Meson: meson.build
* _Servidores de construcción - Integración continua (CI)_
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
