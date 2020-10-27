# Introducción a GitFlow 

 

## Cada proyecto estará ubicado en un repositorio el cual partirá de las siguientes ramas: 

 
- Rama **master**: rama principal del proyecto, en esta rama debe haber una versión de código siempre preparada para hacer un despliegue en producción. Se debe etiquetar las confirmaciones sobre esta rama con un número de versión. 

- Rama **develop**: rama de la cual partirán las distintas ramas de desarrollo de las funcionalidades del proyecto. Se genera a partir de la rama master inicial. 

 
Posteriormente se crearán las siguientes ramas: 

 
- Ramas **features**: representan cada funcionalidad del proyecto, se genera a partir de la rama de desarrollo y se integrarán con ella. 

- Ramas **release**: representan la publicación de determinadas funciones. Una vez se determina la creación de una rama de publicación, esta operación se realizará a partir de la rama developer (a la cual se habrán incorporado las features correspondientes). Una release sólo corrige errores, se fusionará con master y developer cuando se libere y se eliminará la rama de publicación. 

- Ramas **hotfix**: ramas de mantenimiento para la corrección de errores. Se genera a partir de la rama master una vez subsanado el error de producción se fusiona con master y developer 

 
![WorkFlow] (https://i.stack.imgur.com/kF7Uf.png) 

**APB-PLANOL** WorkFlow
<img src=/images/workFlow.png alt="APB-PLANOL workFlow">

## Crear el gitFlow
 Ver documentación [gitFlow-workFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

- Neva Feature
  - git checkout master
  - git checkout -b develop
  - git checkout -b feature_branch
    - **Trabajamos en la branca**
  - git checkout develop
  - git merge feature_branch
  - git checkout master
  - git merge develop
  - git branch -d feature_branch

 - Nuevo Release
  - git checkout develop
  - git checkout -b release/1.0
  - git checkout master
  - git merge release/1.0

 - Hotfix
  - git checkout master 
  - git checkout -b hotfix_branch 
    - **Se ha trabajado con algunos commits en hotfix_branch** 
  - git checkout develop 
  - git merge hotfix_branch 
  - git checkout master 
  - git merge hotfix_branch
  - git checkout develop 
  - git branch -d hotfix_branch


## Ejemplo: desde cero en el  working directory con tres ficheros (README.md, contribute.md, /images/workFlow.png)
- git init
- git add .
  - Tres ficheros: README.md, contribute.md /images/workFlow.png
- git commit -m "First commit v1.0"
- git add remote origin https://github.com/portdebarcelona/PLANOL-gitFlow.git
- git push origin master
- git checkout -b develop
- git push --set-upstream origin develop
  - **Añadimos ejemplo en contribute.md**
  - git checkout -b feature_contribute
    - Añadimos ejemplo en contribute.md
    - git add -A
    - git commit -m "Added example"
  - git checkout develop
  - git merge feature_contribute
  - git push origin develop
  - git checkout master
  - git merge develop
  - git push origin master
  - Crear Release V1.0
    - git checkout develop
    - git checkout -b release/1.0
    - git push origin release/1.0
    - git checkout master
    - git merge release/1.0
  - Crear hotfix
    - git checkout master
    - git checkout -b hotfix_1
      - Realizamos cambios en  README.md y Contribute.md
      - git add -A
      - git commit -m"commit hotfix_1"
    - git checkout develop
    - git merge hotfix_1
    - git checkout master
    - git merge hotfix_1
    - git branch -d hotfix_1
    - git push origin master
    - git checkout develop
    - git push origin develop
  