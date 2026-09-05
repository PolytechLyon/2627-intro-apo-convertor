# Convertisseur en format dot

Ceci est une application qui convertit un fichier texte représentant un graphe en un fichier au format dot.

Par défaut, le fichier d'entrée est celui qui porte le nom `graph.txt`. Le nom de fichier peut aussi être fourni en premier argument lors de l'exécution.

Le nom du fichier de sortie est le même que celui du fichier d'entrée, à une seule différence : ce qui suit le premier `.` est remplacé par `.dot`.

### Format du fichier d'entrée
Le fichier d'entrée décrit les liens entre les noeuds.
Il a le format suivant :
1. Une liste des noms de tous les noeuds. Les noms sont séparés par des retours à la ligne.
2. Une ligne vide séparant les noeuds de leurs liens.
3. Une liste des liens entre les noeuds. Les liens sont séparés par des retours à la ligne.
   Chaque lien est composé des éléments suivants, dans l'ordre :
   * L'index du noeud source, dans la liste des noeuds, en commençant à zéro,
   * L'index du noeud cible, dans la liste des noeuds, en commençant à zéro,
   * Le poids du lien.

Les liens sont orientés : chaque ligne décrit un lien allant du noeud source vers le noeud cible uniquement. Pour représenter un lien bidirectionnel, il faut fournir deux liens.

## Compilation et exécution

```
mvn compile exec:java
```

Pour utiliser un autre fichier d'entrée que `graph.txt` :

```
mvn compile exec:java -Dexec.args="mon_fichier.txt"
```