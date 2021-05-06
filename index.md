# Wsl
## Article sur WSL : la nouvelle technologie de virtualisation


# I-Partie Théorique :
Avant d'introduire cette technologie nous jetons un coup d'oeil sur la technologie de virtualisation
## 1/ La virtualisation
La virtualisation est une technologie permettant de créer et d’exécuter une ou plusieurs représentations virtuelles d’un ordinateur ou de ses différentes ressources sur une même machine physique.

- [x] cette technologie est conçue pour des besoins d'optimisation de productivité et des couts logistiques.

![Image of Yaktocat](https://base.imgix.net/files/base/ebm/ehstoday/image/2019/03/ehstoday_3561_problemsolution.png?auto=format&fit=crop&h=432&w=768)

### exemple
par exemple  un serveur qui  a une  capacité de calcul et de stockage puissante :computer:

### une situation: 
_**par exemple ce serveur doit lancer 2 services mais chacun de ces services se déroule sur 2 différente type de O.S (système d'exploitation) 
n'oubliant pas que théoriquement ce serveur a la capabilité de les lancer à la fois le seul obstacle c'est que ce dernier ne peut pas exécuter les 2 différents systèmes d'exploitation simultanément**_

 La **Virtualisation** etais la solution !

 Grâce à cette technologie  , le serveur peut  lancer des systèmes d'exploitation pour avoir 2 services qui fonctionnent simultanément et correctement 

## 2/ les domaines de virtualisation 

- cette technologie touche beaucoups de domaines on parle : 
  - virtualisation de serveur
  - virtualisation de réseau
  - virtualisation de stockage
  - La virtualisation d’application
  - etc..

## 3/ WSL Windows Subsystem Linux 
###      definition generale 
 Windows Subsystem for Linux (WSL) est une couche de compatibilité permettant d'exécuter des exécutables binaires Linux (au format ELF) de manière native sur Windows 10 et Windows Server 2019.

###      concepte
- [x] **wsl est un projet supporté par windows** 

chaque système d'exploitation possède un noyau (kernel) ; il gère les ressources de l’ordinateur et permet aux différents composants — matériels et logiciels — de communiquer entre eux.

la  façon traditionnelle ( la virtualisation ) a un certain étage d'exécution 
    noyau machine virtuelle --> partie software du os host --> noyau os host --> partie  hardware 

d'ou l'innovation du wsl  le noyau windows  possède maintenant  une partie  qui est le kernel linux (debian)
C'est-à-dire   windows  peut maintenant  lancer les commandes  linux directement  d'une  façon native ; l'exécution des commandes et "Tools" linux s'exécute plus rapidement à travers la technologie wsl plus que l'ancienne méthode de machine virtuelle

linux command --> wsl(partie du noyau windows) --> hardware 

## comparaison entre wsl et virtual machine 
-  [x] **le boot d'un system d'exploitation  sur wsl est plus rapide qu'une  machine virtuelle ** 
-  [x] **wsl partage les sources physiques** 
-  [] **la machine virtuelle réserve une partie des  ressources hard**
### exemple

un pc :computer:  de 16gb ram peut virtualiser une machine virtuelle avec des caractéristiques de 8 go de ram si on lance cette machine 8gb seront réservées  et la partie  host  sera lente par contre si on lance ubuntu/wsl windows et Ubuntu partagent les resources

## wsl et la vie de developement 
 chaque  developpeur  ce trouve souvent dans une situation ou il veut exploiter un service ou un software qui n'est pas suporté par windows 
 on peut parler d'un exemple  simple  pour  eclairir  l'idee 
chaque  developpeur doit utiliser git  pour le travail  en groupe 
 pour chaque push il peut envisager 2 methode d'authentification 
  par user and pw  ou bien  par ssh 
  la prcessur de  ssh  authentification   est  un peut  difficile a maintenir sous  windows 
    a traver putty et  etc ..
  un developpeur qui utilise wsl  sa devient  plus simple  










```
  ```diff
      -powershell/system32>``` choco install wsl2 --params "/Version:2 /Retry:true"

```
```diff
-test   1
```











