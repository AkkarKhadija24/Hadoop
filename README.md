# Hadoop
## An implementation of the Map-Reduce model in Java.

Pour tester notre travail en mode distribué, il faut changer les noms des deux premiers éléments de la ligne 22 de la classe 
[HdfsClient]() dans le package hdfs et dans la ligne 12 dans la classe [JobLauncher]() dans le package daemon par les noms des machines à utiliser. Sinon, si c'est en local, il faut les définir tous en 'localhost'.

### Compilation dans src à l’aide de la commande:

```bash
javac /.java
```

### Lancement des serveurs en attribuant à chacun un port via la ligne de commande:

#### Dans le terminal de la première machine, effectuer la commande :

```bash
java -cp src hdfs.HdfsServer
```
Écrire le numéro du port 3158

#### Dans le terminal de la deuxième machine, effectuer la commande :

```bash
java -cp src hdfs.HdfsServer
```
Écrire le numéro du port 3282

### Lancement des workers en attribuant à chacun un port via la ligne de commande:

#### Dans le terminal de la première machine, effectuer la commande :

```bash
java -cp src daemon.WorkerImpl
```
Écrire le numéro du port 8000

#### Dans le terminal de la deuxième machine, effectuer la commande :

```bash
java -cp src daemon.WorkerImpl
```
Écrire le numéro du port 8001

### Lancement de notre JobLauncher avec le nom de notre fichier de test en tant qu'argument:

#### Dans le terminal de la 3ème machine, effectuer la commande :

```bash
java -cp src application.MyMapReduce PATH/filesample.txt
```
(pour PATH c’est le path Absolu vers le filesample.txt existant dans
le dossier data)

#### Dans le dossier data dans la troisième machine, vous trouverez un fichier appelé [resultat.txt] contenant le résultat du traitement.
