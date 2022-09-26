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
4. 
