<!DOCTYPE html>
<html>
  <head>
    <title>aQRootG3</title>  
	<link rel="stylesheet" href="style.css">
  </head>
  
  <body>
    <h1>Activer l'accès telnet via la commande QRCode Injection pour Aqara G3</h1>

	<p align="center" width="100%">
    <img src="https://user-images.githubusercontent.com/1288525/152621650-993c5630-c749-4758-9609-e5421df4d7ff.png"> 
	<h1> Clique sur ce bouton pour installer aQRootG3 </h1>
	  <input type="button" onclick="window.location.href = 'https://github.com/Wh1terat/aQRootG3/blob/main/aQRootG3.py';" value="aQRootG3" />
	 
  </body>
  
 <h2> Introduction </h2>
 
 <p> J'ai été déçu de voir que la caméra Aqara G3 n'était pas livrée avec telnet activé, j'ai donc réussi à récupérer une copie d'une mise à jour du micrologiciel pour une bonne analyse statique qui a confirmé qu'aucune des méthodes précédentes n'allait fonctionner.

En passant par "ha_master", j'ai vu que l'une des variables transmises par le qrcode de configuration est lancée via sprintf en tant que "nslookup %s" et ensuite transmise à popen (yay).

Obtenir telnet était assez trivial, obtenir telnet persistant en une seule fois dans le tampon sprintf de 132 caractères sur un système de fichiers en lecture seule était un peu plus difficile.

Heureusement, une autre variable qrcode (b alias bind_key) a un tampon plus grand, nous y stockons donc des données qui peuvent ensuite être utilisées par la charge utile principale. </p>

<h2>Installation aQRootG3 </h2>

 <p> Pour l’installation de telnet ci-joint avec le dossier aQRootG3 se prémunir de python et du module segmo installé sur votre poste !</p>
 <p>Ensuite lancée l’inviter de commande (cmd) en administrateur (pour avoir tous les droits)</p>
 <p>Maintenant faut se déplacer à la racine pour trouver votre répertoire ou est placé le fichier aQRootG3 </p> 
 <p>La commande pour ce déplacer à la racine est (cd..) 2fois  ensuite la commande (dir) pour localiser votre dossier ensuite faire (cd [nom du dossier])</p>
 <p> Une fois placer au bon endroit exécutait cette commande( py aQRootG3.py [-h] ssid pwd [nom du fichier]) </p>

 <p>[-h] et [nom du fichier] peuvent vous induire en erreur ils sont facultatifs et peuvent poser problème </p>

   <p>SSI = identifiant 
      Pwd=mot de passe </p>
         

 <h2><center>Explication</h2></center>
 
 <p><center>1-Réinitialisez la caméra en maintenant 10 seconde sur le bouton.</p></center>
 <p><center>2-Lorsque vous y êtes invité (bien que probablement en chinois), scannez le code QR que vous avez généré.</p></center>
 <p><center>3-Cela donnera un message d'échec (en raison d'un bind_key invalide).</p></center>
 <p><center>4-Ajoutez l'appareil à la maison Aqara comme d'habitude.</p></center>
 
 <h1> Il faut vous munir de putty pour pouvoir continuer </h1>
 <img src="https://pic.clubic.com/v1/images/1498701/raw"> 
 <p> Clique sur ce bouton pour installer Putty </p>
	  <input type="button" onclick="window.location.href = 'https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html';" value="PUTTY" />
 
 <p>1-Rentrer l'adresse ip de la camera </p>
 <p>2-Choissisez bien le mode telnet </p>
 <p>3-Cliquez sur open </p>
 
Un invité de commande va s'ouvrir, il vous reste plus qu'à suivre la fin du processus
 
 <p>Connexion Camera-Hub-G3-BEEF : root </p>
   <p>Mot de passe : Normalement il n'y a n'a pas besoin car on se log avec root</p>
   <p>  1 ulimit=256 ~ # uname -a ( commande à rentrer dans l'inviter de commande putty)</p>
     <p> Linux Camera-Hub-G3-BEEF 4.9.84 # 67 SMP PREEMPT Lundi 6 septembre 17:51:23 CST 2021 armv7l GNU/Linux  (si ce message apparaît en fin d'exécution vous avez réussi )</p>
  
  
  <p>Profitez.</p>
</html>
