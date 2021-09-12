<!--ts-->
# Índice
   * [Introducción](#introducción)
   * [Justificación](#justificación)
   * [Descripción del estándar](#descripción-del-estándar)
   	    * [Entidades](#entidades)
   	    * [Atributos](#atributos)
   	    * [Llaves primarias](#llaves-primarias)
   	    * [Llaves foráneas](#llaves-foráneas)
   	    * [Excepciones](#excepciones)
<!--te-->






# 
# Introducción

En este trabajo de investigación se tiene como principal objetivo la descripción de algún estandar para la escritura de código en bases de datos MySQL. En el transcurso de la investigación de este trabajo se descubrió varios estilos de escritura de código como lo son: camelCase, PascalCase, snake_case y kebak-case. El autor de este trabajo eligió investigar más a fondo sobre el estilo snake_case, y este documento brindará la manera en la que se aplica ese estándar para una base de datos MySQL.

# 
# Justificación

En el transcurso de la investigación de este trabajo escrito sobre los estándares de nombres para una base de datos como MySQL, descubrí distintos estilos para la escritura de código en lenguaje de bases de datos. Por ejemplo, escritura camelCase, snake_case, PascalCase y kebab-case. De los ejemplos mencionados, elegí el estilo snake_case. Me di cuenta que ese estilo de escritura fue con el que empecé y nunca supe que era un estilo para la definición de variables, tablas y métodos en lenguajes de programación. Cuando programaba en Python al inicio de la carrera utilizaba ese estilo ya que me parecía el más correcto y el más legible para cualquier lector. A día de hoy me sigue gustando y aun lo sigo poniendo en práctica.

# 
# Descripción del estándar

Snake case se refiere a un estilo de escritura en el que cada espacio se reemplaza por un guión bajo (_) y la primera letra de cada palabra escrita en minúsculas. Es una convención de nomenclatura comúnmente utilizada en ciencias de la computación, por ejemplo, para nombres de variables y subrutinas y para nombres de archivos. Un estudio encontró que los lectores pueden reconocer los valores de la escritura de estilo serpiente más rápido que la escritura de estilo camello. Esta notación, cuando se usa en mayúsculas, es común al declarar constantes en lenguajes como PHP o JavaScript. La notación Snake Case en su versión común también se usa a menudo en la declaración de los nombres de los campos en las bases de datos. Además, también se utilizó en la declaración de variables PHP y de hecho sigue siendo el estándar para muchos desarrolladores a la hora de programar plugins o temas para WordPress.

# 
# Entidades

En el ejemplo que se presenta a continuación se muestra la manera en la que se debe escribir una entidad con el estándar snake_case:

```bash
create table usuario_snake_case(
);
```
# 
# Atributos

En el ejemplo que se presenta a continuación se muestra la manera en la que se debe escribir atributos de una entidad con el estándar snake_case:

```bash
create table usuario_snake_case(
	carnet_id int not null,
	codigo_libro int not null,
	fecha_prestamo date not null
);
```


# 
# Llaves primarias

En el ejemplo que se presenta a continuación se muestra la manera en la que se debe escribir las llaves primarias con el estándar snake_case:

```bash
create table usuario_snake_case(
	codigo_libro_pk primary key
);
```

# 
# Llaves foráneas

En el ejemplo que se presenta a continuación se muestra la manera en la que se debe escribir las llaves foráneas con el estándar snake_case:


```bash
create table usuario_snake_case(
	carnet_id_fk int not null,
	foreign key (carnet_id)
);
```

# 
# Excepciones

En los casos en que los datos se envían a una API externa y el desarrollador no tiene control sobre los nombres de las variables, a menudo es necesario utilizar las propiedades de snake_case. Para usar las reglas de notación de puntos y camelcase juntas, sería útil agregar el soporte allowSnakeCase a la regla de notación de puntos. 

```bash
{
    "rules": {
        "camelcase": 2
        "dot-notation": [2, {"allowSnakeCase": true}]
    }
}
```

Y el comportamiento resultante: 

```bash
var data = {};
data.foo_bar = 42; // warning from camelcase

var data = {};
data["fooBar"] = 42; // warning from dot-notation

var data = {};
data["foo_bar"] = 42; // no warning
```



