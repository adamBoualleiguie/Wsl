# Wsl
## Article sur WSL : la nouvelle technologie de virtualisation

 
# I- Partie Théorique :
Avant d'introduire cette technologie nous jetons un coup d'œil sur la technologie de virtualisation
## 1/ La virtualisation
La virtualisation est une technologie permettant de créer et d’exécuter une ou plusieurs représentations virtuelles d’un ordinateur ou de ses différentes ressources sur une même machine physique.

- [x] cette technologie est conçue pour des besoins d'optimisation de productivité et des couts logistiques.

![Image of Yaktocat](https://base.imgix.net/files/base/ebm/ehstoday/image/2019/03/ehstoday_3561_problemsolution.png?auto=format&fit=crop&h=432&w=768)

### exemple
par exemple  un serveur qui  a une  capacité de calcul et de stockage puissante :computer:

### une situation: 
_**par exemple ce serveur doit lancer 2 services mais chacun de ces services se déroule sur 2 différente type de O.S (système d'exploitation) 
n'oubliant pas que théoriquement ce serveur a la capabilité de les lancer à la fois le seul obstacle c'est que ce dernier ne peut pas exécuter les 2 différents systèmes d'exploitation simultanément**_

 La **Virtualisation** étais la solution !

 Grâce à cette technologie  , le serveur peut  lancer des systèmes d'exploitation pour avoir 2 services qui fonctionnent simultanément et correctement 

## 2/ les domaines de virtualisation 

- cette technologie touche beaucoup de domaines on parle : 
  - virtualisation de serveur
  - virtualisation de réseau
  - virtualisation de stockage
  - La virtualisation d’application
  - etc..

## 3/ WSL Windows Subsystem Linux 
###      définition générale 
 Windows Subsystem for Linux (WSL) est une couche de compatibilité permettant d'exécuter des exécutables binaires Linux (au format ELF) de manière native sur Windows 10 et Windows Server 2019.

###      concept
- [x] **wsl est un projet supporté par windows** 

chaque système d'exploitation possède un noyau (kernel) ; il gère les ressources de l’ordinateur et permet aux différents composants — matériels et logiciels — de communiquer entre eux.

la  façon traditionnelle ( la virtualisation ) a un certain étage d'exécution 
    noyau machine virtuelle --> partie software du os host --> noyau os host --> partie  hardware 

d'où l'innovation du wsl  le noyau windows  possède maintenant  une partie  qui est le kernel linux (debian)
C'est-à-dire   windows  peut maintenant  lancer les commandes  linux directement  d'une  façon native ; l'exécution des commandes et "Tools" linux s'exécute plus rapidement à travers la technologie wsl plus que l'ancienne méthode de machine virtuelle

linux command --> wsl(partie du noyau windows) --> hardware 

## comparaison entre wsl et virtual machine 
 - [x]  **le boot d'un system d'exploitation  sur wsl est plus rapide qu'une  machine virtuelle** 
 - [x] **wsl partage les sources physiques** 

 - [ ] **la machine virtuelle réserve une partie des  ressources hard**



### exemple

un pc :computer:  de 16gb ram peut virtualiser une machine virtuelle avec des caractéristiques de 8 go de ram si on lance cette machine 8gb seront réservées  et la partie  host  sera lente par contre si on lance Ubuntu/wsl windows et Ubuntu partagent les ressources

## wsl et la vie de developement 
 chaque  développeur  ce trouve souvent dans une situation ou il veut exploiter un service ou un software qui n'est pas supporté par Windows 
 on peut parler d'un exemple  simple  pour  éclaircir  l'idée 
chaque  developpeur doit utiliser git  pour le travail  en groupe 
 pour chaque push il peut envisager 2 méthodes d'authentification 
  par user and pw  ou bien  par ssh 
l'authentification par ssh    est  un peut  difficile a maintenir sous  Windows 
    a traver putty et  etc ..
  un développeur qui utilise wsl  sa devient  plus simple  





# installation du wsl et mise a jour vers wsl2 

##  exigence : 
 -  version du Windows  minimale :   Windows 2004  19041.264
pour vérifier il suffit  de :  
 2. wind+r
 3. taper : `winver`
 - la technologie de virtualisation doive être activer de coté bios  pour  vérifier 
  ouvrir  votre gestionnaire de tache  voir  capture 
  
 
## les étapes : 
 1.  ouvrir  `windows features` 
 2.  activer `windows subsystem for linux` et `virtual machine platform`
 ***apres redemarage de votre pc  vous*** 
 3.  ouvrir windows store et telecharger une version linux example : **kali linux**  
 4.  si vous lancer maintenant la terminal du kali  vous  trouver une  erreur : 
      add image 
 5. la solution  c'est d'installer le patch de wsl2  telecharger de ce lien et l'installer
  [wsl2 kernel](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
 6. mainteneant  vous pouver creer  votre utilisateur et mot de passe  dans  kali linux et vous beneficier de tout les service console du linux 
 ## autre etapes 
  - dans powershell 
    - `wsl -l -v ` >pour voir liste des distrubitions installées et la version wsl qui supporte 
    - `wsl --set-version kali-linux 2 ` > kali linux va fonctionner a traver la version 2 de wsl 
    - `wsl --set-default-version 2 `> wsl2 est devenue la version par default pout toutes les distrubition (future installée ) 

# une interface graphique pour notre distribution ! 
 les distribution linux proposent un kernel puissant  riche des services et applications 
  mais  n'oubliant  jamais  qu'une interface graphique  est neccessaire pour autre application non-console 
  la solution  est  **Win-KeX**
 **Win-KeX fournit une expérience de bureau Kali pour le sous-système Windows pour Linux (WSL 2)**
visiter la  du projet pour mieux comprendre le concept [ page officiel](https://www.kali.org/docs/wsl/win-kex/) du projet pour mieux comprendre le concept
en générale  **Win-KeX**  assure  une interface graphique gui   évitant seulement une "terminale"  ou invite de commande .
# intégration du Win-KeX

 
note !  Win-KeX  ne supporte pas ~~wsl1~~

 1. `sudo apt upgrade && sudo apt install kali-win-kex -y`
  cette installation   va prendre un moment soyer patient ! 
 2. `sudo apt-get install dbus-x11`  ajouter cette commande 
 
 ## `>kex `   ouvrir l'interface graphique de kali linux ! 
 ## `>kex --esm ` ouvrir l'interface graphique  par RDP (remote desktop protocole ) 

  note : les articles suivantes vont expliquer d'autre truck  en se basant a la technologie wsl  