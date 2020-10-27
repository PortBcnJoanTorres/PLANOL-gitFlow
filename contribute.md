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

# Crear el gitFlow
 [Documentacio](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

- New Feature
  - git checkout master
  - git checkout -b develop
  - git checkout -b feature_branch
  **work happens on feature branch**
  - git checkout develop
  - git merge feature_branch
  - git checkout master
  - git merge develop
  - git branch -d feature_branch

 - New Release
  - git checkout develop
  - git checkout -b release/1.0
  - git checkout master
  - git merge release/1.0

 - Hotfix
  - git checkout master 
  - git checkout -b hotfix_branch 
    **work is done commits are added to the hotfix_branch** 
  - git checkout develop 
  - git merge hotfix_branch 
  - git checkout master 
  - git merge hotfix_branch
  - git checkout develop 
  - git branch -d hotfix_branch



