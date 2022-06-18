# Monday 06-06-2022

<ol>
  <li><strong>Check the All You Need To Know About TypeScript video</strong></li>
  <li><strong>Read this Answer, for the following question: "What is TypeScript and why would I use it in place of JavaScript?"</strong></li>
  <li><strong>Check the 5 reasons to use TypeScript video</strong></li>
</ol>

<a name="input"></a>

## the All You Need To Know About TypeScript video viewed 💹

<p align="justify">El uso de Ts es muy importante, que nos trae el uso de tipos, eliminando casi el 90% de los errores que nos podría traer js. Ya que al aceptar cualquier cosa, le podríamos mandar diversos datos que al final no se trabajaran con un tipo de dato en especifíco y generando problemas.</p>

## What is TypeScript and why would I use it in place of JavaScript? 

<p align="justify">Ts es un superset del lenguaje de Js, que posee un solo compilador de código abierto y desarrollado por Microsoft.</p>

<p align="justify">Ts nos ayuda con la detección de errores de manera temprana a través del sistema de tipos que provee el compilador, haciendo que el desarrollo de Js sea mucho más eficiente.</p>

<p align="justify">Ts logra sus objetivos de tres formas:</p>

<ul>
  <li><p align="justify"><strong>Compatibilidad con funciones modernas de Js</strong>: EL lenguaje de Js (no el tiempo de ejecución) se estandariza por medio de ECMAScript, al usar Ts nos permite el uso de diversas características más nuevas, y puede traducirlar a objetivos de ECMAScript más antiguos. Nos asegura la forma de utilizar las funciones lambda, clases, destructuración, etc, con versiones anteriores de navegadores de forma compatible.</p></li>
  <li><p align="justify"><strong>Sistema de tipos avanzado</strong>: Los tipos no forman parte del estándar ECMAScript y seguramente no lo harán nunca debido a la naturaleza interpretada de Js. Ts incluye interfaces, enumeraciones, tipos híbridos, genéricos tipos de Unión/intersección, entre otros.</p></li>
  <li><p align="justify"><strong>Compatibilidad con herramientas de desarrollador</strong>: El compilador de Ts se puede ejecutar en segundo plano, de modo que se pueda navegar, identificar problemas, inspeccionar posibilidades y refactorizar la base de código de forma sencilla.</p></li>
</ul>

### Relación de TypeScript con otros lenguajes de orientación de JavaScript

<p align="justify">Los archivos Ts se compilan en Js legible, casi puede cambiar la extensión de <i>.js</i> a archivos <i>.ts</i>, Ts se basa en los éxitos de Js mientras mejora sus debilidades.</p>

<p align="justify">Por un lado tiene herramientas prepradaas para el futuro que toman los estándares ECMAScript modernos y los compilan en versiones anteriores de Js, siendo Babel la más popular. Por otro lado, tiene lenguajes que difieren totalmente de Js que apuntan a Js. Estos lenguajes aunque podrían ser mejores de lo que podría conducir el futuro de Js, corren un mayor riesgo de no encontrar suficiente adopción al futuro de Js.</p>

<p align="justify">Aquí es donde entra Ts, ya que se encuentra entre estos dos extremos, equilibrando así el riesgo. Se necesita poco esfuerzo para acostumbrarse si esta familiarizado con Js, ya que no es un lenguaje completamente diferente, posee un excelente soporte de interoperabilidad de Js y se ha visto mucha adopción recientemente.</p>

### Opcionalmente tipeo estático e inferencia de tipos

<p align="justify">JavaScript se escribe dinámicamente. Esto significa que JavaScript no sabe de qué tipo es una variable hasta que se crea una instancia en tiempo de ejecución. Esto también significa que puede ser demasiado tarde. TypeScript agrega soporte de tipo a JavaScript y detecta errores de tipo durante la compilación a JavaScript. </p>

<p align="justify">TypeScript hace que escribir sea un poco más fácil y mucho menos explícito mediante el uso de la inferencia de tipos. Por ejemplo: <i>var x = "hello"</i> en TypeScript es lo mismo que <i>var x : string = "hello"</i>. El tipo simplemente se infiere de su uso. Incluso si no escribe explícitamente los tipos, todavía están allí para evitar que haga algo que, de lo contrario, daría como resultado un error en tiempo de ejecución.</p>

<p align="justify">Un estudio a gran escala de lenguajes de programación y calidad del código en Github sugiere que <i>"los lenguajes tipificados estáticamente, en general, son menos propensos a defectos que los tipos dinámicos, y que la tipificación fuerte es mejor que la tipificación débil en el mismo sentido".</i></p>

### Compatibilidad con IDE mejorada

<p align="justify">La experiencia de desarrollo con Ts, es una gran mejora con respecto a Js.</p>

<p align="justify">El compilador de TypeScript informa al IDE en tiempo real sobre su rica información de tipo. Esto da un par de ventajas importantes.</p>

<p align="justify">Existe una amplia gama de IDE que tienen una excelente compatibilidad con TypeScript, como <i>Visual Studio Code, WebStorm, Atom</i> y <i>Sublime</i>.</p>

### Controles nulos estrictos

<p align="justify">Los errores de tiempo de ejecución del formulario <i>cannot read property 'x' of undefined</i> o <i>undefined is not a function</i> son causados ​​muy comúnmente por errores en el código JavaScript. Listo para usar, TypeScript ya reduce la probabilidad de que ocurran este tipo de errores, ya que no se puede usar una variable que el compilador de TypeScript no conozca (con la excepción de las propiedades de las variables<i>any</i> con tipo.</p>

<p align="justify">Con las comprobaciones nulas estrictas habilitadas ( <i>--strictNullChecks</i> indicador del compilador), el compilador de TypeScript no permitirá <i>undefined</i> que se asigne a una variable a menos que declare explícitamente que es de tipo anulable. Por ejemplo, <i>let x : number = undefined</i> dará como resultado un error de compilación. Esto encaja perfectamente con la teoría de tipos ya que <i>undefined</i> no es un número. Se puede definir que <i>x</i> sea un tipo de suma <i>number</i> y <i>undefined</i> corrigiendo esto: <i>let x : number | undefined = undefined.</i></p>

<p align="justify">Una vez que se sabe que un tipo admite valores NULL, lo que significa que es de un tipo que también puede tener el valor <i>null</i> o <i>undefined</i>.</p>

### Compilacion

<p align="justify">Para usar TypeScript, necesita un proceso de compilación para compilar el código JavaScript. El proceso de compilación generalmente toma solo un par de segundos dependiendo, por supuesto, del tamaño de su proyecto. El compilador de TypeScript admite la compilación incremental ( <i> --watch</i> indicador del compilador) para que todos los cambios posteriores se puedan compilar a mayor velocidad.</p>

### Interoperabilidad de JavaScript

<p align="justify">Dado que Ts está tan estrechamente relacionado con JavaScript, tiene excelentes capacidades de interoperabilidad, pero se requiere algo de trabajo adicional para trabajar con bibliotecas de JavaScript en TypeScript. Las definiciones de TypeScript son necesarias para que el compilador de TypeScript comprenda que las llamadas a funciones como <i>_.groupBy</i> o <i>angular.copy</i> o <i>$.fadeOut</i> no son, de hecho, declaraciones ilegales. Las definiciones de estas funciones se colocan en  archivos <i>.d.ts</i>.</p>

<p align="justify"><i>Los módulos de Npm</i>que vienen preempaquetados con sus propias definiciones de tipo son entendidos automáticamente por el compilador de TypeScript. Para prácticamente cualquier otra biblioteca de JavaScript semipopular que no incluya sus propias definiciones, alguien ya ha puesto a disposición definiciones de tipo a través de otro módulo npm. Estos módulos tienen el prefijo "@types/" y provienen de un repositorio de Github llamado <i>DefinitelyTyped</i>.</p>

<p align="justify"><strong>Hay una advertencia:</strong> las definiciones de tipo deben coincidir con la versión de la biblioteca que está utilizando en tiempo de ejecución. Si no lo hacen, TypeScript podría impedirle llamar a una función o quitar la referencia a una variable que existe o permitirle llamar a una función o quitar la referencia a una variable que no existe, simplemente porque los tipos no coinciden con el tiempo de ejecución en tiempo de compilación. . Así que asegúrese de cargar la versión correcta de las definiciones de tipo para la versión correcta de la biblioteca que está utilizando.</p>

### Convertir de JavaScript a TypeScript

<p align="justify">Se puede cambiar el nombre de cualquier archivo <i>.js</i> a un archivo <i>.ts</i> y ejecutarlo  a través del compilador de TypeScript para obtener sintácticamente el mismo código JavaScript como salida (si era sintácticamente correcto en primer lugar). Incluso cuando el compilador de TypeScript obtiene errores de compilación, seguirá generando un archivo <i>.js</i></p>

<p align="justify">Incluso puede aceptar archivos <i>.js</i> como entrada con la bandera <i> --allowJs</i>. Esto permite comenzar con Ts de inmediato Desafortunadamente, es probable que ocurran errores de compilación al principio. Uno debe recordar que estos no son errores que detengan el espectáculo como los que puede estar acostumbrado con otros compiladores.</p>

<p align="justify">El mayor obstáculo es la curva de aprendizaje. Te animo a que juegues con un proyecto pequeño al principio. Mire cómo funciona, cómo se construye, qué archivos usa, cómo está configurado, cómo funciona en su IDE, cómo está estructurado, qué herramientas usa, etc. Convertir una gran base de código JavaScript a TypeScript es factible cuando sabe qué estás haciendo. Lea este blog, por ejemplo, sobre <a href="https://www.lucidchart.com/techblog/2017/11/16/converting-600k-lines-to-typescript-in-72-hours/">cómo convertir 600k líneas a mecanografiado en 72 horas</a>, solo asegúrese de tener un buen conocimiento del idioma antes de dar el salto.</p>

### Adopción

<p align="justify">TypeScript es de código abierto (con licencia de Apache 2, consulte GitHub ) y está respaldado por Microsoft. Anders Hejlsberg , el arquitecto principal de C#, encabeza el proyecto. Es un proyecto muy activo; el equipo de TypeScript ha estado lanzando muchas funciones nuevas en los últimos años y aún se planean muchas otras excelentes (consulte la hoja de ruta ).</p>

<p align="justify">En resumen, Ts es muy potente al tener el tipado de datos, funciones, etc. Brindando el uso de interfaces, tipos, uniones, interescciones entre otros. Con facilidad de aprendizaje si la persona/programador, se encuentra familiarizado con Js.Otra ventaja que nos brinda es nuevamente no cometer errores, ya que al ser tipado, se tiene que inferir el dato o decirle explicitamente que tipo de dato será. Puede mezclarse con gran cantidad de tecnologías como Angular, React, entre otras, y además de tener soporte en vs code, sublimetext, entre otros más.</p>

### 5 reasons to use TypeScript

<ul>
  <li>Type safety</li>
  <li>Classes, interfaces, and inheritance</li>
  <li>IDE experience</li>
  <li>Future proof</li>
  <li>Grow as you go</li>
</ul>
