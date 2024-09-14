## FullstackProject2024 🚀

### 💡 **Curso Fullstack de Programación**
Bienvenidos a la entrega de ejercicios del curso Fullstack de Programación. Este repositorio contiene los proyectos y ejercicios completados.

### 📂 **Ejercicios 0.4 - 0.6**

📌 **Ejercicio 0.4** - *Diagrama de Eventos: Nueva Nota (Tradicional)*  
Diagrama que describe la situación en la que el usuario crea una nueva nota en la página   

```mermaid
sequenceDiagram  
    participant user 
    participant browser 
    participant server 

    user->>browser: Escribir nota en el campo de texto
    user->>browser: Clic en el boton "Save"

    Note right of browser: El navegador recoge la nota ingresada por el usuario

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note con los datos de la nota
    activate server
    Note right of server: El servidor recibe la nueva nota y la guarda en la base de datos
    server-->>browser: Respuesta de confirmacion (HTTP 302 Redirect)
    deactivate server

    Note right of browser: El navegador redirige a la pagina principal de notas

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML actualizado con la nueva nota
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: El archivo CSS
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: El archivo JavaScript
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Datos JSON con las notas actualizadas
    deactivate server

    Note right of browser: El navegador renderiza la nueva nota en la pagina
```


📌 **Ejercicio 0.5** - *Diagrama de Eventos: Carga pagina con (SPA)*  
Diagrama que describe la situación en la que el usuario accede a la versión de aplicación de una sola página

```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: Documento HTML (spa)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Archivo css (main)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: Archivo JavaScript (spa)
    deactivate server

    Note right of browser: El navegador empieza ejecutando el javascrip con los datos (JSON) que recibe

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Contenido actualizado (data)
    deactivate server

    Note right of browser: carga la pagina
```

📌 **Ejercicio 0.6** - *Diagrama de Eventos: Nueva Nota (SPA)*  
Diagrama que representa la situación en la que el usuario crea una nueva nota utilizando la versión de una sola página de la aplicación.  

```mermaid
sequenceDiagram
    participant user 
    participant browser 
    participant server 

    Note right of user: El usuario escribe una nota en el campo de texto y hace clic en "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note con los datos de la nota
    activate server
    Note right of server: El servidor recibe la nueva nota y la guarda en la base de datos
    server-->>browser: Respuesta de confirmacion (HTTP 200 OK o similar)
    deactivate server

    Note right of browser: El navegador solicita los datos actualizados para incluir la nueva nota

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Datos JSON con las notas actualizadas
    deactivate server

    Note right of browser: El navegador renderiza la nueva nota en la pagina SPA

```

📬 **Contacto**
- GitHub: /N3WL4ND5  
* Correo Electrónico: jeanpier.madridb@gmail.com