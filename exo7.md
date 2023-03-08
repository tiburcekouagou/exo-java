## Modéliser un groupe d'élèves

Cet exercice fait suite à l'exercice Modéliser un élève, qu'il faut donc faire avant celui-ci.

Un groupe d'Eleve(s) (instances de la classe gestionEleves.Eleve précédemment définie) sera ici modélisé par la classe GroupeEleves du paquetage gestionEleves de la façon suivante.

La classe GroupeEleves posséde un attribut privé : une collection d'Eleve(s) nommée listeEleves, de type ArrayList<Eleve>.

La classe GroupeEleves ne possède pas de constructeur explicite.

La classe GroupeEleves possède aussi cinq méthodes publiques :

* La méthode d'en-tête
    ```java
  public int nombre()
  ```
    renvoie le nombre d'Eleve(s) contenus dans listeEleves
* La méthode d'en-tête
    ```java
  public ArrayList<Eleve> getListe()
  ```
    renvoie listeEleves.
* La méthode d'en-tête
    ```java
  public void ajouterEleve(Eleve eleve)
  ```
    ajoute l'Eleve reçu en paramètre à listeEleves.
* La méthode d'en-tête
    ```java
  public Eleve chercher(String nom)
  ```
    renvoie l'Eleve dont le nom est indiqué par le paramètre ; si plusieurs Eleve(s) ont même nom, la méthode renvoie le premier Eleve ayant ce nom contenu dans listeEleves ; si aucun Eleve n'a le nom indiqué, la méthode retourne null . On pourra utiliser la méthode equals de la classe String pour comparer une chaîne de caractères à une autre.
* La méthode d'en-tête
    ```java
  public void lister()
  ```
    écrit à l'écran la liste des Eleve(s). Elle utilise une ligne par Eleve ; elle utilise la méthode toString de la classe Eleve.    
Après avoir terminé la classe GroupeEleves, écrire un programme qui teste cette classe.
