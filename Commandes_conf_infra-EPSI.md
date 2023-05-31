# Configuration infra EPSI 2023

## Commandes pour configurer les switches (nom des switches)
$ ```conf t```
$ ```vlan 20```
$ ```name server```
$ ```end```

## Commandes pour configurer les ports des switchs + ajout de sports au vlan
$ ```conf t ```
$ ```int f0/1```
$ ```switchport mode access```
$ ```switchport access vlan 20```
$ ```end```

## Commande pour afficher la configuration des ports d'un switch 
$ ```show vlan brief```

## Commande pour connecter des switchs entre eux
$ ```int f0/1```
$ ```switchport mode trunk```
$ ```switchport trunk native vlan 1 (vlan default)```
$ ```switchport trunk allowed vlan 20,30,40```
$ ```end```



### Commande pour configurer le router (nom du routeur)
$ ```commande à taper```

### Commandes pour configurer le firewall (optionnel -> Romain verra)
$ ```commande à taper```

<!--### ajout de gateway pour vlan
Se brancher aux ports correspondants (ici pour le VLAN 20)
  ip default gateway 192.168.20.254-->

Légende :
$ pour les commandes
