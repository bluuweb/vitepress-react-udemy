# Introducción

## Objetivos

-   ¿Qué es React?
-   create-react-app / vite.js
-   JSX
-   Introducción a componentes
-   Introducción a Hooks

## Recursos

-   [es.reactjs.org](https://es.reactjs.org/)
-   [beta.reactjs](https://beta.reactjs.org/learn)
-   [vitejs](https://vitejs.dev/)
-   [getting-started](https://es.reactjs.org/docs/getting-started.html)
-   [tutorial](https://es.reactjs.org/tutorial/tutorial.html)
-   [create-react-app](https://create-react-app.dev/)
-   [getting-started-with-react](https://www.taniarascia.com/getting-started-with-react/)

## ¿Qué es React?
-   React es una biblioteca Javascript para crear interfaces de usuario.
-   React no es un framework (a diferencia de Angular o Vue, que tienen más opiniones).
-   React es un proyecto de código abierto creado por Facebook.
-   Está basado en componentes.

:::tip [getting-started-with-react](https://www.taniarascia.com/getting-started-with-react/)
Uno de los aspectos más importantes de React es el hecho de que puede crear componentes, que son como elementos HTML personalizados y reutilizables, para construir interfaces de usuario de manera rápida y eficiente. React también agiliza la forma en que se almacenan y manejan los datos, utilizando el estado y los accesorios.
:::

## Requisitos

-   [node js](https://nodejs.org/es/): es un entorno en tiempo de ejecución multiplataforma, de código abierto, para la capa del servidor (pero no limitándose a ello) basado en el lenguaje de programación JavaScript.
-   [npm](https://www.npmjs.com/): NPM (Node Package Manager) es un gestor de paquetes desarrollado en su totalidad bajo el lenguaje JavaScript por Isaac Schlueter, a través del cual podemos obtener cualquier librería con tan solo una sencilla línea de código, lo cual nos permitirá agregar dependencias de forma simple, distribuir paquetes y administrar eficazmente tanto los módulos como el proyecto a desarrollar en general. [fuente](https://openwebinars.net/blog/que-es-node-package-manager/)

:::tip ¿Qué es un módulo?

-   Un módulo no es nada más que una unidad de código organizado en archivos o directorios, la cual puede ser exportada con facilidad para poder reutilizarse en otras partes de la aplicación. [fuente](https://alvaroperdiz.com/javascript/node-js/sistema-modulos/)
-   External modules: Son, en esencia, los paquetes de terceros distribuidos a través de npm (aunque pueden provenir de otros repositorios). Estos paquetes se instalan como dependencias y, aunque aportan funcionalidad a la aplicación, no deben incluirse en el repositorio ya que no son parte de la misma.

:::

## Instalación
- Vite.js
- CRA create react app

## Vite

-   [Vite web oficial](https://vitejs.dev/): Vite se define como una herramienta de frontend que te ayudará a crear proyectos (sin atarte a ningún framework concreto) y que su desarrollo y construcción final sea lo más sencilla posible.
-   Está desarrollada por Evan You, el creador de Vue.
-   Actualmente, Vite soporta tanto proyectos vanilla (sin utilizar frameworks), como proyectos utilizando Vue, React, Preact o Lit-element (tanto en versión Javascript, como Typescript). [Fuente](https://lenguajejs.com/automatizadores/vite/guia-tutorial-inicial-de-vite/)
-   [Templates](https://github.com/vitejs/awesome-vite#templates)
-   [Comunidad DEV](https://dev.to/t/vite)

```sh
npm create vite@latest
```

## create-react-app

-   [create-react-app](https://create-react-app.dev/) Afortunadamente, Facebook ha creado la aplicación Create React App, un entorno que viene preconfigurado con todo lo necesario para crear una aplicación React.
-   Creará un servidor de desarrollo en vivo.
-   No es necesario instalar ni configurar herramientas como webpack o Babel. Están preconfigurados y ocultos para que pueda concentrarse en el código.
-   Ventaja: enfocarse en el código, no en las herramientas de compilación.

```
npx create-react-app my-app
cd my-app
npm start
```

:::tip npx

-   Npx es una herramienta de cli que nos permite ejecutar paquetes de npm, los busca en su servidor y lo ejecuta en nuestra máquina.
-   Si usas npx no tienes que instalar paquetes de forma global.
-   Busca siempre la última versión.

:::

:::warning
Si ha instalado previamente `create-react-app globalmente` a través de: `npm install -g create-react-app`, le recomendamos que desinstale el paquete usando `npm uninstall -g create-react-app` o `yarn global remove create-react-app` para asegurarse de que `npx` siempre usa la última versión.
:::

## CRA vs Vite
- Vite y CRA no son tan diferentes como podría pensar. Básicamente, hacen más o menos lo mismo, que es servir a un servidor de desarrollo local y agrupar códigos para la producción. 
- La principal diferencia que notará es cómo se sirve el código en el desarrollo y qué módulos son compatibles.
- Vite no necesita agrupar la aplicación completa o transpilar los módulos y el código antes de iniciar un servidor de desarrollo; la transpilación se realiza bajo demanda, lo que la hace significativamente más rápida que CRA.
- [Sigue estudiando aquí](https://blog.logrocket.com/vite-3-vs-create-react-app-comparison-migration-guide/)


## JSX: JavaScript + XML
-   Como ha visto, hemos estado usando lo que parece HTML en nuestro código React, pero no es HTML del todo. Esto es JSX , que significa JavaScript XML.
-   El uso de JSX no es obligatorio para escribir React.
-   Debajo del capó, se está ejecutando `createElement`, lo que toma la etiqueta, las propiedades y los elementos secundarios del componente y muestra la misma información.
-   JSX está más cerca de JavaScript, no de HTML, por lo que hay algunas diferencias clave a tener en cuenta al escribirlo.
    -   `className` se usa en lugar de `class` para agregar clases CSS, ya que `class` es una palabra clave reservada en JavaScript.
    -   Las propiedades y métodos en JSX son camelCase.
    -   Las etiquetas de cierre automático deben terminar en una barra inclinada,  <br /> Ej. `<img />`
    - Su componente tampoco puede devolver varias etiquetas JSX. Tienes que envolverlos en un padre compartido, como un envoltorio ``<div>...</div>`` vacío o: ``<>...</>``

Las expresiones de JavaScript también se pueden incrustar dentro de JSX usando llaves, incluidas variables, funciones y propiedades.

```jsx
const App = () => {
    const title = "Mi primero proyecto con React.js";
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
        </div>
    );
};

export default App;
```

```jsx
const App = () => {
    const title = "Mi primero proyecto con React.js";
    const classColors = {
        primary: "text-primary",
        info: "text-info",
    };
    return (
        <div className="container">
            <h1 className={classColors.primary}>{title}</h1>
            <p className={classColors.info}>Lorem ipsum dolor sit.</p>
        </div>
    );
};

export default App;
```

## Componentes
- Las aplicaciones React están hechas de componentes . 
- Un componente es una parte de la IU (interfaz de usuario) que tiene su propia lógica y apariencia.
- Un componente puede ser tan pequeño como un botón o tan grande como una página entera.
- Los componentes de React son funciones de JavaScript:

```jsx
const MyButton = () => {
    return <button>i'am a button</button>;
};

const App = () => {
    const title = "Mi primero proyecto con React.js";
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
        </div>
    );
};

export default App;
```

:::warning componentes siempre en Mayúsculas
Fíjate que ``<MyButton />`` empieza con mayúscula. **Así es como sabes que es un componente React.** Los nombres de los componentes de React siempre deben comenzar con una letra mayúscula, mientras que las etiquetas HTML deben estar en minúsculas.
:::

## Renderizado condicional

-   [condicional](https://es.reactjs.org/docs/conditional-rendering.html): En React, puedes crear distintos componentes que encapsulan el comportamiento que necesitas. Entonces, puedes renderizar solamente algunos de ellos, dependiendo del estado de tu aplicación.

```jsx
const MyButton = () => {
    return <button>i'am a button</button>;
};

const UserMessage = () => {
    return <h2>Bienvenido usuario</h2>;
};

const App = () => {
    const title = "Mi primero proyecto con React.js";
    const user = true;
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
            {user ? <UserMessage /> : "Offline"}
        </div>
    );
};

export default App;
```

:::tip ¿Qué pasa si omitimos 'else'?
- Podemos utilizar el operador lógico AND (&&)
- Este operador lógico compara dos expresiones. 
- Si la primera se evalúa como "true", la sentencia devolverá el valor de la segunda expresión.
- Si la primera expresión se evalúa como "false", la sentencia devolverá el valor de la primera expresión, en nuestro caso false.

```jsx
{user && <UserMessage />}
```
:::

## Listas y keys

-   [listas](https://es.reactjs.org/docs/lists-and-keys.html)

```jsx
const App = () => {
    const fruts = ["🍐", "🍌", "🍎"];
    return (
        <div className="container">
            <ul>
                {fruts.map((frut, index) => {
                    return <li key={index}>{frut}</li>;
                })}
            </ul>
        </div>
    );
};

export default App;
```

:::tip

-   React usa el key prop para crear una relación entre el componente y el elemento DOM.
-   La biblioteca utiliza esta relación para determinar si el componente debe volver a renderizarse o no.
-   No se recomienda utilizar el índice de la matriz como key si sabe que la matriz no será estática.
-   Si key es un índice, reordenar un elemento en la matriz lo cambia. Entonces React se confundirá y volverá a renderizar el elemento incorrecto.
-   [fuente](https://sentry.io/answers/unique-key-prop/)

:::

## props
- Se utiliza para enviar información al componente anidado.
- La información que transmites de esta manera se llama props.

```jsx
const ItemFrut = (props) => {
    return <li>{props.frut}</li>;
};

const App = () => {
    const fruts = ["🍐", "🍌", "🍎"];
    return (
        <div className="container">
            <ul>
                {fruts.map((frut, index) => {
                    return <ItemFrut key={index} frut={frut} />;
                })}
            </ul>
        </div>
    );
};

export default App;
```

## Práctica props
- Intenta hacer lo mismo pero con el componente **UserMessage**
- Puedes utilizar la desestructuración de JS. [más info aquí](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

Opción #01:
```jsx
const UserMessage = ({ user }) => {
    if (user) return <h2>Bienvenido</h2>;

    return <h2>Offline</h2>;
};
```

Opción #02:
```jsx
export default ({ user }) => 
    <h2>{user ? "Bienvenido" : "offline"}</h2>;
```

## Manejando eventos

-   [eventos](https://es.reactjs.org/docs/handling-events.html)
-   Los eventos de React se nombran usando camelCase, en vez de minúsculas.
-   Con JSX pasas una función como el manejador del evento, en vez de un string.

```jsx
const MyButton = () => {
    const handleClick = () => {
        console.log("me diste click");
    };

    return <button onClick={handleClick}>i'am a button</button>;
};
```

Con parámetros:

```jsx
const MyButton = () => {
    const handleClick = (name) => {
        console.log("me diste click: ", name);
    };

    return <button onClick={() => handleClick("🍎")}>i'am a button</button>;
};
```

## Componentes (modularizar)

-   [components](https://es.reactjs.org/docs/components-and-props.html)
-   Los componentes permiten separar la interfaz de usuario en piezas independientes, reutilizables y pensar en cada pieza de forma aislada.

components/MyButton.jsx

```jsx
const MyButton = () => {
    const handleClick = (name) => {
        console.log("me diste click: ", name);
    };

    return <button onClick={() => handleClick("🍎")}>i'am a button</button>;
};

export default MyButton;
```

App.jsx

```jsx
import MyButton from "./components/MyButton";
const App = () => {
    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
        </div>
    );
};

export default App;
```

## Práctica components
- Intenta llevar todo a componentes modularizados.
- ./components/MyButton.jsx
- ./components/UserMessage.jsx
- ./components/fruts/ListFruts.jsx
- ./components/fruts/ItemFrut.jsx

```jsx
import MyButton from "./components/MyButton";
import UserMessage from "./components/UserMessage";
import ListFruts from "./components/fruts/ListFruts";

const App = () => {
    const title = "Mi primero proyecto con React.js";
    const user = false;

    return (
        <div className="container">
            <h1 className="text-primary">{title}</h1>
            <MyButton />
            <UserMessage user={user} />
            <ListFruts />
        </div>
    );
};

export default App;
```


:::tip Fragmentos

-   [fragment](https://es.reactjs.org/docs/fragments.html): Un patrón común en React es que un componente devuelva múltiples elementos. Los Fragmentos te permiten agrupar una lista de hijos sin agregar nodos extra al DOM.

:::

```jsx
import MyButton from "./components/MyButton";
import UserMessage from "./components/UserMessage";
import ListFruts from "./components/fruts/ListFruts";
import React from "react";

const App = () => {
    const title = "Mi primero proyecto con React.js";
    const user = false;

    return (
        <React.Fragment>
            <h1 className="text-primary">{title}</h1>
            <MyButton />
            <UserMessage user={user} />
            <ListFruts />
        </React.Fragment>
    );
};

export default App;
```

```jsx
import MyButton from "./components/MyButton";
import UserMessage from "./components/UserMessage";
import ListFruts from "./components/fruts/ListFruts";

const App = () => {
    const title = "Mi primero proyecto con React.js";
    const user = false;

    return (
        <>
            <h1 className="text-primary">{title}</h1>
            <MyButton />
            <UserMessage user={user} />
            <ListFruts />
        </>
    );
};

export default App;
```

## Estado

-   El estado le permite a los componentes de React cambiar su salida a lo largo del tiempo en respuesta a acciones del usuario, respuestas de red y cualquier otra cosa.
-   [state](https://es.reactjs.org/docs/state-and-lifecycle.html)
-   Para hacer cambios vamos a utilizar un hook.

## Hooks

¿Qué pasa si hago esto?
import CounterExample from "./components/CounterExample";

```jsx
export default () => {
    let counter = 0;

    const handleClickIncrement = () => {
        counter++;
        console.log(counter);
    };

    return <button onClick={handleClickIncrement}>Counter: {counter}</button>;
};
```

-   Nada le indica a React que tenemos que volver a renderizar para pintar nuevamente button.
-   Necesitamos un Hook que modifique el estado. (ahora con hooks es más fácil)

:::tip hooks

-   [hooks](https://es.reactjs.org/docs/hooks-overview.html)
-   Los Hooks son funciones que te permiten “enganchar” el estado de React y el ciclo de vida desde componentes de función.
-   Los hooks no funcionan dentro de las clases — te permiten usar React sin clases.
-   React proporciona algunos Hooks incorporados como useState.
-   También puedes crear tus propios Hooks para reutilizar el comportamiento con estado entre diferentes componentes.

:::

## useState

-   [useState](https://es.reactjs.org/docs/hooks-state.html)

```js
import { useState } from "react";

export default () => {
    const [counter, setCounter] = useState(0);

    const handleClickIncrement = () => {
        setCounter(counter + 1);
        //setCounter((prevCounter) => prevCounter + 1);
    };

    return <button onClick={handleClickIncrement}>Counter: {counter}</button>;
};
```

### ¿Qué hace la llamada a useState?

-   Declara una “variable de estado”.
-   useState es una nueva forma de usar exactamente las mismas funciones que `this.state` nos da en una clase.
-   Normalmente, las variables “desaparecen” cuando se sale de la función, pero las variables de estado son conservadas por React.

### ¿Qué pasamos a useState como argumento?

-   El único argumento para el Hook useState() es el estado inicial.

### ¿Qué devuelve useState?

-   Devuelve una pareja de valores (array): el estado actual y una función que lo actualiza.

### Resumen:

-   Declaramos una variable de estado llamada contador y le asignamos a 0.
-   React recordará su valor actual entre re-renderizados, y devolverá el valor más reciente a nuestra función.
-   Si se quiere actualizar el valor de contador actual, podemos llamar a setContador.
-   Cuando el usuario hace click, llamamos a setContador con un nuevo valor. React actualizará entonces el componente Contador pasándole el nuevo valor de contador.
-   Nota los corchetes son intaxis de Javascript, se llama “desestructuración de arrays”.

## Prueba esto...
```jsx
<CounterExample />
<CounterExample />
```

- Verás que cada componente tiene su propio state o estado.
- ¿y si quiero compartir el estado? 

```jsx
import { useState } from "react";
const App = () => {

    const [counter, setCounter] = useState(0);

    const handleClickIncrement = () => {
        setCounter((prevCounter) => prevCounter + 1);
    };

    return (
        <div className="container">
            <CounterExample
                counter={counter}
                handleClickIncrement={handleClickIncrement}
            />
            <CounterExample
                counter={counter}
                handleClickIncrement={handleClickIncrement}
            />
        </div>
    );
};

export default App;
```

src\components\CounterExample.jsx
```jsx
export default (props) => {
    return (
        <button onClick={props.handleClickIncrement}>
            Counter: {props.counter}
        </button>
    );
};
```

Opción #02:
```jsx
<CounterExample
    counter={counter}
    onClick={handleClickIncrement}
    className="btn-primary"
/>
<CounterExample
    counter={counter}
    onClick={handleClickIncrement}
    className="btn-info"
/>
```

src\components\CounterExample.jsx
```jsx
export default ({ counter, ...props }) => {
    return <button {...props}>Counter: {counter}</button>;
};
```

:::tip ¿Qué está pasando acá?
- Estamos utilizando destructuring, rest operator y spread operator. [tutorial aquí](https://www.digitalocean.com/community/tutorials/understanding-destructuring-rest-parameters-and-spread-syntax-in-javascript)
- `export default ({ counter, ...props })` En esta línea estamos aplicando ***destructuring***: inicializando counter como una variable y el "resto" (rest operator) se va a una variable props.
- `<button {...props}>` aquí aplicamos la sintaxis extendida (Spread operator) expande iterables en elementos individuales.
:::


## Siguiente Clase

-   ¿Cómo utilizar state con objetos o arrays?