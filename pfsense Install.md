# Installation du firewall pfSense

## Installer pfSense et s'assurer d'une configuration réseau valide permettant aux machines internes d’accéder à l'extérieur

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Edit%20mdp.png width ="600" height ="300">

VM | Mode d'accès réseau | IP
:---:|:---:|:---:
pfsense | Bridge | 192.168.2.1
Windy(poste d'administration)| Interne, Lan_V | 192.168.2.3
Shinra (client) | Interne, Lan_VM | 192.168.2.4

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Windi%20reconfigur%C3%A9%20pour%20pfsense_r.%20interne%20lan_vm.png width ="600" height ="300">

<br>

## Tester que la machine client peut accéder à l'extérieur

* Shinra, Machine Cliente : 

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Shinra%20Ping%20IP%20Google.png width ="600" height ="300">

<br>

## Mettre en place une règle de filtrage réseau pour interdire à la machine client de sortir du réseau interne

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Pfsense%20rule%20created.png width ="600" height ="70">

<br>

## Vérifier que la machine client ne peut plus communiquer avec l'extérieur, mais que le poste d'administration peut encore communiquer avec l'extérieur

* Shinra, Machine Cliente :

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Shinra%20Ping%20Google%20after%20rule%20created.png width ="600" height ="70">

<br>

* Windy, Poste d'administration

<img src=https://github.com/Fairskip/Pfsense-Install/blob/main/Windy%20ping%20google%20after%20rule%20created.png width ="600" height ="200">

<br>

## Expliquer la règle de filtrage mise en place dans le bloc de texte solution de la quête

La règle spécifie que la machine (Shinra) dont le IP est 192.168.2.4 du réseau Lan ne peut plus aller à l'extérieur car on lui a bloqué l'accès via les protocoles de sécurités qu'on lui ait retirés. En gros, pour passer la douane, il lui faut les papiers d'identifications et de sécurité. Pas de papiers, pas de communication possible hors du lan.
