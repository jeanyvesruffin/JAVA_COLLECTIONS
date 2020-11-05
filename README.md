# JAVA_COLLECTIONS

# Context et lecture application

Apres avoir recupere le projet et l'avoir construit a l'aide de gradle, lisons le code.

Pour chaque module etudie deux packages existent, une trame (before) suivi d'une correction (after).


L'application,

Declare de nouveaux produits, les produits ont les attributs nom et poids.

Le but vas t'etre d'implementer les methodes permettant de:

* Creer un tableau contenant ces produits

```java
Product[] products = {door, floorPanel};
```

* Ecrire dans la console le tableau de produit

```java
System.out.println(products);
// retourne [Lcom.monotonic.collections.common.Product;@78308db1
```

* Ajouter un produit au tableau

```java
products[2]=window;
System.out.println(Arrays.toString(products));
```

* Dupliquer ce tableau

# Le probleme des Array

**Inconvenient des Arrays**


* Les Arrays ne sont pas facile a afficher dans la console car retourne uniquement le type d'objet contenu dedans ainsi que l'adresse memoire, rien de plus.

```cmd
[Lcom.monotonic.collections.common.Product;@78308db1].
```

Pour remedier a cela nous pouvons utiliser la methode toString de la class Arrays pour afficher sont contenu:


```java
System.out.println(Arrays.toString(products));

```

>**Arrays.toString(tableau [] en parametre)** ==> Retourne les chaine de caractere contenu dans un tableau

* Si on declare un tableau de deux index contenant deux string et que l'on y ajoute un troisieme element lors JVM nous retourne l'exception ArrayIndexOutOfBoundsException:

```cmd
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 2 out of bounds for length 2
	at com.monotonic.collections._2_what_are_collections.before.TheArrayProblem.main(TheArrayProblem.java:20)
```




































