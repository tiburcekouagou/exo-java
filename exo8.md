# Palindrome
Il s'agit d'écrire un programme qui, étant donnée une chaîne de caractères (une instance de la classe String )

* calcule la chaîne inverse
* indique s'il s'agit ou non d'un palindrome

## Premier temps
En un premier temps, la chaîne à traiter ne comportera pas de caractère d'espacement et sera indiquée sur la ligne de commande.
_Exemples_   
* Si la commande est :
```shell
    java EssaiPalindrome bonjour
```
La réponse pourrait être :
```shell
    L'inverse de bonjour est ruojnob
    bonjour n'est pas un palindrome
```
* Si la commande est :
    java EssaiPalindrome laval
La réponse pourrait être
```shell
    L'inverse de laval est laval
    laval est un palindrome
```

On définira deux classes.

La première classe, nommée Palindrome, aura uniquement une méthodes statique dont l'en-tête sera :
```java
static String inverse(String s)
```
qui retournera un objet de type String contenant la chaîne inverse de la chaîne s. Cette méthode aura entre autres variables locales une variable nommée envers, de type StringBuffer destinée à contenir les caractères de s en sens inverse.

La seconde classe, nommée EssaiPalindrome, contiendra uniquement une méthode main ; dans cette méthode, on récupérera la chaîne sur la ligne de commande, on calculera son inverse grâce à la méthode inverse de la première classe, on affichera cet inverse, on indiquera aussi si la chaîne est ou non un palindrome.

_Indications_

La classe String possède:
* une méthode length() qui retourne le nombre de caractères de la chaîne concernée. Par exemple, si on a :

```
String s = "java",
s.length() vaut 4
```

* une méthode charAt(int i) qui retourne le caractère d'indice i de la chaîne concernée. Par exemple, si on a :
```
String s = "java",
s.charAt(2) vaut v
```
* une méthode equals(String c) qui retourne true si la chaîne concernée est identique à la chaîne c et false sinon.
* La classe StringBuffer modélise une chaîne de caractères modifiable.
    StringBuffer chaine = new StringBuffer();

construit un StringBuffer contenant une chaîne vide. Alors, si c est de type char :
    chaine.append(c)

ajoute c à la fin de la chaîne.
* Si chaine est de type StringBuffer, new String(chaine) construit un objet de type String correspondant à la chaîne de caractères contenue dans chaine


## Second temps

En un second temps, la chaîne à traiter sera lue en cours d'exécution du programme. par ailleurs, la chaîne pourra comporter des espaces. Il s'agira de savoir si la chaîne indiquée est ou non un palindrome en ne tenant pas compte des espaces.
Par exemple : "esope reste ici et se repose" devra être considéré comme un palindrome.

_Exemples_ A l'exécution, pour la commande :

```shell
    java EssaiPalindromeBis
```
on pourra avoir :

```
Indiquez la chaîne de caractères
esope reste ici et se repose
"esope reste ici et se repose" est un palindrome
```

On utilisera la méthode inverse de la classe Palindrome déjà définie. On écrira une classe nommée EssaiPalindromeBis contenant :
* une méthode qui retire les espaces d'une chaîne de caractères; reçue en paramètre et renvoie la chaîne obtenue ;
* une nouvelle méthode main.

_Indication_

Pour effectuer une saisie en cours d'exécution, on peut utiliser l'instruction suivante :
    java.util.Scanner entree = new java.util.Scanner(System.in);
qui définit l'objet entree permettant de faire des saisies au clavier.

Ensuite l'instruction
```
    String chaine = entree.nextLine();
```
met dans chaine la ligne entrée par l'utilisateur.
