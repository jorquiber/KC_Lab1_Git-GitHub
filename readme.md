
Author: **Jorge Quintero** 

- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

    Se usó: 
    
    ``` bash
    git reset --hard HEAD~1
    ```

    Este comando se usa para mover la rama entre los distintos commits existentes.

    - *HEAD~1* hace referencia al commit padre del commit al que apunta actualmente el puntero HEAD, es decir, al commit anterior

    -  La opción *--hard* nos permite llevar lo que hay en el graph/repository area del commit destino al working area actual, manteniendo los archivos que nunca han sido versionados (en este escenario no hay archivos que nunca han sido versionados)

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

    Se usaron 2 comandos:
    
    ```bash
    git reflog
    git reset --hard 06a9018
    ```
    1. *git reflog* para saber por qué commits ha pasado históricamente el puntero HEAD. Esto permitió saber en que commit se ubicó el puntero HEAD antes de 'deshacer' el commit anterior.
    2. Tras tener identificado el commit (06a9018) al que acceder, se usó el comando: *git reset --hard 06a9018* para volver a ese commit y llevar lo que hay en el graph/repository area del commit destino al working area actual

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
    
    No, no causó ningún conflicto, pero no se realizó ningún merge. Tras realizar el merge, apareció el siguiente mensaje en la terminal: *Already up to date*.
    Esto es porque si los commits de la rama main están "en el historial" de la rama styled (todos los commits de la rama main son accesibles desde la rama styled), no es necesario realizar una absorción desde styled. La rama styled ya tiene registrados todos los cambios de la rama main.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

   Sí, causó conflictos.
   
    La rama styled esta ubicada en el commit 'A', se realizaron unos cambios en unas líneas del fichero git-nuestro.md y se pasaron los cambios al repositorio (se genera commit 'B' donde está ubicada la rama styled)

    La rama htmlify esta ubicada en el commit 'A', se realizaron unos cambios en unas líneas del fichero git-nuestro.md y se pasaron los cambios al repositorio (se genera commit 'C' donde está ubicada la rama htmlify)

    Se generó una bifucarción desde el commit padre 'A', que tiene dos commits hijos 'B' y 'C'. 
    
    Al intentar styled absorber a htmlify (mergear commit 'B' con commit 'C'), se generó el conflicto porque los 2 cambios anteriores se realizaron en las **mismas líneas del fichero git-nuestro.md** y Git no tiene capacidad para saber cuál es la modificación correcta entre las dos.
   
- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

    No, no causó conflicto. La rama main estaba situado en un commit desde al cual se podía acceder desde la rama styled.
    
    Entonces, se realizó un mergeo fast-forward de la rama main en styled (la rama main se movió al commit donde estaba la rama styled y el working area pasó a ser el del commit destino)

- ¿Qué comando o comandos utilizaste en el paso 25?

    Se usaron varios metodos por consola:
    ```bash
    git log --graph
    git log --graph --oneline
    ```
    - *git log --graph* para ver el grafo
    - *git log --graph --oneline* para ver el grafo simplificado
    - También se usó la extensión Git Graph de VSCode, bastante más visual

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

    Sí, puede ser fast-forward. Esto es porque todos los commits accesibles desde la rama main están incluidos en la lista de commits accesibles desde la rama title.

- ¿Qué comando o comandos utilizaste en el paso 27?
    ```bash
    git reset HEAD~1
    ```
    Se usó el comando *git reset HEAD~1* para colocarse en el commit anterior

- ¿Qué comando o comandos utilizaste en el paso 28?
    ```bash
    git restore git-nuestro.md
    ```
    Se usó el comando *git restore git-nuestro.md* para dejar el working copy igual que en el graph/repository area.

- ¿Qué comando o comandos utilizaste en el paso 30?
    ```bash
    git reflog
    git reset --hard 6702348
    ```

    1. se usa *git reflog* para encontrar el id del commit en el que se estuvo antes de deshacer el commit
    2.  Se usa el comando *git reset --hard 6702348* para mover la rama main al commit deseado y dejar el working copy igual que el graph/repository area.

- ¿Qué comando o comandos usaste en el paso 32?
    ```bash
    git log
    git checkout a584232
    ```

    1. Sabiendo que HEAD apunta a la rama main y esta rama está apuntando al último commit realizado, se usa el comando *git log* para obtener todos los commits a los que puede acceder la rama main.
    2. Se obtiene el id del commit inicial: a584232
    3.  Se usa el comando *git checkout a584232* para que el puntero HEAD apunte al commit inicial

- ¿Qué comando o comandos usaste en el punto 33?
    ```bash 
    git reflog
    git checkout 6702348
    ```

    1. Mediante *git reflog*, se obtiene el id del commit final (También se puede obtener del comando *git log* del punto anterior, ya que el puntero HEAD estaba apuntando al commit final) 
    2. Se usa el comando *git checkout 6702348* para que el puntero HEAD apunte al commit final