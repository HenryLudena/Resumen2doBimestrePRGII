# WorkShop Segundo Bimestre Programación II

Nombre: **Henry Ludeña**

Grupo: **GR2SW**

## **Tema 1:** Corrección Examen Primer Bimestre

El comienzo del Segundo Bimestre fue con un tema respecto a la corrección del examen del Primer Bimestre, durante la resolución de este se reconocieron algunos aspectos nuevos respecto a código se tiene:

### ***ArrayList***

El ArrayList es una clase de Java que proporciona una matriz de arreglo, la cual varía su tamaño según los datos que se vayan agregando, de esta manera se manipula y almacena variables como en una matriz haciendo todo esto algo más sencillo y flexible. Además, de poseer una optimización de recursos al poder reducir o aumentar su tamaño según la necesidad.
Se permite la duplicación de datos, de esta manera se permite una búsqueda eficiente si se requiere la repetición de un dato.

- $ La clase ArrayList permite almacenar datos primitivos y de referencia como lo son los String, int, double, float, etc.
- $ Tiene acceso a nuevos comandos tal es el caso de *contains()*, *indexOf()*, ...

Ejemplo de un ArrayList de tipo String:

```java
// Crea una Lista vacia
ArrayList<String> lista = new ArrayList<>(); 
// Agrega elementos a la lista
lista.add("Hola");
lista.add("Perro");
lista.add("Casa");
// Imprime todos los elementos en la terminal              
System.out.println(lista);    

//De igual manera se puede hacer uso de la clase contain para verificar si existe cierto elemento de la lista
// Verifica si existe "Hola"
if (lista.contains("Hola")) { 
// Si se encuentra se imprime            
System.out.println("Existe Hola!");       
} else{
//Caso contrario indica que no existe                                     
System.out.println("No Existe.");      
}                                          
```

### ***HashSet:***

HashSet es un Array que trabja de forma similar que ArrayList por lo cual se define como un arreglo que contiene una cantidad de información notable, a diferencia de los arreglos de cadenas como String[] donde se limita a una manipulación limitada debido a su complejo uso cuando se insertan demasiados datos.

```java
        // Creación de un HashSet de tipo String
        HashSet<String> set = new HashSet<>();

        //Elementos agregados al HashSet como una List
        set.add("Manzana");
        set.add("Banana");
        set.add("Cereza");
        set.add("Durazno");
        set.add("Fresa");

        //Impresión del HashSet con los datos insertados
        System.out.println("HashSet: " + set);
```

Algo que diferencia al HashSet del ArrayList, es que el primero no permite el ingreso de datos repetidos, algo que es útil en ciertas situaciones como ingresos de datos a una database.

### ***Lectura de Archivos:***

La lectura de archivos se basa en el uso de objetos los cuales permiten la identificación de datos de un archivo lo cual se puede hacer mediante diversas clases al instanaciarlas, en este caso se destacan: file, BufferedReader, ...

```java

        //Ruta del archivo a leer
        String rutaArchivo = "archivo.txt";

        // Creación de un objeto File
        File archivo = new File(rutaArchivo);
            // Creación de un objeto FileReader para leer el archivo
            FileReader fileReader = new FileReader(archivo);

            // Creación un objeto BufferedReader para leer líneas de texto.
            BufferedReader bufferedReader = new BufferedReader(fileReader);
            // Lectura de cada línea del archivo e impresión en la consola
            String linea;
            while ((linea = bufferedReader.readLine()) != null) {
                System.out.println(linea);
            }

            // Cierra el BufferedReader y el FileReader
            bufferedReader.close();
            fileReader.close();
```

![Lectura Archivos](/Imagenes/descarga.png)

### ***Comandos Varios:***

- $ **Line.split("dato"):** Se aplica a un array o a un arreglo de cadenas, lo cual hace es esperar un String en diversos String en el punto especificado. Por ejemplo:

```java
        // Cadena de texto con palabras separadas por comas
        String texto = "Manzana,Plátano,Uva,Fresa,Piña";

        // Cadena en palabras conformado de strings separados por comas (en este caso 5)
        String[] palabras = texto.split(",");

        //Impresión de los resultados con un foreach
        for (String palabra : palabras) {
            System.out.println(palabra);
        }
```

## **Tema 2:** Diagramas de Casos de Uso

### ***Objetos***

Se puede definir como objeto en POO a aquello que en la vida real le podríamos llamar ser u objeto y posee ciertas características, que lo distinguen del resto, en programación se denominan métodos, un objeto se compone de varios ellos.

```java
public class Moto{
    //Llamado de la clase Scanner en un método estático para de esta manera llamarla por su variable en cada método.
    public static Scanner sc = new Scanner(System.in);
public String marca(){
    System.out.println("Ingrese la marca de su moto");
    String marca = sc.nextLine();
    return marca;
}

public int placa(){
    System.out.println("Ingrese la placa");
    int numero = Integer.parseInt(sc.nextLine());
    return numero;
}
}
```

A través de esto se pueden definir muchas caracteírsticas de los objetos, y según lo que se desee mostrar en pantalla, el ámbito variará se tiene el caso de:

- $ Public: Ámbito más "general" permite importar el método a otra clase.
- $ Private: Ámbito más privado únicamente puede llamarse dentro de la propia clase (grupo restringido).
- $ Protected: Ámbito en el cual no puede llamarse, el método es únicamente para sí mismo.

![Ejemplo de Objeto](/Imagenes/EjemplodeObjetoAuto.jpg);

### ***Diagrama de Caso de Uso***

Los diagramas de caso de uso son esquemas que ayudan a una explicación sencilla y eficaz respecto a un tema, gracias a la identifcación de componentes del sistema y sus respectivos requerimientos desde un punto de vista amplio y ordenado.

Partes del diagrama de caso de uso:

- $ **Escenario:** Es el software o modelo manejado por el actor (punto focal). Tiene un nombre sencillo que describe su uso frente al usuario.
Puede tener ser principal o secundario. El principal es el sistema en sí, por la razón de que los secundarios son los derivados de este (complementos)
- $ **Actor:** Interactúa con sistema y esto a la vez permite interacción con el caso de uso puede ser persona, objeto o software que desempeña un rol.
- $ **Funcionalidades (Casos de uso):** Incluyen los métodos que se realizan en el software estos empiezan por un verbo (la acción) que realiza el actor.
- $ **Relaciones:** Es aquella "línea" que conecta los casos de uso, pueden ser de: uso, inclusión, extensión o generalización.

![Tipos de Relaciones](/Imagenes/RelacionesFundamentales.png)

1. La inclusión (<<.Include.>>) es una relación "obligatoria" cuando se ejecuta la acción de un caso específico, puede ser que al comprar en una tienda sea obligatorio pagar con efectivo o tarjeta.
2. La extensión (<<.extend.>>) es aquella relación "opcional" que se ejecuta si el actor lo desea puede ser una opción de "Pedir Ayuda"
3. La Generalización es una relación de herencia entre casos de uso.

He aquí un ejemplo para mayor comprensión del tema:

![Ejemplo de Diagrama Lobo](/Imagenes/EjemploUseCase.png)

## **Tema 3:** Diagramas UML

En este tema se aprenderá a utilizar diagramas para representar mejor un sistema software, el cual ayuda a identificar de mejor manera una idea base que sirve como guía para pasarlo a código.
Aunque los detalles en este diagrama no son tan específicos, si poseen más información que por ejemplo un diagrama de caso de uso.
Los diagramas UML son herramientas gráficas para representar modelos conceptuales donde se indica los ámbitos, métodos, clases, interfaces, ... Esto tiene una base fundamentada en herencia algo que lo diferencia de un diagrama de flujo como lo era en programación estructurada.

![Diagrma UML](/Imagenes/DiagramaUMLLobo.png)

Dependiendo de la relación esta puede tener un significado diferente como en el caso de Uso así se posee, en otras palabras cada flecha tiene su propio uso:

![Significado Flechas](/Imagenes/SignificadoFlechas.png)

Además, en el diagrama UML se tiene la asociación, donde destaca la cardinalidad que es la relación entre dos elementos del diagrama. Se posee diversos ejemplos de esta:

- $ Cardinalidad Bidireccional con multiplicidad 0...1 o 1

![Bidireccional](/Imagenes/Bidireccional.png)

- $ Direccional con multiplicidad 0..1 o 1

![Direccional](/Imagenes/Direccional.png)

_ $ Recursividad

![Recursividad](/Imagenes/Recursividad.png)

## **Tema 4:** Herencia

La herencia (Extensión o Generalización) se define como el mecanismo por el cual se pueden crear nuevas clases a partir de otras, es decir, se heredan los métodos de la clase principal llamada clase padre a las subclases llmadas clase hijo. Mediante esto se puede modificar, añadir o eliminar métodos en las subclases.

Se puede tener el caso de que a partir de una clase padre vehículo, se hereden sus caractríticas a las clases hijo que añadieron nuevos argumentos como: tipo de vehículo, color o número de serie.

- He aquí un ejemplo de herencia para utilizar los métodos de la clase padre en la subclase:

```java
public class ClasePadre{
    public void metodoClasePadre(){
        System.out.println("Este es un método padre");
    }
}
```

```java
public class ClaseHijo extends ClasePadre {
    public void metodoClaseHijo(){
        // Llamando al método de la superclase desde la subclase, para esto se emplea la palabra super.
        super.metodoClasePadre();
    }
}
```

- También se puede añadir código al método heredado por el padre, esto se debe denotar con *@Override* para que el programador conozca los cambios a la vez del lenguaje aunque no es obligatorio.

```java
public class ClasePadre{
    public void metodoClasePadre(){
        System.out.println("Este es un método padre sin cambios");
    }
}
```

```java
public class ClaseHijo extends ClasePadre {
    // Añadiendo una instrucción adicional dentro del método heredado que no
    @Override
    public void metodoClasePadre(){
        super.metodoClasePadre();
        System.out.println("- Este es el nuevo código agregado - ");
    }
}
```

![Herencia](/Imagenes/Herencia.jpg)

### ***Ventajas y Desventajas de usar Herencia***

**Ventajas**:

- Mejora de diseño, al dar los problemas que se pretenden resolver.
- Ahorro de líneas mediante la reutilización del código de la clase padre en las clases hijo
- Facilidad de mantenimiento ya que si hay algún error o actualización solo será en la clase hijo.
- Permite crear relaciones jerárquicas entre objetos.
- Facilita la extensión al crear nuevas clases al no tener que modificar ninguna otra clase.

**Desventajas**:

- Mayor acoplamiento entre más reutilización de código se haga, cada subclase será más dependiente de la anterior, enraizándose a tal punto de que si necesita algún cambio en alguna clase padre esto afectará a sus clase hijo.

Algo a recalcar es que los constructores no se heredan por lo cual cada sublcase debe crear el suyo propio internamente.

```java
public class Subclase(){
    //Creación del constructor de la subclase
    public void SubClase(){
        //Llamada del constructor de la clase padre en una subclase.
        super.ClasePadre();
    }
}
```

En caso de que no se llame al constructor de la superclase dentro del constructor de la subclase, el programa lo hará automáticamente. Si el constructo sin parámetros no existe habrá un error en la ejecución.
Como modificadores de acceso para las clases se poseen los ámbitos: public, private, protected o ningún ámbito.

En el caso específico de protected puede ser un problema su llamado al hacer accesible desde cualquier subclase, lo cual complica la tarea de mantenimiento, y de igual manera sería accesible desde los paquetes y sean subclases o no.

## **Tema 5:** Clase y Subclase

Las clases como parte fundamental de la programación orientada a objetos se definen como una plantilla donde se pueden crear objetos, por ende los objetos son instancias directas en una clase. Si esto lo relacionamos con herencia entonces las clases son las "clases padre" y las subclases son las "clases hijas" donde estas últimas heredan los objetos total o parcialmente de su padre.
Para la herencia se realiza mediante un <<"Extend">> donde la clase hija hereda todos los objetos del padre con el método "super" en el constructor si se desea eliminar o cambiar los datos heredados se debe realizar un objeto con el mismo nombre que en el padre y se le pueden añadir nuevos datos o inhabilitar.

```java
public class ClasePadre{
    public void metodoClasePadre(){
        System.out.println("Este es un método padre sin cambios");
    }
}
```

```java
public class ClaseHijo extends ClasePadre {
    // Añadiendo una instrucción adicional dentro del método heredado que no
    @Override
    public void metodoClasePadre(){
        super.metodoClasePadre();
        System.out.println("- Este es el nuevo código agregado - ");
    }
}
```

## **Tema 6:** Compisición vs Agregación

Para realizar la comparación entre estos dos conceptos primero se debe definirlos:

- $ **Composición:** Es la relación entre diversos objetos hacia uno en específico, es decir, un objeto se compone de una o varias clases, como si se tratase de una Subclase, este aspecto tiene ciertas partes clave como por ejemplo: relación de todo, reutilización, encapsulamiento (getters y setters) y dependencias.

```java
//Clase Motor, parte del auto a evaluar
public class Motor {
    //Acciones que puede realizar el motor
    public void arrancar() {
        System.out.println("Motor arrancado.");
    }
}

//Clase coche que hereda del motor
public class Coche {
    //Variable motor extraída de la clase "motor"
    private Motor motor;
    // Composición: el Coche tiene un Motor
    public Coche() {
        this.motor = new Motor(); 
    }
    //Acción que realiza el coche con un motor
    public void arrancarCoche() {
        System.out.println("Arrancando el coche.");
        motor.arrancar(); 
    }
}
```

- $ **Agregación:** Es una relación entre clases que describe como un objeto puede ser parte de otro pero el objeto a incluir puede ser externo, es decir, independiente. Se define con un "está compuesto por"
Sus características más destacadas son: Independencia de objetos, reutilización y asociación débil.

- $ **Agregación vs Composición:** Entre estos dos conceptos existen diferencias notables debido a su uso, y condiciones según como se presenten:
- Independencia: La agregación tiene un menor acoplamiento al no tener una fuerte vinculación con otros objetos, por lo cual si un objeto se elimina el resto puede seguir en sus funciones.
- Asociación: En la agregación la relación entre objetos es débil por lo cual no están estrechamente vinculados todos los objetos, más bien pueden estar asociados consigo mismos, por ejemplo en la recursividad.

## **Tema 7:** Conceptos Básicos de Base de Datos

Una base se define como un programa donde se almacena una gran cantidad de datos, mediante tablas (filas y columnas), cada dato se almacena en una "celda" de posición x, y. Además, a través de comandos el usuario tiene la posibilidad de acceder a datos específicos de dichas tablas.
Debido a su organización y especialización en el tema, las bases de datos reemplazan a los Array o las cadenas de arreglo (String[]) cuando se trata de un guardado de datos masivo.

![DataBase](/Imagenes/BaseDatos.png)

Existen diferentes modelos de base de datos, desde las más sencillas como SQLite hasta las más complejas (SQL, MySQL, ...), la elección de que modelo de base usar depende del usuario, pero esto por lo general por ejemplo se puede necesitar un programa para lugares pequeños como tiendas o para educación. En esos casos es cuando no es necesario una base de datos muy grande aparte que su mantenimiento es más caro y se requiere de conocimientos más complejos en la materia.

En una base de datos existen 3 tipos de relaciones para la interacción de datos:

- 1___________1  Uno a Uno

- 1 __________+ Uno a muchos

- +___________+ Muchos a Muchos

De los tres el más importante es el Uno a Muchos debido a que los otros se derivan de este.

## **Tema 8:** SQLITE

En este caso para la materia la base de datos a usar fue SQLITE debido a su facilidad para manejar los datos, insertar, eliminar y leerlos, en otras palabras para un CRUD (Create, Read, Update, Delete). Además, no requiere factores externos como acceder a páginas de terceros mediante internet, pero esa es una limitantes el no subirse a la nube automáticamente sino más bien alojarse de manera local.

![SQLITE](/Imagenes/SQLITE.jpeg)

Para manejar SQLITE en este caso en VS CODE se requieren de tres factores:

- Un JDBC: que establezca la conexión entre el código en Java y la base de datos, este JDBC puede ser en formato JAR para mayor facilidad al agregar a las librerías. Esta biblioteca se encarga en establecer la conexión con la base de datos de tal manera que se puede acceder a su información para su respectiva manipulación (CRUD) de tal manera que el usuario es el que establece como usar la información, por ejemplo mostrarla en Frames mediante Tablas.

![JDBC](/Imagenes/JDBC.jpeg)

- Extensión SQLITE: en VS Code existe una extensión llamada SQLITE la cual permite crear los archivos .sql los cuales ayudan a establecer la conexión con la base de datos, es decir, los script sql son quienes envían la información a la base de datos para realizar un CRUD.

![SQLITEExtension](/Imagenes/SQLITEExtension.png)

- Extensión SQLITE Viewer: mediante los dos componentes anteriores es suficiente para establecer la conexión a la base y realizar el CRUD pero cuando se quiere visualizar los datos que contiene la base de datos o el script sql, es necesario de una nueva extensión para visualizar las tablas. De esta manera, se puede observar los datos que se ingresan, además de lograr identificar algún error más fácilmente.

![SQLITEViewer](/Imagenes/SQLITEViewer.png)

### ***Comandos CRUD:***

Para manipular los datos como se mencionó existen una serie de comandos a insertar para que el CRUD ocurra, en el script se puede insertar directamente pero en el lenguaje se debe hacer esto mediante querys.

- **CREATE:** Para insertar una tabla en la interfaz se necesita un nombre y los campos (columnas) de la tabla, donde dos campos deben ser el ID como identificador de cada fila más conocido como PRIMARY KEY (PK) y el Estado para comprobar si se encuentra activo (A) o no:

```SQL
CREATE TABLE SEXO(
     IdSexo     INTEGER     NOT NULL PRIMARY KEY AUTOINCREMENT
    ,Nombre     VARCHAR(10) NOT NULL
    ,Estado     VARCHAR(1)  NOT NULL DEFAULT('A')
);
```

- **INSERT:** Una vez que se crea la tabla se debe insertar los datos dentro de esta, para eso se debe especificar que dato va en que campo, los campos que son nombrados como NULL o aquellos nombrados por DEFAULT pueden tener vacíos, el resto deben contener alguna información obligatoriamente.

```SQL
--NOMBRE es la etiqueta de la columna en la tabla, "HEMBRA" es el valor ingresado en dicha columna
INSERT INTO SEXO (NOMBRE) VALUES ("HEMBRA");
INSERT INTO SEXO (NOMBRE) VALUES ("MACHO");
INSERT INTO SEXO (NOMBRE) VALUES ("SIN SEXO");
```

- **UPDATE:** Cuando se tiene datos ingresados en la tabla ya sean NULL o NOT NULL y se desee cambiar una celda o columna especifica, entonces se recurre al UPDATE, este comando lo que hace es actualizar dicha casilla con un parámetro que es la información que se desee actualizar.

```SQL
--En el ID = 3 de la columna NOMBRE de la tabla SEXO, se actualiza o coloca "NOMBRE"
--En este caso "SIN SEXO" va a ser cambiado por "CAMBIO" 
UPDATE SEXO SET Nombre = "CAMBIO" WHERE IdSexo = 3
```

- **DELETE:** En caso de querer borrar una fila o una celda especifica en una tabla se puede hacer con DELETE, el cual elimina totalmente la información contenida en dicho lugar.

```SQL
--En este caso se va a eliminar la fila donde el ID es igual a 2 que es donde se encuentra "MACHO"
DELETE FROM SEXO WHERE IdSexo = 2;
```

Este tipo de DELETE no es recomendado debido a como se mencionó la eliminación total del dato, lo cual sería pérdida de información que no puede recuperarse a futuro. Además, de existir un salto en los ID debido a que si se elimina un ID, este no será reemplazado, más bien la tabla saltará dicho número.

Para estos casos es más recomendable usar un UPDATE actualizando así el estado de la fila lo cual la desahabilitaría para de esta forma al llamar la tabla o hacer un UPDATE ya no le haga efecto a la fila deshabilitada.

```SQL
--Se establece el estado de la fila 2 (donde está "MACHO") como X es decir deshabilitado
UPDATE SEXO SET Estado = 'X' WHERE IdSexo = 2
```

- **SELECT:** Una vez se ha creado una tabla y se ha insertado datos dentro de ella, entonces existe la posibilidad de visualizarla, esto se hace mediante un SELECT en el cual se proporciona los campos que se desee que aparezcan, y de que tabla o tablas se obtiene la información.

```SQL
--Se imprime una tabla con Id y Nombre de la tabla SEXO donde el estado sea activo, es decir, los desahibilitados no son cinluidos
SELECT IdSexo, Nombre 
FROM SEXO
WHERE Estado = 'A';
```

- **FOREIGN KEY (FK):** Cuando se desea tener una tabla que contenga columnas de más de dos tablas diferentes entonces es cuando se recurre a un FOREIGN KEY, recordando los conceptos de los PK, los FK son los PK de cada tabla "importada" mediante los cuales la tabla principal reconoce que filas debe extraer de otra tabla.

```SQL
--Se crea una nueva tabla MASCOTA_TIPO con el FK de SEXO para ejemplificar
CREATE TABLE MASCOTA_TIPO(
    IdMascotaTipo   INTEGER         PRIMARY KEY AUTOINCREMENT,
    IdSexo          INTEGER         NOT NULL,
    Nombre          VARCHAR(10)     NOT NULL,
    Estado          VARCHAR(1)      NOT NULL DEFAULT('A'),
    FOREIGN KEY (IdSexo) REFERENCES SEXO (IdSexo)
);
--Ingreso de tipos de mascota para la tabla TIPO_MASCOTA, los números son los FK traídos de SEXO
INSERT INTO MASCOTA_TIPO (IdSexo, Nombre) VALUES (1, "Gato");
INSERT INTO MASCOTA_TIPO (IdSexo, Nombre) VALUES (2,"Perro");
INSERT INTO MASCOTA_TIPO (IdSexo, Nombre) VALUES (1,"Loro");
--SELECT el cual admite las dos tablas SEXO Y MASCOTA_TIPO
--Para reconocer cada tabla se le crea una variable como identificador para extraer sus columnas
SELECT s.Nombre, m.Nombre
FROM MASCOTA_TIPO m
JOIN SEXO s ON s.IdSexo = m.IdSexo
WHERE m.Estado = 'A';
```

El resultado al final sería el siguiente con el SELECT en FOREIGN KEY:
![SELECTSQL](/Imagenes/SELECTSQL.png)

## **Tema 9:** Arq N-Tier

El Arq N-Tier es una arquitectura de n capas donde la presentación, la conexión, la lógica de negocios están separadas en capas para un manejo más flexible, eficaz y sencillo de manipular.

![ArqNTier](/Imagenes/ArqNTier.png)

Aunque cada empresa va a tener su propia lógica y su propio manejo, en general, se resume en 4 capas: User Interface (UI), Business Logic (BL), Data Access Component (DAC) y Framework.

### ***Framework***

El Framework es una capa que tiene diversidad de funciones por ejemplo: Consistencia (uso de estándares), Seguridad (protección contra ataques) y Escabilidad (Expansionismo a futuro).

En el caso del curso, el campo en el que más se enfocó es Seguridad al brindar clases que soporten las excepciones que lanza algún objeto, siendo así que los errores se manejan de manera más resumida, al recoger únicamente la ubicación útil de la excepción y desechando el resto.

![Framework](/Imagenes/Framework.png)

### ***Data Access***

Como su nombre lo indica el Data Access se encarga del acceso a la data, es decir, la información que en este caso se encuentra en la base de datos, por lo cual está capa es la que se encarga de llamar a la base y extraer los datos según se requiera por lo cual es la que se encarga de los query (CRUD), para ello mediante el JDBC se llaman a objetos como Connection, Statement, ... los cuales están listos para recibir las órdenes de acceso a la base.

Los query en palabras sencillas son las operaciones CRUD (INSERT, UPDATE y SELECT) que se realizaban en el script sql, solo que en este caso se le añade otros objetos para el llamao de código a base.

![DataAccess](/Imagenes/DataAccess.png)

### ***Business Logic***

La Business Logic (BL) (Lógica de Negocios) en términos generales es aquella que implementa las reglas, operaciones y procesos clave en un programa para que este se ajuste a las necesidades del negocio o empresa. Como ejemplo se tiene: Ordenamiento (Gestión de Inventario), Autorización (Verficar el acceso a solo x usuarios), Pedidos (Procesamiento de data).

Aplicando esta capa para el procesamiento de información en la base de datos quedaría que la BL es el objeto que brinda que columnas de la tabla se requiere, según las necesidades del usuario.

![BusinessLogic](/Imagenes/BusinessLogic.png)

De la misma manera esta lógica se aplica para los otros query (DELETE, INSERT y UPDATE) mediante los cuales la BL escoge que partes de las tablas desea a partir de las necesidades del usuario (o empresa).

### ***User Interface***

La User Interface (UI, Interfaz de Usuario) es el "producto final" debido a que gracias a la BL y la Data Access se han obtenido los datos de la base de datos por lo cual en la UI se presentan dichos datos. Se pasa de un lenguaje de programador a una interfaz entendible para cualquier usuario debido a que es el producto que la empresa o usuario ofrece a los clientes.

En términos de programación la UI son los Frame que se presentan en la ejecución del programa, los Tabel, Label, TextField, ... que lo conforman.

![UserInterface](/Imagenes/UserInterface.png)
![FrameResultado](/Imagenes/FrameResultado.png)

## **Tema 10:** DTO

Los DTO (Data Transference Object) son como un conjunto de Data Access Component (DAC) pero en realidad no lo es porque lo que realmente está llamando y haciendo un conjunto es a las Entidades de las Tablas que desea el usuario, por lo cual es una manera más simplificada de evitar diversos DAC llamándolos mediante bucles, lo cual hace más sencillo el llamado a la base de datos al estar más simplificado y más eficaz.

Algunas de sus utilidades son:

- **Reducción de sobrecarga de datos:** Al no tener que llamar cada Tabla en su propio DAC
- **Manejabilidad:** Al encontrarse los llamados a la base de datos en una clase, el manejo para futuros cambios es más sencillo y eficaz.
- **Comprensión:** En caso de que el código sea manejado por diversas personas, se decida cambiar de base de datos, etc. el cambio no se dificultaría demasiado debido a la fácil comprensión de la transferencia de datos.

![DTO](/Imagenes/DTO.png)

## **Tema 11:** Personalización

La personalización en una interfaz de usuario es un aspecto importante no indispensable pero es algo a tener en cuenta debido a que son las primeras impresiones del cliente sobre el producto, el atractivo a primera vista que da a entender al cliente que calidad de producto le espera.

Para este tema cabe destacar dos elementos que se encuentran por defecto en Java pero que se puede personalizar ciertos detalles.

### ***Botones***

Los botones que tiene por defecto Java tienen el problema de no ser atractivos debido a que se limitan a que el usuario tenga la idea de como funciona el programa y que aquel cuadrado es un botón que realiza una acción, pero para ponerle más énfasis es mejor detallarlo para un detalle más cuidadoso, porque al final los clientes observan los pequeños detalles.

![Botones](/Imagenes/Botones.png)

Algunos aspectos que se pueden modificar limitándose a no importar librerías son: Texto, Color de fondo, posición, tamaño, ...

Para el uso directo de los objetos de los Botones se recurre a un extend (Herencia) del método JButton

### ***Label (Etiqueta)***

Los textos estáticos que se observa en una interfaz como "Ingrese su usuario" se deben a Label, que por defecto tiene un texto básico que se puede modificar según la necesidad, en las interfaces sería muy monótono si toda la información tuviese el mismo tamaño, color, aspecto en general. Por lo cual personalización es algo que ayuda a una interfaz más atractiva e interactiva a la persona.

![Label](/Imagenes/Label.png)

Aspectos generales a modificar son: Tamaño, Color, Tipo de letra, ...
