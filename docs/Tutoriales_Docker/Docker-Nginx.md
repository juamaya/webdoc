---
sidebar_position: 3
---


# Docker + Nginx

## Docker Container Web

# 🐳

![container_docker](img/container_docker.png)

## <font color="#00ff00" >  En Windows Docker Desktop de estar corriendo </font>

## <font color="#6bbfe5ff">Abre Terminal en VScode.</font>

:::info

### <font color="#00ff00">Ejecuta estos comandos dentro de la carpeta del proyecto</font>

# 🚀
## Run Container 

```bash
 docker-compose up -d
```

## Stop Container

```bash
docker-compose down
```

## Stop and Run Container

```bash
docker-compose down && docker-compose up -d
```
:::

---

### Estructura del proyecto

![container_docker](img/estructura.png)

---

### Crea el archivo: docker-compose.yml  en la raiz de tu proyecto.

:::info

>docker-compose.yml

```yml

version: '3.8'

services:
    nginx:
        image: nginx:alpine
        container_name: nginx-container
        ports: - "8081:80"
        volumes: - ./nginx.conf:/etc/nginx/nginx.conf - ./html:/usr/share/nginx/html
        restart: unless-stopped

networks:
    default:
    name: nginx-network

```
:::

---

## Crea el archivo: nginx.conf

>nginx.conf

```conf

events {
    worker_connections 1024;
}

http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;

    sendfile on;
    keepalive_timeout 65;

    server {
        listen 80;
        server_name localhost;
        root /usr/share/nginx/html;
        index index.html;

        location / {
            try_files $uri $uri/ /index.html;
        }

        error_page 404 /404.html;
        error_page 500 502 503 504 /50x.html;
        
        location = /50x.html {
            root /usr/share/nginx/html;
        }
    }
}


```

## Crea el archivo: index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta name="description"
        content="Docker Nginx Tutorial - A simple setup to run Nginx in a Docker container with Docker Compose.">

    <meta name="author" content="Juamaya">
    <link rel="icon" href="img/docker.jpg" type="image/x-icon">

    <title>Docker Nginx Tutorial</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            max-width: 600px;
            margin: 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .badge {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            padding: 0.5rem 1rem;
            border-radius: 25px;
            margin: 0.5rem;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .docker-logo {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .status {
            margin-top: 2rem;
            padding: 1rem;
            background: rgba(0, 255, 0, 0.2);
            border-radius: 10px;
            border: 1px solid rgba(0, 255, 0, 0.3);
        }

        .footer {
            margin-top: 2rem;
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.7);
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="docker-logo">🐳</div>
        <h1>Docker + Nginx</h1>
        <p class="subtitle">Successfully running in a container!</p>

        <div class="badges">
            <span class="badge">Docker Compose</span>
            <span class="badge">Nginx Alpine</span>
            <span class="badge">Port 8081</span>
        </div>

        <div class="status">
            <strong>✅ Container Status: Running</strong><br>
            Your Docker Compose setup is working correctly!
        </div>
    </div>
    <footer class="footer">

        <span class="badge">Juamaya 🍺 2025</span>
    </footer>

</body>

</html>

```

## Para levantar el contenedor:
<font color="#00ff00" >En la terminal, desde la carpeta donde está el docker-compose.yml, ejecuta:</font>

```bash
docker-compose up -d
```

###  Luego abre tu navegador y visita: http://localhost:8081

---
 