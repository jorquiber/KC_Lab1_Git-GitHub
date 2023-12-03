
Author: **Jorge Quintero** 

- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

    Se usó el comando *git reset --hard HEAD~1*:

    Este comando se usa para mover la rama entre los distintos commit.

    -  La opción --hard nos permite hacer perder los cambios del working area actual tras el cambio de posición de la rama (hacer que el working area coincida con el graph/repository area del commit al que accedes)

    - HEAD~1 hace referencia al commit padre del commit al que apunta actualmente el puntero HEAD 

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

    Se usaron  2 comandos:
    
    1. *git reflog* para saber por qué commits ha pasado históricamente el puntero HEAD. Esto permitió saber en que commit se ubicó el puntero HEAD antes de 'deshacer' el commit anterior.
    2. Tras tener identificado el commit (06a9018) al que acceder, se usó el comando: *git reset --hard 06a9018* para volver a ese commit y perder el working area actual (hacer que el working area coincida con el graph/repository area del commit al que accedes)

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
    
    No, no causó ningún conflicto, pero no se realizó ningún merge. Tras realizar el merge, apareció el siguiente mensaje en la terminal: *Already up to date*.
    Esto es porque si los commits de la rama main están "en el historial" de la rama styled, no es necesario realizar una fusión porque la rama styled ya contiene todos esos cambios. 

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

   Sí, causó conflictos. Se realizaron 2 modificaciones del fichero git-nuestro.md, una en la rama styled y otra en la rama htmlify. Ambas ramas partieron del mismo commit padre, por lo que generaron 2 bifurcaciones distintas. 
   
   Por lo anterior y al ser 2 modificaciones distintas de las **mismas líneas del fichero git-nuestro.md**, al mergearlos, se generó el conflicto.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

    No, no causó conflicto. La rama main estaba situado en un commit desde al cual se podía acceder desde la rama styled.
    
    Entonces, se realizó un mergeo fast-forward de la rama main en styled (la rama main se movió al commit donde estaba la rama styled)

- ¿Qué comando o comandos utilizaste en el paso 25?

    Se usaron varios metodos:
    - *git log --graph* para ver el grafo
    - *git log --graph --oneline* para ver el grafo simplificado
    - También se usó la extensión Git Graph de VSCode 

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

    Sí, puede ser fast-forward. Esto es porque el commit en el que está la rama main está incluido en la lista de commits a los que puede acceder la rama title (desde el commit inicial del repositorio hasta el commit en el que está la rama title).

- ¿Qué comando o comandos utilizaste en el paso 27?

    Se usó el comando *git reset HEAD~1* para colocarse en el commit anterior

- ¿Qué comando o comandos utilizaste en el paso 28?

    Se usó el comando *git restore git-nuestro.md* para dejar el working copy igual que el graph/repository area

- ¿Qué comando o comandos utilizaste en el paso 30?

    - Como primer paso, se usa *git reflog* para encontrar el id del commit en el que se estuvo antes de deshacer el commit
    - Se usa el comando *git reset --hard 6702348* para mover la rama main al commit deseado

- ¿Qué comando o comandos usaste en el paso 32?

    - Sabiendo que HEAD apunta a la rama main y esta rama está apuntando al último commit realizado, se usa el comando *git log* para obtener todos los commits a los que puede acceder la rama main.
    - Se obtiene el id del commit inicial: a584232
    - Se usa el comando **git checkout a584232** para que el puntero HEAD apunte al commit inicial

- ¿Qué comando o comandos usaste en el punto 33?

    -  Mediante *git reflog*, se obtiene el id del commit final (También se puede obtener del comando *git log* del punto anterior, ya que el puntero HEAD estaba apuntando al commit final) 
    - Se usa el comando **git checkout 6702348** para que el puntero HEAD apunte al commit final