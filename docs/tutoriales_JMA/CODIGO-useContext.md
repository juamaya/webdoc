# useCcontext

## app_web/src/contexts/myVariableContext.jsx

>Aqui creamos el contexto ***MyContext***

```jsx
import { createContext, useState } from "react";

const MyContext = createContext();

function MyProviderWrapper(props) {
  const [nombre, setNombre] = useState("My variable de Context : JUAMAYA");

  return (
    <MyContext.Provider value={{ nombre, setNombre }}>
      {props.children}
    </MyContext.Provider>
  );
}

export { MyContext, MyProviderWrapper };
```

## main.jsx

>Aqui envolvemos la APP en  el contexto ***MyProviderWrapper***

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import "./index.css";
import App from "./App.jsx";
import { BrowserRouter } from "react-router-dom";
import { MyProviderWrapper } from "./contexts/myVariableContext.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <MyProviderWrapper>
      <BrowserRouter>
        <App />
      </BrowserRouter>
    </MyProviderWrapper>
  </StrictMode>
);
```

## Home.jsx

>Aqui usamos el contexto ***MyContext***

```jsx
import { MyContext } from "../contexts/myVariableContext";
import { useContext } from "react";

const Home = () => {
  const { nombre, setNombre } = useContext(MyContext);

  return (
    <div>
      <h3>Home</h3>
      <h4>Imagen de la carpeta public</h4>
      <img src="/images/car1.png" alt="Car" width={500}></img>
      <h1>{nombre}</h1>
    </div>
  );
};
```

## Contact.jsx


>Aqui usamos el contexto ***MyContext***

```jsx
import React, { useContext } from "react";
import { MyContext } from "../contexts/myVariableContext";

const Contact = () => {
  const { nombre, setNombre } = useContext(MyContext);

  return (
    <>
      <div>Contact</div>
      <h1>{nombre}</h1>
    </>
  );
};

export default Contact;
```
