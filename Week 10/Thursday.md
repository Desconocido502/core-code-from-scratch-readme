# Thursday 16-06-2022

<ul>
    <li><strong>APIs Core Understanding Learning Exercise 🧠</strong></li>
    <li><strong>From JSON to REST Learning Exercise 🧠</strong></li>
    <li><strong>REST API Clients Learning Exercise 🧠</strong></li>
    <li><strong>Express.JS Core Understanding Learning Exercise 🧠</strong></li>
</ul>

<a name="API"></a>

# APIs Core Understanding

## ¿Qué es una API?

<p align="justify">La API viene siendo como un intermediario entre quien pide los datos y el que los retorna, se puede decir que una API es un servicio Backend que es utilizada para conectar dos aplicaciones, en tal caso una aplicación que interactua con un cliente, las peticiones realizadas por el cliente llegan a la API y procesa toda esa información en la parte trasera que sería un servidor/programa que al final retorna una respuesta (datos, informacion, página, etc.).</p>

## ¿Qué es un protocolo?

<p align="justify">Define la forma/manera en que se traslada/maneja/procesa la información de un aplicación a otra. Siguiendo un conjunto de reglas ya preestablecidas para el manejo de dicha información de forma segura. Pueden existir varios protocolos que coexistan entre si.</p>

## ¿El término API sólo es aplicable a la comunicación de programas a través de Internet?

<p align="justify">El término API como tal que viene siendo <strong>Application Programming Interfaces</strong>, se puede usar localmente para aplicaciones que se comunican dentro de un mismo ambiente o dispositivo. Queriendo esto decir que no es algo exclusivo de la web.</p>

## ¿Por qué es importante la comunicación estructurada entre dos programas?

<p align="justify">Para no cometer errores con el manejo de la información/datos, y el buen uso de buenas practicas para el control de datos. Ademas de tener un conjunto de reglas para las computadoras.</p>

## ¿Los seres humanos utilizamos las API cuando nos comunicamos sin tecnología?

<p align="justify">En algunos casos si, quizá con el ejemplo del restaurante donde se tiene al comensal (cliente), el mesero (API) y la cocina(backend), y el comensal realiza su pedido el mesero lo puede apuntar en una nota, irse a la cocina y dejar la nota puesta en un lugar donde el chef la vea, y realice la orden pedida, y en cuanto este el chef le entregue la orden al mesero y el mesero le entregue la comida al comensal.</p>

## ¿Una API es un programa más o un estándar?

<p align="justify">Una API como tal, se entiende que es un éstandar de como trabajar, ya que existen diversas maneras de manejar la información como SOAP, entre otras. No solo es un programa más ya que contiene un conjunto de reglas para el buen manejo de la informacion de manera segura, dada por los protocolos que maneja.</p>

## ¿Conoces alguna API? ¿Puedes enumerar al menos 5 ejemplos de API?

<ol>
  <li>La API que nos da acceso al DOM en JavaScript</li>
  <li>La API de wordpress</li>
  <li>Las API's que vienen con Java.</li>
  <li>La API pública de pokemon</li>
  <li>La API pública de Rick and Morty</li>
</ol>

Entre otras...

---

### **extras:**

<p align="justify"> La interfaz puede considerarse como un <strong>contrato</strong> de servicio entre dos aplicaciones. Este contrato define cómo se comunican entre sí mediante solicitudes y respuestas.</p>

---


<a name="json-to-rest"></a>

# From JSON to REST 

## ¿Qué es HTTP?

<p align="justify">El significado de HTTP es <strong>Protocolo de transferencia de hipertexto</strong>. Es un conjunto de reglas definidas formalmente para la comunicación entre un cliente (el recurso de red que solicita datos o servicios) y un servidor (el recurso que recibe y responde a la solicitud).</p>

## ¿Qué es JSON?

<p align="justify">Es un formato ligero para almacenar e intercambiar información que cualquier persona pueda entender y leer. Simplemente contienen texto y tienen la extensión <strong>.json</strong>. Su uso principal radica en la transferencia de datos entre un servidor y un cliente. A su vez se debe de seguir la sintaxis correcta:</p>

<ul>
  <li><p align="justify">Las <strong>Keys</strong> deben ser cadenas de caracteres (strings). Como su nombre en español lo indica, estas contienen una secuencia de caracteres rodeados de comillas.</p></li>
  <li><p align="justify">Los <strong>Values</strong> son un tipo de datos JSON válido. Puede tener la forma de un arreglo (array), objeto, cadena (string), booleano, número o nulo.</p></li>
</ul>

## ¿Es JSON lo mismo que un objeto Javascript plano?

<p align="justify">No, no son lo mismo, JSON es un formato de transferencia de datos mientras que JavaScript Object es un objeto literal del lenguaje de JavaScript. Un JSON posee diversas restricciones entre las cuales se tiene:</p>

<ul>
  <li>No puede tener funciones</li>
  <li>No puedo tener comentarios</li>
  <li>Todo el texto siempre tiene comillas dobles</li>
  <li>Las propiedades siempre tienen comillas dobles</li>
</ul>

<p align="justify">Por lo tanto, JSON está más restringido que un objeto JavaScript.</p>

## ¿Qué es REST?

<p align="justify">Es un estilo de arquitectura de software que se utiliza para describir cualquier interfaz entre diferentes sistemas que utiliza HTTP para la comunicación.</p>

<p align="justify">El cliente y el servidor están débilmente acoplados, es decir, el cliente no necesita conocer los detalles de implementación del servidor y el servidor no se preocupa de cómo utiliza el cliente los datos.</p>

<p align="justify">En la arquitectura REST, los clientes envían solicitudes para recuperar o modificar recursos y los servidores envían respuestas a estas solicitudes. Echemos un vistazo a las formas estándar de realizar solicitudes y enviar respuestas.</p>

## ¿Es REST un lenguaje de programación, un marco de trabajo, una tecnología o un patrón de arquitectura?

<p align="justify">Es un patrón de arquitectura, ya que se encuentra en muchos ámbitos de la web, mayormente como <strong>API</strong> para desarrolladores. Sitios web como Amazon, Facebook, o MEGA ofrecen a los desarrolladores estas API's basadas, casi en su totalidad en REST.</p>

## ¿Qué es un recurso en REST?

<p align="justify">Los recursos son URI's para acceder a la manipulación o lectura de nuesta API. Ejemplo: </p>

<p align="center">api.kodoti.com/<strong>users</strong></p>

<ul>
  <li><p align="justify">El <strong>recurso</strong> es el usuario "/users".</p></li>
  <li><p align="justify">La URL completa se conoce como <strong>endpoint</strong>.</p></li>
  <li><p align="justify">De esta manera se expone el recurso usuario para que pueda ser manipulado.</p></li>
</ul>

## ¿Qué es un identificador de recurso?

<p align="justify">El URI (siglas de <i>uniform resource identifier</i>) o identificador uniforme de recursos nos sirve para acceder a un <strong>recurso físico o abstracto por internet</strong>. Dependiendo de la situación, el recurso puede ser de muchos tipos. Los protocolos como HTTP o FTP funcionan gracias a esta sintaxis, ya que la forma de direccionamiento se establece en base a la estructura del URI. De esta manera, el sistema identifica a <strong>qué información debe acceder</strong>, así como <strong>dónde y cómo</strong>.</p>

<p align="justify">Un URI consta de un máximo de cinco partes, de las cuales solo dos son obligatorias:</p>

<ul>
  <li><p align="justify"><strong>scheme (<i>esquema</i>)</strong>: Proporciona información sobre el protocolo utilizado.</p></li>
  <li><p align="justify"><strong>authority (<i>autoridad</i>)</strong>: Identifica el dominio.</p></li>
  <li><p align="justify"><strong>path (<i>ruta</i>)</strong>: Muestra la ruta exacta al recurso.</p></li>
  <li><p align="justify"><strong>query (<i>consulta</i>)</strong>: Representa la acción de consulta.</p></li>
  <li><p align="justify"><strong>fragment (<i>fragmento</i>)</strong>: Designa una parte del recurso principal.</p></li>
</ul>

<p align="justify">Los dos elementos imprescindibles que deben contener todos los identificadores son <i>scheme</i> y <i>path</i>. En la estructura del URI, los componentes se enumeran uno tras otro por este orden y están separados por caracteres estándar.</p>

```code
scheme :// authority path ? query # fragment
```

<br />
<p align="justify">Las dos barras después de los primeros dos puntos solo son necesarias si hay contenido en la parte de <i>authority</i> puede contener información del usuario, que se separa del dominio mediante el signo de @, e incluir una especificación de puerto al final, que se separa a su vez del dominio mediante dos puntos.</p>

<p align="justify">Como ejemplo podemos colocar una dirección web de uso común, como la siguiente: "https://example.org/test/test1?search=test-question#part2"</p>

<ul>
  <li>scheme: https</li>
  <li>authority: example.org</li>
  <li>path: test/test1</li>
  <li>query: search=test-question</li>
  <li>fragment: part2</li>
</ul>

<p align="justify">En el ejemplo, el URI direcciona a una <strong>parte de una página web</strong> (part2), a la que se accede mediante HTTP. Dicha parte se sitúa en un dispositivo con el identificador “example.org” y puede encontrarse siguiendo la ruta indicada si antes se realiza la búsqueda.</p>

## ¿Qué es un método HTTP?

<p align="justify">Un verbo o método HTTP le indica al servidor qué hacer con los datos identificados por la URL. La solicitud puede contener opcionalmente información adicional en su cuerpo, que podría ser necesaria para realizar la operación, por ejemplo, los datos que desea almacenar con el recurso. Entre los más comunes usados:</p>

<table>
  <thead>
    <tr>
      <td><strong>Método HTTP</strong></td>
      <td><strong>Descripción</strong></td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>POST</td>
      <td>Crea un recurso.</td>
    </tr>
    <tr>
      <td>GET</td>
      <td>Recupera un recurso.</td>
    </tr>
    <tr>
      <td>PUT</td>
      <td>Actualiza un recurso existente. No crea el recurso si no existe.</td>
    </tr>
    <tr>
      <td>DELETE</td>
      <td>Suprime un recurso.</td>
    </tr>
  </tbody>
</table>

## ¿Qué métodos HTTP utiliza REST dentro de sus reglas de arquitectura?

<p align="justify">El protocolo HTTp definfe una diversa cantidad de métodos que son utilizados para diferentes circunstacias, se listan los más relevantes y más utilizados en la construcción de servicios REST, los métodos son los siguientes:</p>

<ul>
  <li><p align="justify"><strong>GET:</strong> Es utilizado únicamente para <i>consultar información</i> al servidor, muy parecidos a realizar un <i>SELECT</i> a la base de datos.</p></li>
  <li><p align="justify"><strong>POST:</strong> Es utilizado para solicitar la <i>creación de un nuevo registro</i>, es decir, algo que no existía previamente, es decir, es equivalente a realizar un <i>INSERT</i> en la base de datos.</p></li>
  <li><p align="justify"><strong>PUT:</strong> Se utiliza para <i>actualizar por completo un registro existente</i>, es decir, es parecido a realizar un <i>UPDATE</i> a la base de datos.</p></li>
  <li><p align="justify"><strong>PATCH:</strong> Este método es similar al método <i>PUT</i>, pues permite actualizar un registro existente, sin embargo, este se utiliza cuando <strong>actualizar solo un fragmento del registro</strong> y no en su totalidad, es equivalente a realizar un <i>UPDATE</i> a la base de datos.</p></li>
  <li><p align="justify"><strong>DELETE:</strong> Este método se utiliza para <strong>eliminar un registro existente,</strong> es similar a <i>DELETE</i> a la base de datos.</p></li>
  <li><p align="justify"><strong>HEAD:</strong> Este método se utiliza para <strong>obtener información sobre un determinado recurso</strong> sin retornar el registro. Este método se utiliza a menudo para probar la válidez de los enlaces de hipertexto, la accesibilidad y las modificaciones recientes.</p></li>
</ul>

## ¿Por qué utilizamos métodos HTTP en REST y cómo se relacionan con los recursos?

<p align="justify">Se utilizan los métodos HTTP, ya que contienen un conjunto de reglas bien definido para el traspaso de información de un lugar a otro de forma segura, y se encuentran ligados a los recursos ya que cada uno de los métodos existentes manipulan dichos recursos para poder procesar sus datos de manera correcta, y devolver la información solicitada.</p>

## ¿Es REST lo mismo que HTTP?

<p align="justify">REST no es lo mismo que el protocolo HTTP, ya que REST es un patron de arquitectura, que se utiliza para describir cualquier interfaz entre diferentes sistemas y la comunicación la realiza por medio del protocolo HTTP que es un conjunto de reglas bien definidas para el traspaso de información de un sistema a otro.</p>

# REST API CLIENTS

Se instalo el programa PostMan correctamente.

<p align="justify">Anotaciones del curso de postman.</p>

<p align="justify">La primera request con Postman.</p>

## Postman only works with REST APIs?

<p align="justify">Las aplicaciones det tipo API REST en definitiva solo trabaja con postman.</p>

## Is there an alternative to Postman?

<p align="justify">Si existen varias alternativas a Postman, como Insomnia, Hoppscotch, paw, entre otros.</p>


<!-- ```typescript

``` -->

<!-- <ul>
  <li></li>
</ul> -->
<!-- <img/> -->

<i></i>

<strong></strong>
<p align="justify"></p>
<p align="center"></p>
<br />
