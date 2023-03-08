# Gérer une pile d'entiers

Il s'agit de définir une classe modélisant une pile d'entiers. Nécessairement, tous les attributs de cette classe auront le modificateur private, ce qui signifie qu'on ne peut pas les utiliser directement de l'extérieur de la classe (on dit encore qu'ils ne sont visibles que de leur propre classe).
Cette classe possèdera les trois méthodes suivantes (il faudra reprendre exactement les en-têtes indiquées) :

* ```void empiler(int n)```
Cette méthode empile la valeur n reçue en paramètre.
* ```int depiler() throws ExceptionPileVide```
    Si la pile est vide, cette méthode lance une exception, ce que vous ferez par l'instruction :
    ```throw new ExceptionPileVide();```
    sinon, elle dépile un entier dont elle retourne la valeur,
    Vous devez recopier dans votre répertoire courant le fichier ExceptionPileVide.java qui vous est fourni.
    * boolean estVide()
    Cette méthode retourne true si la pile est vide et false dans le cas contraire.
    
Vous pourrez implémenter la pile de trois façons différentes, en définissant une classe pour chaque façon. Vous pouvez bien sûr choisir une des possibilités si vous ne souhaitez pas traiter les trois.

* La première classe, nommée Pile1, utilisera un ArrayList<Integer> pour y ranger les entiers.
_Indications_
    * La méthode add de la classe ArrayList ajoute les nouveaux éléments à la fin de la liste.
    * Si l'ArrayList se nomme liste, les éléments sont rangés dans liste entre les indices 0 et liste.size() - 1.
    * La méthode remove(int indice) permet de retirer l'élément qui se touve à l'indice indiqué.
    * Si une variable n de type int est utilisée à un endroit où un Integer est attendu, le compilateur s'en aperçoit et transforme n en l'Integer contenant la valeur de n.
* La deuxième classe, nommée Pile2, utilisera une liste chaînée. Il faudra définir une classe supplémentaire pour modéliser un maillon de cette liste.
* La troisième classe, nommée Pile3, utilisera un tableau d'entiers. Au départ, ce tableau aura une certaine longueur, petite (par exemple 3); il faudra veiller à agrandir ce tableau lorsqu'il est plein et que l'on veut encore empiler un entier ; on pourra alors agrandir le tableau d'une quantité déterminée (par exemple 2).

On testera les classes en utilisant le fichier InterfacePile.java. Dans ce fichier, il faudra juste changer Pile1 en Pile2 si on veut tester la classe Pile2 et en Pile3 si on veut tester la classe Pile3. Après avoir compilé le fichier, on exécutera la méthode main avec l'instruction java InterfacePile. On aura alors une interface graphique qui utilise Pile1 (ou Pile2 ou Pile3) et qui permet :

* d'empiler des entiers, en les écrivant dans une petite ligne de texte, un par un, ou plusieurs à la suite séparés par des espaces puis en activant le bouton "empiler" ou bien en tapant sur la touche d'entrée ;
* de dépiler une donnée de la pile ;
* de savoir si la pile est vide ou non.
