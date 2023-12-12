---
sidebar_position: 5
---
 
---
 

![vite](https://vitejs.dev/logo-with-shadow.png)

## * Crear una app con Vite 

 ---
### ENLACE PARA DESCARGAR Node.js
:::tip
  [  DESCARGAR Node.js](https://nodejs.org/en)
:::

---
### ENLACE PARA DESCARGAR UN EDITOR DE CODIGO: VScode.
:::tip
  [  DESCARGAR VScode](https://code.visualstudio.com/)
:::



---

ABRIR LA CONSOLA DE COMANDOS CMD

### CREAR UNA CARPETA DEL PROYECTO:



En la consola situada en la carpeta del proyecto escribimos el comando, para crear la App.

~~~
  npm create vite@latest
~~~
---

```
C:\Users\marin\Desktop\VITE_CURSO>npm create vite
√ Project name: web
√ Select a framework: » React
√ Select a variant: » JavaScript

Scaffolding project in C:\Users\marin\Desktop\VITE_CURSO\web

Done. Now run:

  cd web
  npm install
  npm run dev

```
---

### INSTALAR MODULOS O PAQUETES.

- Aqui instalamos la libreria para crear rutas

En la consola situada en la carpeta del proyecto escribimos el comando:

~~~
  npm i react-router-dom
~~~
---

### CORRER LA APP

- Aqui abrimos la App en el navegador

En la consola situada en la carpeta de la App escribimos el comando:
~~~
  npm run dev
~~~

--- 

<!-- ####################################### -->
<!-- ####################################### -->
<!-- ####################################### -->


## * Publicar App en github-pages

---

### ABRIR LA CONSOLA DE COMANDOS CMD

- Aqui instalamos la libreria gh-pages

En la consola situada en la carpeta del proyecto escribimos el comando:
~~~
  npm i gh-pages -D
~~~

---

### CREAR REPOSITORIO EN TU CUENTA DE GITHUB.com

Nombre REPOSITORIO: web

---

### CONFIGURAR ARCHIVOS

1.  AÑADIR EN EL ARCHIVO vite.config.js
~~~
 base:"/web/"
~~~
vite.config.js

```js
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  base: "/web/",
});
```

---

2. AÑADIR EL SCRIPT AL ARCHIVO package.json
~~~
"deploy": "gh-pages -d dist" 
~~~
package.json

```json
{
  "name": "app-componentes",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "deploy": "gh-pages -d dist"
  },
  "dependencies": {
    "gh-pages": "^5.0.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.9.0"
  },
  "devDependencies": {
    "@types/react": "^18.0.27",
    "@types/react-dom": "^18.0.10",
    "@vitejs/plugin-react": "^3.1.0",
    "vite": "^4.1.0"
  }
}
```

---

### SUBIR PROYECTO AL REPOSITORIO.

En la consola situada en la carpeta del proyecto escribimos el comando:

```
  git init

  git add .

  git status

  git commit -m "mi primer commit"

  npm run build

  git branch -M main

  git remote add origin https://github.com/juamaya/web.git

  git push -u origin main
```

---

### SUBIR CAMBIOS AL REPOSITORIO.

En la consola situada en la carpeta del proyecto escribimos el comando:

```
  git add .

  git commit -m "cambios realizados."

  npm run build

  git push

 
```

---

### PUBLICAR PROYECTO EN GITHUB-PAGES.

En la consola situada en la carpeta del proyecto escribimos el comando:

```
  npm run deploy
```

---


<!-- ####################################### -->
<!-- ####################################### -->
<!-- ####################################### -->


## * CLONAR EL REPOSITORIO. (web)

1. Crear una carpeta.

   - En la consola situada en la carpeta
   - Escribir el comando:

```
   git clone https://github.com/juamaya/web.git
```

2. Abrir el editor de codigo vsCode.

   - En la consola situada en la carpeta
   - Escribir el comando:

```
  code .
```

3. Instalar la carpeta **node_modules.**

   - Abrir la terminal en vsCode.
   - Escribir el comando:
~~~
    npm i
   ~~~

4. Correr la app.

   - Abrir la terminal en vsCode.
   - Escribir el comando:
~~~
   npm run dev

~~~
---
 
