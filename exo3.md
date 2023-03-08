## Premier contact : modéliser un étudiant
Vous avez déjà dans le fichier créé :
```java
package etudiant;

public class Etudiant {

}
```
Vous allez compléter le code de cette classe en lui ajoutant :   
* un attribut privé de type String nommé nom ;
* un constructeur publique qui a un paramètre de type String servant à initiliser le nom de l'étudiant ;
* une méthode publique sans paramètre et qui ne renvoie rien, nommée `travailler`, qui écrit à l'écran, si le nom de l'étudiant a pour nom toto :
    ```toto se met au travail !  ``` 
Pour cela, il faut utiliser l'instruction : ```System.out.println(this.nom + " se met au travail !")```;
* une méthode publique sans paramètre et qui ne renvoie rien, nommée `seReposer`, qui écrit à l'écran, si le nom de l'étudiant a pour nom toto :
    ```toto se repose```   
Vous allez ensuite créer parallèlement à la classe `Etudiant` une classe `TestEtudiant` (aussi dans le paquetage etudiant) contenant une méthode main qui :
* crée un étudiant (instance de la classe Etudiant) en lui donnant un nom écrit directement dans le fichier source ;
* invoque la méthode travailler de l'étudiant créé ;
* invoque la méthode seReposer de l'étudiant créé .   
Il faut alors exécuter ce programme, c'est-à-dire la méthode main de la classe TestEtudiant. Pour cela, dans le menu de gauche, cliquez avec le bouton de gauche de la souris sur TestEtudiant, classe qui contient la méthode main ; puis avec le bouton droite, dans le menu déroulant, choisissez Run as et dans le nouveau menu déroulant Java Application ; les fois suivantes, vous pourrez exécuter le programme avec une petite flèche sur fond vert qui figure dans la barre en haut d'Eclipse.    
Si tout fonctionne, vous pouvez améliorer un peu le programme en faisant en sorte que le nom de l'étudiant soit indiqué comme argument de la méthode main ; pour cela

* modifiez votre méthode main pour que le nom de l'étudiant soit l'argument d'indice 0 du main (si l'en-tête de la méthode main est
```java
public static void main(String[] arg),
```
il s'agit *d'arg[0])* ;
* au moment d'exécuter, faite comme précédemment, mais choissez dans le menu déroulant de Run as, l'item Run Configuration ; dans la fenêtre obtenue par Run configurations, complétez en choisissant un nom pour la configuration, en notant le nom du projet (TP1A) et la classe contenant le programme principal (etudiant.TestEtudiant) ; puis, cliquez sur l'onglet Arguments et inscrire le nom choisi pour l'élève dans Program arguments, enfin cliquez sur Run ; les fois suivantes, vous pourrez exécuter le programme avec la petite flèche qui figure dans la barre en haut d'Eclipse (si vous ne voulez pas conserver les arguments de la méthode main).   
Si vous êtes arrivé au bout de ce premierTP, bravo, vous êtes prêt pour continuer !
