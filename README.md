6.1. Primer proyecto en Maven
Ejercicio 18. Responda a las siguientes preguntas:
1. ¿Qué es Maven?
Maven es una herramienta de gestión de proyectos de software utilizada principalmente para proyectos basados en Java. Facilita la construcción, el manejo de dependencias y la generación de informes. Maven utiliza un formato de proyecto estándar, un archivo de configuración XML (pom.xml), y proporciona una estructura de directorios predefinida para la construcción del proyecto.

2. ¿Cuál es el repositorio central de Maven?, ¿hasta qué punto son fiables las bibliotecas que hay en él?
El repositorio central de Maven es un repositorio en línea que almacena bibliotecas y artefactos de software que pueden ser utilizados como dependencias en proyectos Maven. Este repositorio es mantenido por la comunidad de Maven y contiene una amplia variedad de bibliotecas de código abierto y propietario. En general, las bibliotecas en el repositorio central de Maven son bastante fiables, ya que están sujetas a ciertas políticas y procedimientos de calidad establecidos por la comunidad Maven. Sin embargo, siempre es importante revisar la reputación y la calidad de las bibliotecas antes de incorporarlas a un proyecto.

3. ¿Qué es el repositorio local?
El repositorio local es un directorio en el sistema de archivos del desarrollador donde Maven almacena localmente las dependencias descargadas desde el repositorio central o cualquier otro repositorio remoto. Cuando Maven necesita una dependencia para construir un proyecto, primero verifica si está disponible en el repositorio local. Si no lo encuentra, lo descarga del repositorio remoto y lo almacena en el repositorio local para usos futuros. Este repositorio local permite a Maven trabajar de manera más eficiente al evitar la necesidad de descargar las mismas dependencias repetidamente y también proporciona una mayor autonomía en el desarrollo cuando no se dispone de conexión a internet.

Ejercicio 19. Instale Maven. Por ejemplo, en OpenSuse, se ejecuta:sudo zypper install mavenPara comprobar que se ha instalado correctamente:mvn --version



Ejercicio 20. Realice los siguientes apartados:
1. Cree un proyecto en Maven ejecutando la siguiente instrucción1:
mvn archetype:generate -DgroupId=org.pr2 -DartifactId=miPrimeraAplicacion -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=falsey explore el árbol de directorios generado.


2. ¿Qué es un arquetipo en Maven?
Un arquetipo en Maven es una plantilla predefinida para crear nuevos proyectos, facilitando el inicio rápido de desarrollo al proporcionar una estructura y configuración inicial.

3. Entre el el directorio
miPrimeraAplicacion: cdmiPrimeraAplicacion


4. Explique el fichero pom.xml:
El archivo pom.xml es un archivo de configuración de Maven, un sistema de gestión de proyectos utilizado principalmente para proyectos Java. Maven utiliza este archivo para gestionar las dependencias del proyecto, configurar la construcción del proyecto y definir otras configuraciones importantes.
Algunos elementos son:
<project>: Este es el elemento raíz del archivo pom.xml y encapsula toda la configuración del proyecto.
<modelVersion>: Indica la versión del modelo de objeto de proyecto (POM). En este caso, se está utilizando la versión 4.0.0.
<groupId>, <artifactId>, <version>: Estos elementos definen las coordenadas del proyecto. El groupId identifica de manera única al grupo o a la organización a la que pertenece el proyecto. El artifactId es el nombre del proyecto y el version es la versión actual del proyecto.
<name> y <url>: Proporcionan el nombre y la URL del proyecto, respectivamente.
<properties>: Aquí se pueden definir propiedades personalizadas que luego se pueden usar en otros lugares del archivo pom.xml. En este caso, se define la codificación del origen y las versiones del compilador de Java.
<dependencies>: Este elemento contiene todas las dependencias del proyecto. En este caso, se está incluyendo la dependencia de JUnit para realizar pruebas unitarias.
<build>: Este elemento define la configuración relacionada con la construcción del proyecto. Aquí se pueden configurar varios plugins de Maven que se utilizarán durante la construcción del proyecto.
En resumen, el archivo pom.xml es una parte fundamental de cualquier proyecto de Maven, ya que define la estructura, las dependencias y la configuración de construcción del proyecto. Permite a Maven gestionar eficientemente las dependencias y construir el proyecto de manera consistente.

5. Explore el árbol de directorios.


6. Compile el programa:
mvn compile


7. Ejecute el programa:
mvn exec:java -D exec.mainClass=org.pr2.App


8. Elimine los artefactos generados anteriormente, vuelva compilar y ejecute de nuevo:
mvn clean compile 
mvn exec:java -D exec.mainClass=org.pr2.App


9. Genere la documentación del proyecto, y explórela:
mvn site

cd target/site


10. Explique en qué consisten las siguientes fases:
validate: Verifica que el proyecto sea válido y todas las dependencias estén disponibles.
compile: Compila el código fuente del proyecto y genera archivos de clase en el directorio target.
test: Ejecuta las pruebas unitarias del proyecto utilizando un framework de pruebas como JUnit.
package: Empaqueta el código compilado y otros recursos en un formato específico, como JAR, WAR o EAR.
install: Instala el paquete en el repositorio local de Maven para ser utilizado como dependencia en otros proyectos.
deploy: Copia el paquete a un repositorio remoto para ser compartido con otros desarrolladores o sistemas de producción.
clean: Elimina los archivos generados en el proceso de construcción, como los archivos compilados y los artefactos de construcción.
site: Genera documentación del proyecto, como informes, estadísticas y otros documentos, y la despliega en un sitio web para referencia y colaboración.



