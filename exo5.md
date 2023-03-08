# Le jeu de chifoumi
Le jeu de Chifoumi s'appelle aussi Caillou-Ciseaux-Papier. Il se joue entre deux joueurs, en général avec les mains. Simultantément, les deux joueurs font un signe avec les mains qui représente soit un caillou, soit des ciseaux, soit un papier.

Nommons A et B les deux joueurs.

Si les deux joueurs ont fait le même signe, on considère que c'est un cas d'égalité, aucun des deux joueurs ne marque un point.   
Si le joueur A a joué Caillou et le joueur B Ciseaux, A marque un point car "le caillou émousse les ciseaux", et réciproquement.   
Si le joueur A a joué Papier et le joueur B Caillou, A marque un point car "le papier enveloppe le caillou", et réciproquement.   
Si le joueur A a joué Ciseaux et le joueur B Papier, A marque un point car "les ciseaux coupent le papier", et réciproquement.   
On donne un nombre de points à atteindre (3 ou 5 par exemple) et le premier joueur qui a atteint ce nombre de points a gagné.   
Il s'agit de programmer ce jeu.   

Toutes les classes concernant ce jeu seront mises dans un paquetage nommé chifoumi.

## Premier temps   
Effectuez les opérations suivantes (on suppose que vous travaillez sous Eclipse) :   
* créez un paquetage nommé chifoumi ;
 
* dans le menu à gauche, cliquez avec le bouton de gauche sur chifoumi, puis avec le bouton de droite, choisir new puis Enum ; vous obtenez une fenêtre dans laquelle vous indiquez que le nom est Choix ; vous validez avec finish ; vous obtenez un fichier dans lequel vous remplacez le code qui se trouve par défaut en recopiant le code ci-dessous :
package chifoumi;
```java
public enum Choix {
    CAILLOU,  CISEAUX, PAPIER;
}
```

On définit ainsi ce qu'on appelle un type énuméré ; on pourra utiliser les trois valeurs de ce type énuméré en les nommant : `Choix.CAILLOU`, `Choix.CISEAUX` et `Choix.PAPIER`. On pourra avoir des variables de types Choix ; elles pourront uniquement contenir une des trois valeurs énumérées.   
 
* créez un nouveau fichier dans le paquetage chifoumi pour une classe de nom IHMSaisie ; vous obtenez un fichier dans lequel vous remplacez le code qui s'y trouve par défaut en recopiant le code ci-dessous :
package chifoumi;
```java
import javax.swing.JDialog;
import javax.swing.JOptionPane;

public class IHMSaisie extends JOptionPane {
	final static long serialVersionUID = 1;
	JDialog dialogue;
	Choix[] choix = {Choix.CAILLOU, Choix.CISEAU, Choix.PAPIER};
	public IHMSaisie(String nom) {
		setMessage(nom + ", que jouez-vous ?" );
		setOptions(choix);
		dialogue = createDialog(null, "chifoumi");
	}

	Choix proposerChoix() {
		dialogue.setVisible(true);
		return (Choix)getValue();
	}
}
```

Vous avez ainsi le code d'une classe qui, lorsqu'on invoquera sa méthode proposerChoix pour une de ses instances, fera surgir une petite fenêtre permettant de choisir entre CAILLOU, CISEAUX ou PAPIER.
 
* créez un nouveau fichier dans le paquetage chifoumi pour une classe de nom TestIHMSaisie ; vous obtenez un fichier dans lequel vous remplacez le code qui s'y trouve par défaut en recopiant le code ci-dessous :
package chifoumi;
```java
public class TestIHMSaisie {
	public static void main(String[] arg) {
		IHMSaisie saisie = new IHMSaisie("toto");
		Choix choix = saisie.proposerChoix();
		System.out.println("Le choix de toto est " + choix);
	}
}
```

Vous exécuterez alors la méthode main qui se trouve dans la classe TestInterfaceSaisie. Vous observerez le résultat.

## Deuxième temps   

Il s'agit maintenant de programmer le jeu entre deux joueurs, mais en ne faisant pour l'instant qu'un seul tour de jeu : les deux joueurs choisissent une seule fois chacun entre les trois possibilités, puis le programme conclut sur les trois cas possibles (égalité, l'un est gagnant, l'autre est gagnant). On utilisera la classe IHMSaisie et le type énuméré Choix définis ci-dessus.    
Vous créerez dans le paquetage chifoumi les trois classes suivantes.

* La classe Joueur - elle possède :
  * un attribut privé de type String pour le nom du joueur initialisé par le constructeur ;
  * un attribut privé de type int nommé score initialisé à 0 ;
  * un attribut privé de type IHMSaisie, nommé saisie, initialisé dans le constructeur de la classe Joueur avec le nom du joueur comme valeur du paramètre du constructeur de la classe IHMSaisie ;
  * un constructeur prenant en paramètre le nom du joueur ;
  * une méthode nommée crediter servant à augmenter de 1 la valeur du score ;
  * une méthode nommée choisir qui ne fait qu'invoquer la méthode proposerChoix de l'objet saisie et renvoie la valeur renvoyé par proposerChoix ;
  * un getter pour le score ;
  * une méthode ecrireScore qui écrit le score sur la sortie standard ; par exemple, si le nom du joueur est toto et si son score vaut 2, la méthode pourrait écrire :    
    ```Le score de Toto est 2```

 
* La classe JeuUnTour - elle possède :
  * deux attributs privés de type Joueur, pour les deux joueurs ;
  * un constructeur prenant en paramètres deux chaînes de caractères (instances de la classe String) qui :
    * construit les deux joueurs en leur donnant à chacun un nom en utilisant les deux paramètres ;
    * invoque la méthode jouer décrite ci-dessous ;
  * une méthode jouer qui :
    * invoque la méthode tour ci-dessous,
    * écrit sur la sortie standard le score de chacun des joueurs en invoquant pour chacune d'entre-eux leur méthode ecrireScore,
    * conclut en utilisant la méthode conclure ci-dessous ;
  * une méthode `tour` qui :
    * fait choisir une fois chacun des deux joueurs (avec leur méthode choisir),
    * récupère leurs choix respectifs,
    * si les choix des deux joueurs sont différents, crédite le score du joueur dont le choix l'emporte ; cette méthode nécessite l'utilisation d'une instruction conditionnelle ; si vous ne connaissez pas cette instruction, vous pouvez regarder ici. On compare deux éléments de type Choix avec ==. Si choix est de type Choix, on pourrait écrire, if (choix == Choix.PAPIER)...
  * une méthode conclure qui sert à conclure sur le gagnant. Cette méthode utilisera sans doute une instruction conditionnelle.

 
* La classe LanceJeuUnTour - cette classe contient une méthode main qui instancie la classe JeuUnTour en indiquant au constructeur de la classe LanceJeuUnTour deux arguments de la méthode main servant à nommer les deux joueurs.

## Troisième temps

On veut faire en sorte que le joueur qui gagne soit le premier joueur ayant atteint un certain score donné à l'avance. On reprendra dans cet objectif une bonne partie du travail déjà fait. On conseille de créer une nouvelle classe nommée Jeu plutôt que de modifier la classe JeuUnTour.   
Le score à atteindre pourra être donné par un troisième argument de la méthode main et traduit alors de String à int par :
```    int scoreAAtteindre = Integer.parseInt(arg[2]);```

si le tableau des arguments de la méthode main s'appelle arg. La valeur du score à atteindre sera transmise à la classe Jeu par le constructeur de cette classe.

La classe Jeu différera de la classe JeuUnTour essentiellement pat la méthode jouer. Pour cela, il faudra sans doute utiliser une boucle qui peut être du genre.
```java
boolean fini = false;
    while (!fini) {
        ...
        ...
    }
```
Le signe ! se lit "not" ou "non". Le bloc suivant "while (!fini)" n'est exécuté que si fini vaut false. Lorsque le flux d'exécution arrrive à la fin du bloc, il remonte à "while (!fini)". Il conviendrait de donner à l'intérieur du bloc la valeur true à la variable fini lorsqu'un des joueurs a atteint le score à atteindre.
Une classe sera définie pour contenir une méthode main lançant ce nouveau jeu.
