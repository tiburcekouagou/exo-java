## Une classe pour modéliser un segment de droite
Il s'agit de modéliser un segment de droite dont les valeurs des abscisses des deux extrémités sont entières. Les opérations que l'on souhaite faire sur ce segment sont :   

* calculer sa longueur ;
* savoir si un point d'abscisse donné se trouve sur le segment (c'est-à-dire si son abscisse est comprise entre la plus petite et la plus grande valeurs des abscisses des extrémités du segment).   

Écrire le code une classe publique `Segment` se trouvant dans un paquetage de nom `segment` comportant :

  * deux attributs privés de type int, extr1 et extr2, représentant les abscisses (entières) des extrémités d'un segment sur un axe ; la classe fera en sorte que extr1 soit toujours au plus égal à extr2 ;
  * un constructeur de ce segment recevant en arguments les deux valeurs entières des abscisses des extrémités du segment que l'on veut construire ;
  * une méthode privée nommée `ordonne` échangeant éventuellement les valeurs des extrémités du segment de telle sorte que la valeur de extr1 soit au plus égale à la valeur de extr2 ; cette méthode devra utiliser une instruction conditionnelle ; voir ci-dessous pour ceux qui ne connaitraît pas ce type d'instruction.
  * une méthode publique retournant la longueur du segment ;
  * une méthode dont le prototype est :
**public boolean appartient(int x);** indiquant si le point de coordonnée `x` appartient ou non au segment ;
      * le getter public int getExtr1() ;
      * le setter public void setExtr1(int a) ;
      * le getter public int getExtr2() ;
      * le setter public void setExtr2(int a) ;
      * une méthode d'en-tête :   
&nbsp;&nbsp;&nbsp;public String toString()
&nbsp;(qui redéfinit la méthode toString de la classe Object, mais cela sera sans doute vu plus tard). Cette méthode décrira une instance de Segment sous la forme d'une chaîne de caractères, c'est-à-dire d'un objet de type String ; pour le segment d'extrémités -35 et 44, cette chaîne pourrait être : "segment [-35, 44]"). La méthode "retournera" (return...) cette chaîne.

Vous définirez aussi dans le paquetage segment une classe TestSegment pour tester la classe Segment. Cette classe comportera une méthode main à laquelle vous devrez fournir trois paramètres entiers par la ligne de commande : abcisses des deux extrémités d'un segment et abscisse d'un point dont on voudra savoir s'il appartient ou non au segment.

Si le tableau de chaînes de caractères qui se trouve en argument de la méthode main s'appelle arg, ces trois arguments sont nommés arg[0], arg[1] et arg[2] et seront convertis en int par la méthode Integer.parseInt(String s).

Avant d'exécuter la méthode main, dans la fenêtre obtenue par Run configurations, cliquez sur l'onglet Arguments et inscrire les valeurs des trois paramètres.

On utilisera nécessairement la méthode toString lorsqu'on voudra écrire le segment sur la sortie standard (l'écran).

**Exemple d'exécution souhaitée pour la méthode `main`**

Pour la commande :   
    java segment.TestSegment 44 -35 8, c'est-à-dire pour les arguments -35 44 8, la sortie du test pourrait être :
    Longueur du segment [-35, 44] : 79   
    8 appartient au segment [-35, 44]
Pour la commande :   
    ```__TestSegment__ 44 -35 100```, c'est-à-dire pour les arguments -35 44 100, la sortie du test pourrait être : :   
```java
    Longueur du segment [-35, 44] : 79
    Longueur du segment [-35, 44] : 79
    100 n'appartient pas au segment [-35, 44]
```
    
**Indications**   
1. Pour transformer une chaîne de caractères s en un int que l'on affecte à une variable entière n, on peut écrire :
```java
n = Integer.parseInt(s);.
```
La méthode parseInt est une méthode statique de la classe java.lang.Integer.   

2. Si la méthode toString est définie comme indiqué ci-dessus, si on a défini :
Segment e = new Segment(1, 3));
l'instruction :
```System.out.println(e);```
donnera sur la sortie standard : ```segment [1, 3]```
et l'instruction :
```System.out.println("le " + e);```
donnera sur la sortie standard : ```le segment [1, 3]```

3. Le "et logique" sécrit && en Java, le "ou logique" s'écrit ||.


## Indications sur l'instruction conditionelle

Une instruction conditionelle s'écrit :
```java
if (condition) {
    instruction1;
    instruction2;
    ...
}
else {
    autreInstruction1;
    autreInstruction2;
}
```

Les parenthèses autour de la condition sont obligatoires.   
Il peut ne pas y avoir de else, on peut écrire :
```java
if (condition) {
    instruction1;
    instruction2;
    ...
}
```

puis la suite du code sans commencer par le mot else.   
Si une seule instruction est à faire dans le bloc du if ou dans le bloc du else, les accolades sont facultatives. On peut écrire :
```java
if (condition) instruction1; ...
```

On peut composer en écrivant :
```java
if (condition) //bloc d'instructions
else if (autreCondition) //bloc d'instructions
else //bloc d'instructions
```
