1. Primero debes acceder a tu cuenta de [Github](https://github.com/login), en la ventana de bienvenida debes ubicar la manera de crear un repositorio, a la fecha de creación de esta guía la creación se realiza desde la sección "Start Writing Code" como te señalamos en la siguiente imagen. 

    ![IMG-01](./assets/01.png)

2. Una vez localices el apartado correspondiente deberás darle un nombre a tu repositorio (en nuestro caso "MkDocs") y seleccionar la visibilidad (en nuestro caso será un repositorio "Public"). En cuanto hayas indicado esos valores da click en el botón "Create a New Repository".

    ![IMG-02](./assets/02.png)

3. En cuanto crees el repositorio podrás acceder al parámetro que permite clonarlo en nuestro equipo, asegurate que la opción de "Quick Setup" tenga seleccionado "SSH" y copia el valor correspondiente. 

    ![IMG-03](./assets/03.png)

4. En tu terminal ejecuta el siguiente comando sustituyendo por tu valor correspondiente.
    ```BASH
    git clone git@github:<USUARIO>/<REPOSITORIO>.git
    ```
    
    ![IMG-04](./assets/04.png)

    Una vez se haya copiado el repositorio deberas ver un mensaje como el siguiente.

    ![IMG-05](./assets/05.png)

5. Cambia tu directorio de trabajo al del repositorio recien copiado.
    ```BASH
    cd <Repositorio>
    ```
    ![IMG-06](./assets/06.png)


6. Crea un [entorno virtual](https://docs.python.org/es/3/tutorial/venv.html) mediante el siguiente comando:

    ```BASH
    python3 -m venv .venv
    ```
    ![IMG-07](./assets/07.png)

7. Activa tu entorno virtual con:
    ```BASH
    source .venv/bin/activate
    ```
    ![IMG-08](./assets/08.png)

8. Asegurate de tener instalado el gestor `pip`con:
    ```BASH
    pip --version
    ```    
    ![IMG-09](./assets/09.png)

9. Instala el generador de sitios con el comando:
    ```BASH
    pip install mkdocs-material
    ```    
    ![IMG-11](./assets/10.png)

    Se generará una serie de líneas con notas de lo que está haciendo el instalador, espera a que termine. 

    ![IMG-11](./assets/11.png)

10. Abre tu carpeta en el editor VS Code.

    ```BASH
    code .
    ```
    ![IMG-12](./assets/12.png)
        
    ![IMG-13](./assets/13.png)

11. Regresa a tu terminal para generar un nuevo sitio mediante este comando:
    ```BASH
    mkdocs new .
    ```
    ![IMG-14](./assets/14.png)

    Se generará una carpeta llamada docs, con un archivo llamado "index.md" y en la raíz se generará un archivo llamado "mkdocs.yml".

    ![IMG-15](./assets/15.png)

    ![IMG-16](./assets/16.png)
    
12. Ejecute un servidor temporal mediante el siguiente comando:
    ```BASH
    mkdocs serve
    ```    
    ![IMG-17](./assets/17.png)
        
    ![IMG-18](./assets/18.png)

13. Visite el sitio que indicó su consola, generalmente será [http://172.0.0.1:8000/](http://172.0.0.1:8000/)    
    ![IMG-19](./assets/19.png)
14. Añada el tema "material" en su archivo `mkdocs.yml`.    
    ![IMG-20](./assets/20.png)
15. Actualice el sitio y vea el nuevo formato.    
    ![IMG-21](./assets/21.png)

16. Detenga la ejecución del servidor y copie el siguiente contenido en su archivo `mkdocs.yml`

    ```YAML
    site_name: Guía MKDocs con Material
    #site_url: 
    theme:
    name: material
    #  logo: 
    #  favicon: 
    features:
        - navigation.tabs
        - navigation.sections
        - navigation.expand
        - toc.integrate
        - navigation.top
        - search.suggest
        - search.highlight
        - content.tabs.link
        - content.code.annotation
        - content.code.copy
    language: es
    palette:
        - scheme: default
        toggle:
            icon: material/toggle-switch-off-outline 
            name: Switch to dark mode
        primary: pink
        accent: red 
        - scheme: slate 
        toggle:
            icon: material/toggle-switch
            name: Switch to light mode    
        primary: pink
        accent: pink

    plugins:
    - social
    - search

    extra:
    social:
        - icon: fontawesome/brands/discord
        #  link: 
        - icon: fontawesome/brands/github-alt
        #  link: 
        - icon: fontawesome/brands/linkedin
        #  link: 

    markdown_extensions:
    - pymdownx.highlight:
        anchor_linenums: true
    - pymdownx.inlinehilite
    - pymdownx.snippets
    - admonition
    - pymdownx.arithmatex:
        generic: true
    - footnotes
    - pymdownx.details
    - pymdownx.superfences
    - pymdownx.mark
    - attr_list
    - pymdownx.emoji:
        emoji_index: !!python/name:material.extensions.emoji.twemoji
        emoji_generator: !!python/name:materialx.emoji.to_svg

    #copyright: |
    

    extra_javascript:
    - https://polyfill.io/v3/polyfill.min.js?features=es6
    - https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js

    ```

17. Ejecute el siguiente comando en su terminal
    ```BASH
    pip install "mkdocs-material[imaging]"
    ```
    ![IMG-22](./assets/22.png)

18. Vuelva a habilitar el servidor:
    ```BASH
    mkdocs serve
    ```
19. Su sitio debería verse así:

    ![IMG-23](./assets/23.png)

