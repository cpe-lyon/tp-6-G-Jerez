TP6: Admin Linux

**Exercice 1:**
Ayant un masque de réseau en /23, il nous reste donc 8+1=9 bit pour le découpage en sous réseaux
le plus de machines dans un sous réseau étant 52, le plus proche supérieur est donc 64.  
Il nous faut donc diviser le réseau nous étant donné en sous réseaux de 64 machines ce qui nous donne donc:  
-sr1: 172.16.0.0    b: 172.16.0.63    1st: 172.16.0.1     last: 172.16.0.62  
-sr2: 172.16.0.64   b: 172.16.0.127   1st: 172.16.0.65    last: 172.16.0.126  
-sr3: 172.16.0.128  b: 172.16.0.191   1st: 172.16.0.129   last: 172.16.0.190  
-sr4: 172.16.0.192  b: 172.16.0.255   1st: 172.16.0.193   last: 172.16.0.254  
-sr5: 172.16.1.0    b: 172.16.1.63    1st: 172.16.1.1     last: 172.16.1.62  
-sr6: 172.16.1.64   b: 172.16.1.127   1st: 172.16.1.65    last: 172.16.1.126  
-sr7: 172.16.1.128  b: 172.16.1.191   1st: 172.16.1.129   last: 172.16.1.190  
-sr8: 172.16.1.192  b: 172.16.1.255   1st: 172.16.1.193   last: 172.16.1.254  

**Exercice 2:**
1. infaisable
2. L'interface appellée ```lo``` est l'interface de loopback.
3. Pour désinstaller le paquet ```cloud-init``` on effectue la commande ```sudo apt remove cloud-init``` sur les deux machines.
4. Afin de changer de manière permannente le hostname, il y a trois commandes à effectuer. La première commande est la suivante ```sudo hostnamectl set-hostname serveur```. La seconde étape est d'effectuer ```sudo nano /etc/hosts``` et de corriger toutes les occurences du nom du host. Et enfin pour que les changements soient effectif, il faut effectuer ```sudo reboot```.

**Exercice 3:**
1. On peut installer le paquet avec ```sudo apt install isc-dhcp-server```.
2. La commande pour définir de manière permanente l'adresse IP est ```netplan apply``` après avoir effectuer les modifications nécessaires. On peut vérifier la configuration avec ```ip a```.
3. Le ```default-lease-time``` correspond au temps par défaut de l'expiration de l'adresse désignée pour le dhcp. Le ```max-lease-time``` est donc le temps maximal au bout duquel il changera l'adresse IP.
4. Le port à renseigner est donc le ```enp0s8``` puisque c'est celui que l'on a reparamétré dans ce but.
5. Afin de vérifier que le programme est actif, on peut effectuer ```service isc-dhcp-server status```.
7. DHCPDISCOVER: requête du client servant à découvrir les serveurs dhcp disponible.
   DHCPOFFER: réponse du serveur dhcp à la requête DHCPDISCOVER en offrant leur adresse ipv4.
   DHCPREQUEST: réponse du client à la requête DHCPOFFER.
   DHCPACK: réponse du serveur comprenant les configurations pour les paramètres réseau du client.
8. Le fichier ```/var/lib/dhcp/dhcpd.leases``` contient les heures auquelles le serveur a attribué des adresses ip, ainsi que des paramètres et l'heure d'échéance de cette entrée. La commande ```dhcp-lease-list``` contient sous forme de tableau les adresses ip données à des adresses MAC avec d'autres infos.
9. Les deux machines peuvent communiquer entre elle à l'aide de la commande ping.


vlan 14
