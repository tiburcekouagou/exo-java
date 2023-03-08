## Une factorielle
Il s'agit d'écrire un programme qui calcule la factorielle d'un entier et indique à l'écran le résultat. Le nombre n doit être lu sur la ligne de commande.

Les quelques renseignements qui suivent peuvent être utiles :

* si n est une variable de type int, l'instruction :
```java
System.out.println(n);
```
provoque l'écriture de la valeur de n   
* l'instruction :
```java
System.out.println("voilà " + n);
```   
provoque l'écriture du mot voilà suivi de la valeur de n   
* La classe Integer du paquetage java.lang possède la méthode :
```public static int parseInt(String s) throws NumberFormatException;```
qui retourne l'int correspondant à la chaîne de caractères indiquée en paramètre. Cette méthode envoie une exception de type NumberFormatException si la chaîne de caractères ne correspond pas à un entier. Ne vous préoccupez pas ici de cet éventuel lancement d'exception, la possibilité de gérer les exceptions est abordée plus tard.   
* Le premier paramètre envoyé sur la ligne de commande après le nom du programme se trouve à l'indice 0 du tableau de chaînes de caractères de l'argument de la méthode main (si l'en-tête du main est public static void main(String[] arg), et si vous tapez sur la ligne de commande ```"java Factorielle 7"```, le ```"7"``` sera accessible dans le main, sous forme d'une chaîne de caractères, par ```arg[0]```) ; l'exécution de :
    ```java
    int n = Integer.parseInt(arg[0]);
    ```
donne alors la valeur 7 à l'entier n.   
Si vous utilisez l'environnement de programmation Eclipse en anglais, il faut donner les arguments avant l'exécution du programme, en choissisant ```" run configurations"``` puis l'onglet ```"Arguments"``` puis érire les arguments dans ```"Program arguments"```.
On peut compiler d'une fenêtre d'exécution avec l'instruction :
```shell
javac Factorielle.java
```
écrite dans le même répertoire que Factorielle.class
et exécuter avec
```shell
java Factorielle 7
```
si vous voulez la factorielle de l'entier 7.
