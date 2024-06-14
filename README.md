# Description

This is a project to apply a software modernization 🧑🏻‍💻

# Interpreter commands

```txt
[self.name/]

[self.eAllContents(ClassUnit)/]

[self.eAllContents(ClassUnit)->select(eje.name.contains('JSF') or e.name.contains('Servlet'))/]

[self.eAllContents(Package)->select(p | p.codeElement->forAll(c | not c.oclisTypeOf(Package)))/]

[self.name/]

[self.model/]

[self.model->select(s|s.name.equalsIgnoreCase('io.openliberty.sample.daytrader8'))/]

[self.eAllContents(ClassUnit)/]
```
# Functions in Acceleo
| Operador    | Descripción | Ejemplo    | Resultado |
| ----------- | ----------- | ---------- | --------- |
| collect     | Devuelve una lista con los elementos resultado de aplicar una operación en la lista.        | Sequence{'a', 'b', 'c'}->collect(str | str.toUpper())

"Sequence" crea una lista conteniendo los elementos a, b y, c. Sobre los elementos de esa lista se aplica la operación toUpper (que cambia cada str a mayúscula) y el resultado se coloca en una nueva lista.

El collect puede ser un análogo de una operación map, en donde a los elementos de la lista se les aplica una función que transforma todos los elementos de la lista y retorna el resultado de esa transformación en una nueva lista. En lenguajes como Typescript, podríamos escribir algo como:

const list=["a","b","c"];

list.map((str)=>{return str.toUpperCase();});    |Sequence{'A', 'B', 'C'}      |
| count          | Devuelve un entero con el número de elementos encontrados.              |Sequence{'a', 'b', 'c'}->count('a')

Sobre una lista creada se aplica el "count"           |1           |
|excludes           |Retorna un boolean indicando si el elemento no se encuentra en una lista.               |Sequence{'a', 'b', 'c'}->excludes('a')           |false           |
|exists           |Retorna si existe un elemento en la lista que cumpla con la condición dada.               |Sequence{'a', 'b', 'c'}->exists(str | str.size() > 5)

La expresión evalúa si dentro de la lista existe un string (referidos con el nombre de variable str) cuyo tamaño sea mayor a 5. Si ese es el caso devuelve "true" sino "false"          |false           |
|select           |Retorna un Set con los elementos que cumplen con la condición.               |Sequence{'a', 'b', 'c'}->select(str | str.equals('a'))

La expresión escoge dentro de la lista los strings (referidos con el nombre de variable str) que sean iguales a "a". El resultado es una nueva lista que puede tener cero, uno o más elementos           |Sequence{'a'}           |
| forAll          |Retorna true si la condición se cumple para todos los elementos o false si no.               |Sequence{'a', 'b', 'c'}->forAll(str | str.equals('a'))

La expresión evalúa si todos los strings de la lista son iguales a "a"           | false          |
|selectByType           |Retorna una lista de elementos del tipo dado como parámetro.               |Sequence{1,2,3,'a', 'b', 'c'}->selectByType(String)

La expresión devuelve los elementos de la lista que son conformes al tipo String           |Sequence{'a','b','c'}           |

# Made with
[![Java](https://img.shields.io/badge/java-2e84bd?style=for-the-badge&logo=data:image/png;base64,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&logoColor=white&labelColor=000000)]()

# Java EE8: DayTrader8 Sample

This sample contains the DayTrader 8 benchmark, which is an application built around the paradigm of an online stock trading system. The application allows users to login, view their portfolio, lookup stock quotes, and buy or sell stock shares. With the aid of a Web-based load driver such as Apache JMeter, the real-world workload provided by DayTrader can be used to measure and compare the performance of Java Platform, Enterprise Edition (Java EE) application servers offered by a variety of vendors. In addition to the full workload, the application also contains a set of primitives used for functional and performance testing of various Java EE components and common design patterns.

DayTrader is an end-to-end benchmark and performance sample application. It provides a real world Java EE workload. DayTrader's new design spans Java EE 8.

This sample can be installed onto Liberty runtime versions 18.0.0.2 and later. A prebuilt derby database is provided in resources/data


To run this sample, first [download](https://github.com/OpenLiberty/sample.daytrader8/archive/master.zip) or clone this repo - to clone:
```
git clone git@github.com:OpenLiberty/sample.daytrader8.git
```

From inside the sample.daytrader8 directory, build and start the application in Open Liberty with the following command:
```
mvn clean package liberty:run
```

The server will listen on port 9080 by default.  You can change the port (for example, to port 9081) by adding `mvn clean package liberty:run -DtestServerHttpPort=9081` to the end of the Maven command.

Once the server is started, you should be able to access the application at:
http://localhost:9080/daytrader



## Notice

© Copyright IBM Corporation 2019.

## License

```text
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
````
