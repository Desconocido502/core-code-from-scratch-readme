# Wednesday 15-06-2022

<ul>
    <li><strong>Node.JS Core Understanding Learning Exercise 馃</strong></li>
    <li><strong>Node.JS Module System Core Understanding Learning Exercise 馃</strong></li>
    <li><strong>Node.JS Module System Practice 馃捇</strong></li>
    <li><strong>Client-Server Model Learning Exercise 馃</strong></li>
</ul>

<a name="Nodejs-Understand"></a>

## Node.js Core

<p align="justify">Understanding well what Node.JS is before starting to use it, will make it much easier for us to work with this powerful tool. In this exercise your task is to answer the following questions in your own words:</p>

<ol>
    <li>
        <h3>驴Qu茅 es Node.js?</h3>
        <p align="justify">Es un entorno de ejecuci贸n para JavaScript fuera de los navegadores, en esencia Node es un programa que incluye el motor de JavaScript V8, adem谩s de m贸dulos adicionales que no se encuentran disponibles en el navegador. Chrome y Node comparten el mismo motor de ejecuci贸n de Javascript(v8), pero proveen un entorno de ejecuci贸n distinta. </p>
        <br />
        <p align="center">
            <img src="../img/nodeJS.png" alt="Node.js" width="350px"/>
        </p>
        <br/>
    </li>
    <li>
        <h3>驴Qu茅 problema resuelve Node.js?</h3>
        <p align="justify">Proporcionar una manera f谩cil para construir programas de red escalables, y a que se refiere con esto, bueno antes JavaScript, era un lenguaje de programaci贸n exclusivo para el lado del cliente y que solo estaba presente en los navegadores, pero apareci贸 Node que nos brinda una 煤nica herramienta de trabajo en este caso un solo hilo de ejecuci贸n (Thread), y con este 煤nico hilo de ejecuci贸n se pueden trabajar varias tareas al mismo tiempo. Ya que cambiando la forma en que se realiza una conexi贸n (solicitud) con el servidor. Como bien deciamos en vez de generar un nuevo thread para cada solicitud, cada solicitud dispara una ejecuci贸n de evento (evento o subproceso) dentro del motor de Node. Todos estos eventos de ejecuci贸n se van almacenando en una cola y van siendo atendidas de forma asincrona. Impidiendo que se quede en un punto muerto, y que puede soportar decenas de miles de conexiones/solicitudes de forma concurrente.</p>
        <br />
    </li>
    <li>
        <h3>驴Qu茅 es el motor V8 de Javascript?</h3>
        <p align="justify">Es un programa que convierte c贸digo de JavaScript en c贸digo que el CPU puede entender y lo ejecuta. El c贸digo de m谩quina es un c贸digo de nivel m谩s bajo que la computadora puede ejecutar sin necesidad de interpretarlo primero, ignorando la compilaci贸n y por lo tanto aumentando su velocidad. Creado por Google es ultra-r谩pido escrito en C++, adem谩s de que es c贸digo Open Source, esto significando que lo puede descargar y utilizar en cualquier aplicaci贸n que se desee utilizar.</p>
        <br/>
    </li>
    <li>
        <h3>驴Es realmente necesario Node.js en el ecosistema de desarrollo?</h3>
        <p align="justify">Si es necesario ya que nos deja crear proyectos escalables, ya que Node.js trabaja fuera de los navegadores y nos da mas ventajas trabajar de esta manera.</p>
        <br/>
    </li>
    <li>
        <h3>驴Cu谩l es la diferencia entre Node.js y cualquier otro navegador?</h3>
        <p align="justify">La principal diferencia es que Node.js se puede ejecutar fuera de cualquier navegador, ya que este cuenta con el motor V8, que simplemente interpreta el c贸digo, y adem谩s de eso provee m贸dulos que los interpretes de cualquier otro navegador no puede utilizar, como ejemplo procesos de E/S del disco de la computadora.</p>
        <br/>
    </li>
    <li>
        <h3>驴Qu茅 es NVM y por qu茅 es 煤til para los desarrolladores de Node.js?</h3>
        <p align="justify">(Node version manager). Es una aplicaci贸n que nos permite tener y gestionar varias versiones de Node.js en el mismo sistema, permitiendo as铆, instalar, administrar, y cambiar las diferentes versiones de Node.js de manera f谩cil y r谩pida. Esto es 煤til para los desarrolladores ya que dependiendo del proyecto que est茅n trabajando puede acoplarse a una cierta versi贸n de Node.js o en tal caso actualizar su versi贸n.</p>
        <br/>
    </li>
</ol>

<a name="Nodejs-module-Understand"></a>

## Node.js Module System

<ol>
    <li>
        <h3>驴Qu茅 es un M贸dulo Javascript?</h3>
        <p align="justify">Es un archivo que puede contener una clase o una biblioteca de funciones para un prop贸sito en espec铆fico. Esto se creo debido al crecimiento de las aplicaciones, as铆 dividiendo ciertos bloques de c贸digo en m煤ltiples archivos. Los m贸dulos pueden cargarse entre s铆 y usar directivas especiales como <i>export</i> e <i>import</i> para intercambiar funcionalidad, llamar a funcines de un m贸dulo de otro.</p>
        <ul>
            <li><p align="justify">La palabra clave <i>export</i> etiqueta las variables y funciones que deber铆an  ser accesibles desde fuera del m贸dulo actual.</p></li>
            <li><p align="justify"><i>import</i> permite importar funcionalidades desde otros m贸dulos.</p></li>
            <li><p align="justify">El atributo &lt;script type="module"&gt; se usa para indicar cu谩ndo se apunta a un m贸dulo.</li>
        </ul>
        <br />
    </li>
    <li>
        <h3>驴Por qu茅 son necesarios los m贸dulos de Javascript?</h3>
        <p align="justify">Son necesarios los m贸dulos ya que cuando la aplicaci贸n/proyecto se vuelve muy grande, de forma preferencial, se opta por colocar clases, librer铆as/bibliotecas de funciones dentro de un m贸dulo, esto con el fin de mantener un orden y de solo exportar e importar el c贸digo necesario para el proyecto.</p>
    </li>
    <li>
        <h3>驴Qu茅 est谩ndares de m贸dulos est谩n disponibles en Node.JS?</h3>
        <p align="justify">Entre los est谩ndares de m贸dulos para Node.js se tiene: CommonJS, y UMD </p>
    </li>
    <li>
        <h3>驴Cu谩les son las diferencias entre los m贸dulos ESModules y los m贸dulos CommonJS?</h3>
        <p align="justify">En ecosistemas donde predomina la utilizaci贸n de NodeJS, es m谩s frecuente usar CommonJS, mientras que en sistemas m谩s modernos, como el navegador o Deno, es m谩s habitual utilizar el ESModules.</p>
        <br />
    </li>
    <li>
        <h3>驴Qu茅 tipos de m贸dulos existen en Node.JS?</h3>
        <p align="justify">Hay 3 tipos de m贸dulos. Todos funcionan de una manera similar pero difieren en el origen.</p>
        <ul>
            <li><p align="justify"><strong>Built-in modules:</strong> Son los m贸dulos nativos de la API de Node.js. No hace falta que se instalen, ya que vienen incluidos por defecto con Node.js</p></li>
            <li><p align="justify"><strong>Local modules:</strong> Son los m贸dulos escritos por los desarrolladores y forman en su conjunto gran parte de la aplicaci贸n, se estructuran as铆 con la finalidad de poder ser un c贸digo reutilizable.</p></li>
            <li><p align="justify"><strong>External modules:</strong> Son en esencia, los paquetes de terceros distribuidos a trav茅s de npm (aunque pueden provenir de otros repositorios). Estos paquetes se instalan como dependencias y, aunque aportan funcionalidad a la aplicaci贸n, no deben incluirse en el repositorio ya que no son parte de la misma.</p></li>
        </ul>
    </li>
</ol>

<a name="CSM"></a>

## Client-Server Model 

<ol>
  <li><strong>驴Qu茅 es un servidor?</strong><p align="justify">Es una m谩quina robusta tanto en hardware como en software, y act煤a como un sistema gestor de datos o aplicaciones. Es el encargado de procesar las solicitudes de los clientes y dando respuestas a los clientes.</p></li>
  <li><strong>驴Qu茅 es un Cliente?</strong><p align="justify">Es un demandante de servicio, el cliente puede ser un ordenador, como tambi茅n una aplicaci贸n, la cual requiere informaci贸n de la red para poder funcionar.</p></li>
  <li><strong>驴Es un servidor un ordenador f铆sico m谩s?</strong><p align="justify">En primera instancia si, si lo es, pero hay dos tipos de servidores, los servidores fis铆cos y los virtuales. El f铆sico se trata de un hardware conocido como <i>host</i> es una m谩quina integrada a una red de nodos basados en software. Mientras que los servidores virtuales <i>(VPS, Virtual Private Server)</i> son softwares que proporcionan servicios a otros programas(clientes).</p></li>
  <li><strong>驴Hay alguna similitud entre la comunicaci贸n humana y el modelo cliente-servidor?</strong><p align="justify"></p></li>
  <li><strong>驴Es el modelo cliente-servidor aplicable s贸lo a la Web?</strong><p align="justify"></p></li>
</ol>

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
