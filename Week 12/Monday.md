# Monday 27-06-2022

<ul>
  <li><strong>Work on my project 🧠</strong></li>
</ul>

<p align="justify">Bien, ya vimos algunas de las explicaciones para poder realizar consultas en SQLITE, ahora entraremos de fondo con cada uno de los endpoints a trabajar.</p>

## Obtener todos los To-Do's

<p align="justify">Como buena práctica para la creación de end-points, se recomienda estandarizar el nombre de la ruta, y que sea singular. También trabajaremos de manera asincrona, ya que el usuario puede hacer la petición en cualquier momento, y habrá que dejarlo interactuar con algo más mientras llega su respuesta. Lo primero que haremos dentro de la función es traer el controlador de la BD. Una vez lo tengamos obtenemos todos los to-do's de la BD.</p>

<p align="justify">Una vez ya se tengan los to-do's, se cierra el controlador de la BD. En caso de que la BD se encuentre vacía, retornará un error, de lo contrario, simplemente retorna los to-do's, además si ocurre algún problema al intentar obtener los to-do's, enviará un mensaje indicado cual es el error. Quedando asi, el siguiente código:</p>

```javascript
//*Obtener todos los Todo's de la tabla
RequestHandler.get("/to-dos", async (req, res) => {
  try {
    const dbHandler = await getDBHandler();
    const todos = await dbHandler.all("SELECT * FROM todos");

    dbHandler.close(); //*Cierro la conexion de la BD
    if (todos.length === 0) {
      //*En el caso de que el arreglo de los To Dos este vacio:
      //*Si todos es undefined o si existe y es un arreglo pero su longitud es 0
      res.status(404).send({ message: "To Dos Not Found" }).end();
    } else {
      res.send({ todos });
    }
  } catch (error) {
    res.status(500).send({
      error: "Something went wrong when trying to get to dos list",
      errorInfo: error.message,
    });
  }
});
```

## Crear un To-Do de la BD

<p align="justify">Dicha función será también asincrona, y como crearemos un todo de la BD, necesitamos obtener la información que nos ayudará a crear dicho to-do para ingresarlo a la BD. Dicha información se encuentra almacenada en el cuerpo de la petición, obtenemos cada una de los atributos por medio de la destructuración. Obtenemos el manejador de la BD, e insertamos los datos obtenidos anteriormente a la tabla. Al final se cierra el manejador de la BD y se retorna la información del to-do creado. En caso de que exista un error al intentar crear un nuevo to-do, se retornará un mensaje, quedando así el siguiente código:</p>

```javascript
//*CREAR un TODO de la tabla de Todo's
RequestHandler.post("/to-dos", async (req, res) => {
  try {
    const { title, description, isDone: is_done } = req.body;

    const dbHandler = await getDBHandler();

    const newTodo = await dbHandler.run(`
        INSERT INTO todos (title, description, is_done)
        VALUES (
            '${title}',
            '${description}',
            ${is_done}
        )
    `); //* Se insertan los datos a la BD

    await dbHandler.close(); //* Se cierra el controlador de la BD
    //console.log(newTodo);
    res.send({ newTodo: { title, description, is_done, ...newTodo } });
  } catch (error) {
    res.status(500).send({
      error: `Something went wrong when trying to create a new to do:`,
      errorInfo: error.message,
    });
  }
});
```

## Actualizar un To-Do de la BD por medio del id

<p align="justify">Vamos a actualizar un to-do de la BD por medio del id que se le agregue a la petición, esta función también será asincrona. Lo primero que haremos es obtener el id de la url, y esto se hace por medio de los parametros que tiene la url de la petición, en caso de que no sea un id, o un valor que no represente a un id, se retornará un error.</p>

<p align="justify">En caso contrario, se obtiene le manejador de la BD, obtenemos nuevamente los datos a actualizar del cuerpo de la petición y actualizamos el to-do por medio de su id, también si observamos un poco antes obtenemos el to-do que vamos a actualizar, esto se debe a que a veces el usuario no actualiza todas las propiedades, por lo tanto, al momento de actualizar el to-do, lo que hacemos es mandarle tanto las propiedades que tenia el usuario antes de actualizar junto con las nuevas propiedades a actualizar, y se manda una o la otra dependiendo de si la información que mando el usuario realmente es nueva, en caso contrario simplemente se ingresa la información que ya se tenía, en caso de que exista un error al intentar actualizar un to-do, se reportará un error, de lo contrario se mostrará el to-do actualizado, quedando asi el siguiente código:</p>

```javascript
//*Actualizar un TODO de la tabla de Todo's por medio del id
RequestHandler.patch("/to-dos/:id", async (req, res) => {
  try {
    const todoId = req.params.id;

    if (!todoId) {
      res.status(400).send({ error: `A todo id was expected, got ${todoId}` });
    }

    const dbHandler = await getDBHandler();
    const { title, description, isDone: is_done } = req.body;

    const todoToUpdate = await dbHandler.get(
      "SELECT * FROM todos WHERE id = ?",
      todoId
    );

    const updateTodo = await dbHandler.run(
      "UPDATE todos SET title = ? , description = ? , is_done = ? WHERE id = ?",
      title || todoToUpdate.title,
      description || todoToUpdate.description,
      is_done !== undefined ? is_done : todoToUpdate.is_done,
      todoId
    );

    /*
    const updateTodo = await dbHandler.get(
      "SELECT * FROM todos WHERE id = ?",
      todoId
    );
    */

    await dbHandler.close();

    res.status(200).send({ updateTodo });
  } catch (error) {
    res.status(500).send({
      error: "Something went wrong when trying to update a the to do",
      errorInfo: error.message,
    });
  }
});
```

## Eliminar un To-Do de la BD por medio del id

<p align="justify">Nuevamente está función también será asíncrona, y de nuevo obtendremos el id del to-do a actualizar por medio de la url de la petición, luego si el id del to-do a actualizar no es un valor númerico, retornará un error, en caso contrario obtendremos el manejador de la BD, y eliminaremos el to-do dela BD por medio de su ID, cerrando el manejador de la BD y respondiendo con el to-do eliminado de la BD. En caso de que exista un problema al intentar eliminar el todo de la BD, se retornará un error mostrando posiblemente cual es el problema., quedando así el siguiente código:</p>

```javascript

//*Eliminar un TODO de la tabla de Todo's por medio del id
RequestHandler.delete("/to-dos/:id", async (req, res) => {
  try {
    const todoId = req.params.id;

    if (!todoId) {
      res.status(400).send({ error: `A todo id was expected, got ${todoId}` });
    }

    const dbHandler = await getDBHandler();

    const deletedTodo = await dbHandler.run(
      "DELETE FROM todos WHERE id = ?",
      todoId
    );

    await dbHandler.close();

    res.send({ todoRemoved: { ...deletedTodo } });
  } catch (error) {
    console.log("HERE");
    response.status(500).send({
      error: `Something went wrong when trying to delete a to do:`,
      errorInfo: error.message,
    });
  }
});

```

<p align="justify">Terminado asi con cada una de las peticiones que se le realizarán a la API, además cabe agregar que todas estas peticiones se encuentran al macenadas en el archivo manejador de rutas, por tanto al final de todo se debe exportar el manejador de rutas, para que las rutas de la API, funcionen de manera correcta.</p>

<a href="../README.md">Inicio</a>

