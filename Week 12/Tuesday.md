# Tuesday 28-06-2022

<ul>
  <li><strong>Work on my project 馃</strong></li>
</ul>

<p align="justify">Bien, se estuvo explicando la parte del backend de como hacer cada uno de los endpoints, ahora nos enfocaremos en unir los dos proyectos, la parte del backend y la parte del frontend. Para empezar crearemos una carpeta raiz, y se le da el nombre que gusten, en mi caso <i>finalProject</i>, en dicha carpeta se ingresar谩n los dos proyectos a trabajar quedando de la siguiente manera:</p>

<p align="center"><img src="../img/final_project_carpetas.png" alt="distribuci贸n de carpetas"/></p>

<p align="justify">Bien, como se mencion贸 antes, se trabajar谩 con el <strong>puerto 5000</strong>, para el <strong>backend</strong>, y el <strong>puerto 3000</strong>, para el <strong>frontend</strong>, ya que se est谩 trabajando con react, react normalmente trabaja con los puertos <i>3000</i>. Para poder trabajar los dos proyectos como uno solo, es la raz贸n del por que se realiz贸 la uni贸n de los dos proyectos en una sola carpeta. Ahora se preguntar谩n como haremos para ir probando ambos, y es sencillo vs code, nos permite abrir una n cantidad de consolas en su editor, por lo que tendremos una consola para la parte del backend y otra para la parte del frontend, a continuaci贸n se muestra un ejemplo:</p>

<p align="center"><img src="../img/consolas.png" alt="consolas del backend y frontend"/></p>

<p align="justify">Cabe recalcar que al estar en la carpeta raiz, debemos de colocar en cada consola la ruta correcta para el backend y el frontend para iniciar cada uno de los servidores sin problema.</p>

<p align="justify">Para comprobar que los servidores estan funcionando correctamente se puede realizar una prueba, en el caso del backend con postman, y el en frontend con que cargue la p谩gina base estaremos bien.</p>

<p align="justify">Ahora lo que toca realizar es la debida conexi贸n del backend con el frontend. La parte del backend ya se encuentra lista, 煤nicamente hay que realizar la uni贸n por el lado del frontend, esto lo haremos por medio de la libreria <strong><a href="https://github.com/axios/axios">axios</a></strong>, la cual nos permite realizar peticiones a un servidor, en este caso el servidor ser谩 el backend que creamos anteriormente.</p>

<p align="justify">Nos concentraremos en la carpeta de <i>components</i>, que son los componentes necesarios para mostrar la informaci贸n, a continuaci贸n se muestra la carpeta components:</p>

<p align="center"><img src="../img/components.png" alt="componentes a trabajar"/></p>

<p align="justify">Poseemos 3 archivos los cuales representan una etiqueta creada por "<i>nosotros</i>", para la interacci贸n del usuario con la lista de To-Do's y el resto de operaciones.</p>

<p align="justify">Lo primero que realizaremos es ir al archivo <i>Todo.js</i>, ya que realizaremos algunos cambios. El primer cambio se realiza alrededor de la linea 37, aqui cambiaremos el nombre de la variable de la tarea comletada <code>className={todo.isComplete ? "todo-row complete" : "todo-row"}</code> a el nombre de la variable <strong>is_done</strong>, <code>className={todo.is_done === 1 ? "todo-row complete" : "todo-row"}</code>, se realiza este cambio ya que todo antes se trabajaba y se operaba desde el frontend, pero al tener una API, para realizar las peticiones del frontend es necesario realizar los cambios debidos para el buen funcionamiento de la aplicaci贸n.</p>

<p align="center"><img src="../img/first_change.png" alt="primer cambio"/></p>

<p align="justify">El segundo cambio a realizar es agregar la propiedad is_done, nuevamente ya que es necesario para que las funciones adecuadas, reconozcan que la tarea ha sido completada o no, o  simplemente mostrar si fue completada o no.</p>

<p align="center"><img src="../img/second_change.png" alt="segundo cambio"/></p>

<p align="justify">El tercer cambio fue alrededor de la linea 65, ya que como se menciono antes, todo se trabajaba en la parte del frontend, es por eso que tiene colocado text, y el cambio fue pasado a la propiedad title, adem谩s cabe agregar que cuando la persona agregaba una nueva tarea el titulo de la tarea no era visible, por lo tanto al solucionar este problema, el nombre de la tarea ya era visible.</p>

<p align="center"><img src="../img/third_change.png" alt="tercer cambio"/></p>

<p align="justify">Para este archivo ser铆an los 煤nicos cambios a trabajar, ahora nos enfocaremos en el m贸dulo de <i>TodoList</i>, en este archivo, utilizaremos la librer铆a de axios.</p>

<p align="justify">Como se mencion贸 antes, todo se trabajaba y almacenaba en el frontend, ahora con la API incluida podemos almacenar la informaci贸n en otro lugar y solicitarla para poder realizar las acciones necesarias con dicha informaci贸n. Pero antes de avanzar m谩s, se utilizar谩 una libreria que "creamos", para que sea m谩s sencillo el uso de la informaci贸n y no estar escribiendo el mismo c贸digo varias veces. Para esto tambi茅n es necesario exportar cada una de las funciones que llegaremos a utilizar.</p>

<p align="justify">En este caso se creo la carpeta lib, y en ella se encuentra el archivo llamado API.js, el cual nos proporcionar谩 funciones que pueden ser llamadas las veces que sean necesarias sin repetir una y otra vez el c贸digo en toda la aplicaci贸n, a continuaci贸n se presenta la carpeta y el archivo: </p>

<p align="center"><img src="../img/lib.png" alt="archivo y carpeta"/></p>

<p align="justify">Mostraremos el c贸digo utilizado con una explicaci贸n de su uso:</p>

<p align="center"><img src="../img/api.png" alt="api"/></p>

<p align="justify">Bien, lo primero que tenemos que hacer es importar la libreria de axios, ya que es necesaria para realizar las peticiones al servidor, se tienen dos funciones asincronas en dicho archivo, una para obtener todos los To-Do's, y otro para actualizar los datos de un To-Do</p>

### getTodos

<p align="justify">Lo primero que se hace es colocar un try-catch dentro de esta funci贸n ya que al ser as铆crona, nos puede llegar a ocurrir un error. En la parte del catch simplemente se retorna un arreglo vacio, para indicar a otra funci贸n que deber谩 mostrar un error, y en caso de que no exista un error se obtienen los todos, se almacenan en un objeto y se retornan para su posterior procesamiento.</p>

```javascript

export async function getTodos() {
  try {
    const {
      data: { todos },
    } = await axios.get("http://localhost:5000/api/v1/to-dos");
    return todos;
  } catch (_error) {
    return [];
  }
}


``` 

<p align="justify">Usamos una de la peticiones que nos ofrece axios, en este caso es <i>get</i>, al cual debemos pasarle la url donde se realizar谩 la petici贸n. quedando de la siguiente manera:</p>

```javascript

axios.get("http://localhost:5000/api/v1/to-dos");
``` 


### updateTodoData

<p align="justify">Como se mencion贸 antes esta funci贸n sirve para actualizar los datos de un To-Do, por medio de su ID, por tanto simplemente manda los datos por medio del cuerpo de la petici贸n para actualizar la tarea, en caso de que ocurra un error, lanzar谩 el error provocado, y recordando que se usa try-catch, ya que tambi茅n es as铆crona. Quedando de la siguienta manera:</p>

```javascript

export async function updateTodoData(todoId, todoData) {
  try {
    //*console.log("HERE", todoData);
    await axios.patch(`http://localhost:5000/api/v1/to-dos/${todoId}`, {
      ...todoData
    });
  } catch ({ response }) {
    console.log(response);
    throw new Error(response.data.message);
  }
}
``` 

<p align="justify">Como se puede observar ahora utilizamos otra solicitud que nos brinda axios, la cual es <strong>patch</strong>, la cual nos ayudar谩 a actualizar uno o varios datos de una tarea por medio del ID de la tarea. La informaci贸n a actualizar viaja por medio de la solicitud de la petici贸n realizada.</p>

<p align="justify">Seguiremos avanzando mas adelante con el resto.</p>


<a href="../README.md">Inicio</a>