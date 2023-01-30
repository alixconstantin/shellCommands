# shellCommands
Shell command list

💧[**man**]💧

Pour obtenir le manuel d'une commande :  
`man COMMANDE `

  

💧[**pwd**]💧

Pour savoir ou on se trouve a tout instant :  
`pwd`



💧[**cd**]💧

Pour changer de dossier (se deplacer) :  
`cd DIRECTORY`

D'autres facons d'utiliser cd :  

    Revenir au dossier que l'on vient de quitter :  
    `cd -`

    Aller au dossier parent :  
    `cd ..`

    Aller dans la home (~) :  
    `cd`



**[ls]**

Lister le contenu d'un dossier :  
`ls DIRECTORY`

Pour le contenu du dossier dans lequel je suis :  
`ls`

Pour avoir des details sur les fichiers (date, droits, a qui ils appartiennent, taille) :  
`ls -l`

Pour voir aussi les fichiers et dossiers caches (qui ont un nom commencant par un ".") :  
`ls -a`

On peut combiner les options :  
`ls -l -a`
`ls -la`


**[mkdir]**

Creer un dossier :  
`mkdir NOM_DOSSIER`


**[touch]**

Creer un fichier :  
`touch NOM_FICHIER`


**[cat]**

Affiche le contenu d'un fichier :  
`cat NOM_FICHIER`


**[cat] -e**

Affiche les caractères non affichable
par exemple le "$" qui indique les retours a la ligne 


**[cp]**

Copier-Coller :  
`cp FICHIER NOUVEAU_FICHIER`


**[mv]**

Deplacer, renommer :  
`mv ANCIEN_CHEMIN NOUVEAU_CHEMIN`
`mv ANCIEN_NOM NOUVEAU_NOM`


**[rm]**

Supprimer un fichier :  
`rm FICHIER`


**[rmdir]**

Supprimer un dossier (s'il est vide) :  
rmdir DOSSIER


**[rm]** -r

Supprimer recursivement (dossiers, sous-dossiers, fichiers, etc) :  
`rm -r DOSSIER`

Gestions d'utilisateurs / Droits
Les fichiers/dossiers appartiennent a des utilisateurs, sur Linux.
Lorsque vous creez un fichier, il vous appartient.
Lorsque vous listez le contenu d'un dossier, vous pouvez voir votre nom d'utilisateur sur vos fichiers.
Les utilisateurs sont tries par groupe.
Les droits des utilisateurs sur les fichiers sont les suivants :

    Lecture (r comme read) : Voir le contenu des dossiers/fichiers
    Ecriture (w comme write) : Modifier le contenu des dossiers/fichiers
    Execution (x comme execution) : Executer le programme (si c'en est un), se deplacer dans un dossier

La commande ls -l nous donne les details des droits de chaque fichiers. Exemple :  

drwxr-xr-x 2 db0 db0 4096 2010-10-15 12:07 dossier1  
drwxr-xr-x 2 db0 db0 4096 2010-10-15 12:07 dossier2  
drwxr-xr-x 2 db0 db0 4096 2010-10-15 12:07 dossier3  
-rw-r--r-- 1 db0 db0    0 2010-10-15 12:06 fichier1  
-rw-r--r-- 1 db0 db0    0 2010-10-15 12:07 fichier2  
-rwxr--r-- 1 db0 db0    0 2010-10-15 12:07 fichier3  
-rw-r--r-- 1 db0 db0    0 2010-10-15 12:07 fichier4  
-rw-r--r-- 1 db0 db0    0 2010-10-15 12:07 fichier5  
-rw-r--r-- 1 db0 db0    0 2010-10-15 12:07 fichier6  
Les droits sont tout a gauche.  
Le premier caractere indique quel type de fichier c'est :  

'-' = fichier banal  
'd' = dossier  
'l' = lien symbolique (grosso modo equivalent aux raccourcis sur windows)  
'c', 'b', 'f' = fichiers "speciaux" (fifo, peripherique, etc)  
Les trois caracteres suivant sont les droits pour l'utilisateur a qui appartient le fichier   (l'owner) :  
r ou - = droits de lecture ou pas  
w ou - = droits d'ecriture ou pas  
x ou - = droits d'execution ou pas  
Les trois suivants sont pour le groupe de l'utilisateur.  
Et enfin, les trois derniers sont pour tout les autres.  
Pour changer les droits d'un fichier, il faut faire un peu de calcul :  

r = 4  
w = 2  
x = 1  
(C'est exprime en octal, mais on s'en fout pour l'instant).  
Prenons un fichier au hasard qui aurait les droits suivant :  
-rwxrw-r--  
Droits user = rwx = 4 + 2 + 1 = 7  
Droits groupe = rw- = 4 + 2 + 0 = 6  
Droits tout le monde = r-- = 4 + 0 + 0 = 4  
---> Les droits se ce fichier sont donc : 0764.  
On met un 0 devant pour indiquer que c'est de l'octal (base 8).  


**[chmod]**

Pour changer les droits d'un fichier :  
`chmod DROITS FICHIER`  
En remplacant DROITS par le code calcule comme precedemment.


**[chown]**

Pour changer le proprietaire d'un fichier :  
`chown NOUVEAU_PROPRIETAIRE:GROUPE FICHIER`    
(:GROUPE est facultatif)  

ACL
Il existe un systeme de droit plus "puissant" : les acl. Ils se modifient avec la commande :  

`[fs] setacl`  

Sur Linux, il existe un systeme de Super Utilisateur.
Cet utilisateur est tout puissant. Il a tout les droits sur votre machine.
S'il il veut, il peut tout supprimer et detruire votre OS ! Niark niark niark.
Cet utilisateur s'appelle le root.
C'est assez dangereux d'utiliser son ordinateur en tant que root, donc on le fait que quand on doit faire des actions tres particulieres.
  
  
**[su]**

Pour obtenir un shell en tant que root :  
`su`  
(comme super user)


**[sudo]**

Pour lancer une seule commande en tant que root :  
    `sudo COMMANDE`  
(comme super user do)


**[su]**

Pour se connecter en tant qu'un autre utilisateur (pas forcement le root) :  
`su NOM_USER`


**[gcc]**

Pour compiler un fichier C et pouvoir l'executer :  
`gcc nom_du_fichier.c -o nom_de_l_executable`  
exécuter ce fichier en tapant `"./nom_de_l_executable".`  


**[echo]**

afficher du texte ou la valeur d'une ou plusieurs variables sur la sortie standard, souvent   utilisé pour afficher des messages pour l'utilisateur, pour afficher les valeurs de certaines   variables, pour construire des scripts de commandes, etc.  

 1. Afficher du texte :  
`echo "Hello World"`

1. Afficher la valeur d'une variable :  
`name="John"`
`echo "My name is $name"`

1. Afficher sans retour à la ligne :  
`echo -n "Hello"`

1. Afficher du texte sur la sortie d'erreur standard :  
`echo "Error message" >&2`

1. Répéter le texte plusieurs fois :  
`echo "Hello" && echo "Hello" && echo "Hello"`


**[less]**

 visualisation de fichiers en mode texte en ligne de commande. Les deux permettent d'afficher le  contenu d'un fichier par pages, de sorte que l'utilisateur ne soit pas submergé par une quantité excessive de texte sur l'écran :  

`less FICHIER`  

possibilité également de chercher en utilisant le / 


**[head]**

Affiche les 10 premières lignes d'un fichier :  
`head FICHIER`

pour les 3 premières ligne par exemple :  
`head -n 3 FICHIER`


**[tail]**

Affiche les 10 dernières ligne d'un fichier  :  
`tail FICHIER`

pour les 3 dernières ligne par exemple :  
`tail -n 3 FICHIER`


**[grep]**

permet de filtrer le contenu des fichiers et de n'afficher que les lignes contenant le texte spécifié :  
`grep "mot" FICHIER`

pour rechercher du texte dans plusieurs fichiers en spécifiant plusieurs noms de fichiers :  
`grep "motif" FICHIER_1 FICHIER_2`

retirer toutes les lignes qui contienne le mot :  
`grep "mot" -v  FICHIER`

filtre sans tenir compte des minuscules/majuscules :   
`grep "mot" -i FICHIER`

ETC. 