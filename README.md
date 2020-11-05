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

* **1er** Les Arrays ne sont pas facile a afficher dans la console car retourne uniquement le type d'objet contenu dedans ainsi que l'adresse memoire, rien de plus.

```cmd
[Lcom.monotonic.collections.common.Product;@78308db1].
```

Pour remedier a cela nous pouvons utiliser la methode toString de la class Arrays pour afficher sont contenu:


```java
System.out.println(Arrays.toString(products));

```

>**Arrays.toString(tableau [] en parametre)** ==> Retourne les chaine de caractere contenu dans un tableau

* **2eme** Si on declare un tableau de deux index contenant deux string et que l'on y ajoute un troisieme element lors JVM nous retourne l'exception ArrayIndexOutOfBoundsException:

```cmd
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 2 out of bounds for length 2
	at com.monotonic.collections._2_what_are_collections.before.TheArrayProblem.main(TheArrayProblem.java:20)
```

Pour y remedier, nous allons creer une methode d'ajout, qui nous retournera un tableau contenant des Produits et prendra en parametre, un produit (celui a ajouter) et un tableau de Produits (ici le tableau de longeur 2).

Nous y declarons (dans la methode d'ajout) :

* une variable int length representant la longueur du tableau (ici 2)
* une variable newArray de type Produit initialise a l'aide de la methode copy de la class Arrays (Arrays.copy), permettant de copier le tableau actuel et y ajouter un indexe (length +1)

Puis nous utilisons l'index de ce nouveau tableau (ici: 2+1=3) pour y affecter le nouveau produit (ici : windows (passe en parametre)

Et enfin retournons le nouveau tableau:


```java

products=add(window, products);

private static Product[] add(Product product, Product[] array)
{
    int length = array.length;
    Product[] newArray = Arrays.copyOf(array, length + 1);
    newArray[length] = product;
    return newArray;
}

// retourne 
[Product{name='Porte en bois', weight=35}, Product{name='Panneau de plancher', weight=25}, Product{name='Fenetre', weight=10}]

```

* **3eme** Si l'on souhaite reiterer l'operation d'ajout alors nous repetons products = add(window, products), se qui n'est pas une bonne pratique, et n'est pas flexible.


**LES COLLECTIONS SONT LA SOLUTIONS DE NOS PROBLEME D'ARRAYS**



































