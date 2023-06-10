# CI/CD Assignment 01

Authors: Manuel Lorente Almán y Juan Ángel garrido Lupiañez

[Repository](https://github.com/manulorente/mca-4.2-manuel.lorentea-juanangel.garridol-2023-ci)

## GitFlow development

Once workflows are defined, we can start developing our application. We will use GitFlow as a branching model. This model is based on two main branches with infinite life:

```sh
    git flow init -d
```

Push changes to develop branch to trigger the workflow:

```sh
    git push --set-upstream origin develop
```

Create new feature branch:

```sh
    git flow feature start break-lines
```  

Modify version in pom.xml file and add functionality:

```sh
    <version>0.2.0-SNAPSHOT</version>
```  

Commit changes and finish feature branch:

```sh
    git add src/test/java/es/urjc/code/daw/library/unitary/LineBreakerUnitaryTest.java 
    git add src/main/java/es/urjc/code/daw/library/book/LineBreaker.java
    git commit -m "Add line breaker tests"
    git push --set-upstream origin feature/break-lines
    git add src/main/java/es/urjc/code/daw/library/book/BookService.java
    git commit -m "Add line breaker functionality"
    git push --set-upstream origin feature/break-lines
    git flow feature finish -k break-lines
```  

Create release branch tagging the current version:

```sh
    git flow release start 0.2.0
    git flow release finish -k 0.2.0
```

