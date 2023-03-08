# Écrire à l'écran le premier argument de la ligne de commande
Dans l'en-tête d'une méthode main apparait ce qui s'appelle un paramètre ou un argument qui est ci-dessous nommé arg :
    public static void main(String[] arg)
On peut nommer cet argument selon son propre choix. L'en-tête pourrait aussi être :
    public static void main(String[] listeArguments)
ou tout autre identificateur à la place de listeArguments, ou de arg plus haut. Le reste de l'en-tête de la méthode main est obligatoire. Cet argument est de type tableau de String ou encore tableau de chaînes de caractères, mais pour l'instant il suffit de savoir que si son nom est arg, le premier d'entre eux est accessible dans le programme par arg[0], le deuxième par arg[1] et ainsi de suite.
Grâce à ce paramètre, on peut "passer des arguments à la méthode main", ce qu'on fait quelquefois, cela dépend du choix du programmeur.

## Première partie
On souhaite dans cet exercice passer un argument à la méthode main, qui sera un mot. Supposons que la méthode main soit écrite dans une classe qui s'appelle EcrireArgument qu'on veuille passer le mot "bonjour".
Si on exécute le programme directement sur une ligne de commande, dans une fenêtre d'exécution, on tapera la commande :
    java EcrireArgument bonjour
Si on travaille avec Eclipse, il faut donner les arguments avant d'exécuter le programme (en utilisant, si votre version d'Eclipse est en anglais, "Run Configurations", puis en choisissant l'onglet Arguments pour préciser les arguments dans "Program arg", avec notre exemple, bonjour).
Cette première partie de l'exercice consiste à faire en sorte que, à l'exécution, l'argument passé par la ligne de commande soit écrit en sortie du programme (par System.out.println(...). Si l'argument est "bonjour", le programme doit écrire :
`bonjour`

## Seconde partie
Cette partie d'exercice ne peut se faire que quand on a appris à manipuler des boucles et lorsqu'on à quelques connaissances sur les tableaux. Si vous êtes débutant, vous pouvez bien sûr regarder le corrigé dès maintenant et le tester.
L'exercice consiste à faire en sorte que, à l'exécution, tous les arguments passés par la ligne de commande soient écrits en sortie du programme (par System.out.println(...), un par ligne. Si les arguments sont "Bonjour" et "Salut", le programme doit écrire :
```java
Bonjour
Salut
```

Si on travaille directement en ligne de commande, si la méthode main est écrite dans une classe nommée EcrireArguments, la commande est alors :
    `java EcrireArguments Bonjour Salut`
