# Configuration infra EPSI 2023

## Commandes de configuration des switches

### Commandes pour configurer les switches (nom des switches)
  conf t   
  vlan 20   
  name server   
  end

### Commandes pour configurer les ports des switchs + ajout de sports au vlan
  conf t   
  int f0/1   
  switchport mode access   
  switchport access vlan 20   
  end

### Commande pour afficher la configuration des ports d'un switch 
  show vlan brief   

### Commande pour connecter des switchs entre eux
  int f0/1   
  switchport mode trunk   
  switchport trunk native vlan 1 (vlan default)   
  switchport trunk allowed vlan 20,30,40   
  end   

## Commande de configuration du routeur

### Overload (NAT) avec une seule adressse globale
  access-list 1 permit 192.168.0.0 0.0.0.255   
  ip nat inside source list 1 interface s0 overload   
  interface e0   
  ip nat inside   
  interface s0   
  ip nat outside   

### Commande de création des VLANs sur le routeur (nom du routeur)
  vlan database   
  vlan 20 name server   
  exit   
  
### Commandes de configuration des ports pour les VLANs
  configure terminal   
  interface fastethernet 0/5   
  switchport mode access    
  switchport access vlan 20   
  interface fastethernet 0/1   
  switchport mode access    
  switchport access vlan 20   
  interface fastethernet 0/2   
  switchport mode access   
  switchport access vlan 20   
  interface fastethernet 0/3   
  switchport mode access    
  switchport access vlan 20   
  end   
  
### Configuration des règles de routage des VLANs sur le routeur ?
  interface fastethernet 0/0   
  no shutdown   
  interface fastethernet 0/0.2   
  encapsulation dot1q 1   
  ip address 192.168.1.1 255.255.255.0   
  interface fastethernet 0/0.3   
  encapsulation dot1q 10   
  ip address 192.168.5.1 255.255.255.0     
  interface fastethernet 0/0.4    
  encapsulation dot1q 20    
  ip address 192.168.7.1 255.255.255.0    
  end

<!--### ajout de gateway pour vlan
Se brancher aux ports correspondants (ici pour le VLAN 20)
  ip default gateway 192.168.20.254-->
