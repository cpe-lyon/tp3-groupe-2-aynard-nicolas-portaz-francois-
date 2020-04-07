**Exercice 2 - Prise en main de l'interpreteur de commandes**
============

*Manuel*
------------

**2.1**
La commande which sert à localiser une commande, il determine le path (chemin d'accès d'un fichier).

**2.2**
Pour rechercher un terme dans le manual, il faut utiliser /"mot_recherché". Pour naviguer de termes en
termes il faut utiliser la commande "n" pour next et "N" pour previous.

**2.3**
Pour quitter la page du manuel, il suffit d'utiliser la commande "q" comme indiqué sur le terminal.

**2.4** 
La section 6 parle des jeux, économiseurs d'écran et gadgets.


*Navigation dans l'arborescence des fichier*
------------
Commande pour naviguer dans les fichiers : 
*ls : afficher le contenu du dossier
*cd :aller dans le dossier 
*cd .. : aller dans le dossier parent
*cd - revenir dans le précédent dossier
*cd / : aller au dossier racine (root)

**2.5**
Quand on essaie d'accéder au dossier root on a un refus d'accès (permission denied).

**2.6**
Lorsque l'on met sudo, la console dit que cd est inconu car sudo permet de lancer des programmes en mode admin et cd n'est pas un programme , juste une commade bash.

**2.8**
La commande sudo rm Nom_Du_Fichier permet de supprimer un fichier et uniquement un fichier et non pas un dossier (directory).

**2.9**
Pour supprimer un dossier, il faut utiliser la commande rmdir Nom_Du_Dossier.

**2.10**
La commande précédente ne marche que si le dossier est VIDE.

**2.11**
La commande pour supprimer un dossier et son contenu est : sudo rm -r nomDuDossier.


*Commandes importantes*
------------
**1**
Quelle commande permet d’aﬀicher l’heure ? A quoi sert la commande time ?  
Pour afficherl'heure : date .  

**2**
Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ?  
ls : afiche le contenu. 
la : raccourci de ls -A -> affiche aussi ceux commençant par un .   

**3**
Où se situe le programme ls?  
Le programme ls se situe dans /usr/bin/ls.  

**4** 
Essayez la commande ll. Existe-t-il une entrée de manuel pour cette commande ? Utilisez les com-
mandes alias ou alias pour en savoir plus sur la nature de cette commande.  
La commande ll est un aliais de ls (ls -l), elle sert à donner plus d'infomation sur la liste des fichiers comme la date par exemple. Il n'existe pas d'entrée dans la manuel conercant cette commande.

**5**
Quelle commande permet d’aﬀicher les fichiers contenus dans le dossier/bin?  
La commande pour afficher ce qu'il y a dans bin est : ls /bin. 

**6**
Que fait la commande ls ..   
montre ce qu'il y a dans le répertoire parent.  

**7**
Quelle commande donne le chemin complet du dossier courant :    
pwd 

**8**
Que fait la commande echo 'yo' > plop exécutée 2 fois ?  
La commande crée le fichier plop et met yo dedans. (Si on le refait, alors il supprimera ce qu'il y a dans plop pour ne mettre uniquement yo.

**9**
Que fait la commande echo 'yo' >> plop exécutée 2 fois ?  
Pareil que au-dessus mais au lieu de supprimer cequ'il y a dans le fichier il ajoute à la fin de celui-ci.

**10**
A quoi sert la commande file ? Essayez la sur des fichiers de types différents. 
File détermine le type du fichier.

**11**
Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier
avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi :
qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?  
On observe qu'il y a la même chose dans le fichier toto même quand on change. La suppression de titi n'a aucun impact sur toto.

**12**
Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le
contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle
conséquence cela a-t-il sur tutu ?  
Le changement du contenu de l'un change le contenu de l'autre. Si on supprime le fichier de base l'autre fichier n'existe plus (le lien existe encore). Lors d'un ls, le fichier apparaît en rouge.  

**13**
Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et
reprendre le défilement à l’écran 2nd paragraph.  
CTRL S pour stopper. 
CTRL Q pour reprendre. 

**14**
Aﬀichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.  
head -5 <file>  tail -n 5 <file>  head -20 <file> | tail -n 10

**15**
Que fait la commande dmesg | less ?  
less : lit un fichier page par page. 
dmesg : afficher les logs (messages) du noyau. 
dmesg | less affiche les messages du noyau page par page. 

**16**
Aﬀichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’aﬀicher la page de manuel de ce fichier ?  
/etc/passwd stocke les informations essentielles requises lors de la connexion. 
man 5 passwd affiche la page manuel de ce fichier.

**17**
Aﬀichez seulement la première colonne triée par ordre alphabétique inverse. 
cut -c1 /etc/passwd | sort -r

**18**
Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?  
getent passwd | wc -l

**19**
Combien de pages de manuel comportent le mot-clé conversion dans leur description ?  
man -k conversion permet d'afficher toutes les utilisations du mot clé conversion dans l'ensemble du manuel.
ou apropos conversion
Conversion est dans 3 pages du manuel.  

**20**
A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine.  
find -name "passwd"
 
**21**
Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null. 
find -name "passwd" > list_passwd_files.txt 2>/dev/null

**22**
Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment. 

**23**
Utilisez la commande locate pour trouver le fichier history.log.  
sudo apt install mlocate  
locate history.log

**24**
Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il? Pourquoi?  
Locate ne trouve pas le fichier car la commande ne cherche pas directement dans l'arbprescence mais dans une base de donnés contenant la liste des fichiers exsitants.









