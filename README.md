# REFERENCIES
# curs interesant
https://www.youtube.com/watch?v=FZRLRVxlxUw&list=PLm0WEBt1zBgLSZJ-1Ttt2nvfcyudQ-4-l
# Proves de Branch
https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
https://desarrolloweb.com/articulos/trabajar-ramas-git.html

**Creen repositori git PLANOL-xxxx**
1. Clone del repositori en local c:\temp\proves_branch\PLANOL-ProvaBranch
2. Creen un READMI.md
3. git add README.md
4. git commit -m"Add README.md"
5. git push
6. Creem Una Branch nova develop
7. git branch Per veure la branca on som
8. git branch develop (crear bifurcacio)
9.  git chekout develop (canviar de branca)
10. git switch -b develop (crea i es situa en la branca)
11. git checkout master
12. git merge test
13. Si volem retornar a la bhanca develop
14. git checkout develop (Ep develop no esta en la ultim commit)
15. git merge master  (fa un fast-forware) Ara HEAD de master i develop apuntent al mateix
16. git checkout -b develop
17.  git push --set-upstream origin develop

**Merge de dues branchs en local**
Suposem que tenim dues branch master i develop
i volen fer merge  a master
1. git checkout master
2. git merge develop

**Git rebase**
permet restructura la branca master amb una subpronca. Es com si ajuntem les brances.
Suposem que tenim dos branch master i test. A master tenim dos fitxers f1 i f2 . A test tenim f1 i f3
git checkout master
git rebase test
acabem tenin un master amb els fitxers f1,f2,f3 pero hem simplificat els nodes de manera que master s'ha ajuntat a partir de test
git checkout experiment
1. git rebase master
Despres d'aixo develop s'han actualitzar els fitxers de master. Ep no els nous de experiment
Per fer que master tambe tingui els de develop:
1. git checkout master
2. git merge develop


# Forma de treballar
1/ Fer un fork del repositori on em de treballar
2/ Fer clone del repositori fork
3/ push dels canvis al nostre repositori
4/ Crear un pull-request al repositiri original
Ells repassan i fan merge del request


** git log**
1. git log # per veure els commits que s'han fet.
  **HEAD es on apunta actualment en el repositori local**
2. git status
3. echo "Linia 1" >> hola.txt
4. git add hola.txt
5. git commit -m"Mi primer fichero"
6. git log --oneline --graph --decorate
7. git branch (veure branch que tenim)
8. git log --oneline
9. echo "Linia 2" >> hola.txt
10. git add -A
11. git commit m"Segon commit" 
12. git checkout -- hola.txt Tornem endarrera
13. echo "Linia 2" >> hola.txt
14. git add hola.txt
15. git reset HEAD hola # i torna  a unstaget
16. git reset --hard  codiCoomit (git log --oneline) Torna al commit indicat i perdem tots els canvis posteriors
17. git reset --mixed codi  # Desfem darrer commit pero no els canvis fets . Es que com abans del commit
18. echo "otro fichero" >> fichero2.txt
19. git add .
20. git status
21. git commit --amend S'afegeix en el commit anterior. Vull dir no crea un nou commit

**Per revisar un commit**
- git show codiCommit

**git diff**
per comparar dos commits 
- git diff HEAD¬1..HEAD¬2 (compara els dos commits)
- Per comorar branch
  - git diff test..master

# Corregir errores.
# No generar un commit nou. pq t'has deixat alguna cosa )

# git diff # per veure canvis
git diff --> diferencies entre working  area i index area
git diff --cached diferencies entre index area i repositori local

**git rm borrar fitxers**
BSi borrem del working area (directori) i tambe des de index Area
- git rm --cached borra de l'index pero no del workingArea
- git rm -f borra del workingArea i del index Area

**More fitxers (rename - move)**
1. mv menu.txt menu.log
2. git add menu.log
3. git add menu.txt
4. git status --> indica que hi ha un rename. No un add i un delete)
5. git commit -m "Rename"
6. Alternativa 
   - git mv ... ho fa tot directament


**git tag**
1. git tag -a V1.0 -m "Primera version de la app" (-a annotated tags)
2. git cat-file  <codi> per veure objectes (commits)
3. git cat-file -p V1.0

** git clone**
1. git clone https:.....git
2. remote -v
3. git status
4. git push origin master
5. git tag -a V1.0 -m "comment"
6. git push origin --tags

**Crear branca al remote**
- git ckeckout -b nomBranca
- git push
