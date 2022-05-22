# hello-world
 Basic knowledge
Primero se va al switch se da Vlan show, se buscan las y se verifica a donde van:
se crea para cada Vlan una interface
CN5160-Tapachula*> interface create ip-interface TEST-509 ip 1.1.1.1/30 ip-forwarding on vlan 509
asi se borra:
CN5160-Tapachula*> interface delete ip-interface TEST-509

se pone de un lado una ip /30 digamos 1.1.1.1 y del otro lado 1.1.1.2
 
se prueban paquetes con este comando: el 15 puede ser el numero de paquetes que uno quiera

CN5160-Tapachula*> file ping -c15 -s1500 1.1.1.2                                                 
PING 1.1.1.2 (1.1.1.2): 1500 data bytes
1508 bytes from 1.1.1.2: seq=0 ttl=64 time=13.685 ms
1508 bytes from 1.1.1.2: seq=1 ttl=64 time=9.597 ms
1508 bytes from 1.1.1.2: seq=2 ttl=64 time=8.945 ms
1508 bytes from 1.1.1.2: seq=3 ttl=64 time=7.901 ms
1508 bytes from 1.1.1.2: seq=4 ttl=64 time=6.984 ms
1508 bytes from 1.1.1.2: seq=5 ttl=64 time=9.112 ms
1508 bytes from 1.1.1.2: seq=6 ttl=64 time=8.272 ms
1508 bytes from 1.1.1.2: seq=7 ttl=64 time=7.568 ms
1508 bytes from 1.1.1.2: seq=8 ttl=64 time=6.598 ms
1508 bytes from 1.1.1.2: seq=9 ttl=64 time=8.424 ms
1508 bytes from 1.1.1.2: seq=10 ttl=64 time=7.460 ms
1508 bytes from 1.1.1.2: seq=11 ttl=64 time=6.785 ms
1508 bytes from 1.1.1.2: seq=12 ttl=64 time=5.830 ms
1508 bytes from 1.1.1.2: seq=13 ttl=64 time=7.861 ms
1508 bytes from 1.1.1.2: seq=14 ttl=64 time=7.346 ms


al final hay que borrar todas las interfaces creadas en todos los lugares
CN5160-Tapachula*> interface delete ip-interface TEST-509

vlan de la garita hacia otros lados:

209|RBS-GARITA-SAN2-MAIN
309|RBS-GARITA-SAN2-BACKUP

409|RBS-GARITA-TAPACHULA-MAIN
509|RBS-GARITA-TAPACHULA-BACKUP
 
En los ciena 4200 se activa  la luz laser puertos  : revisar los password porque no son los mismos
ipadmin
ipadmin123

para apagar primero los puertos despues los modulos y al reves para  prender, tomar captura de todos para saber como se hace.



Clave internacional vieja
su
pR#Qk6TFd.@35f

CN5160-Tapachula*> vlan 409 file ping -c15 -s1500 1.1.1.2                                                 
PING 1.1.1.2 (1.1.1.2): 1500 data bytes
1508 bytes from 1.1.1.2: seq=0 ttl=64 time=17.563 ms
1508 bytes from 1.1.1.2: seq=1 ttl=64 time=7.206 ms
1508 bytes from 1.1.1.2: seq=2 ttl=64 time=8.809 ms
1508 bytes from 1.1.1.2: seq=3 ttl=64 time=7.228 ms
1508 bytes from 1.1.1.2: seq=4 ttl=64 time=8.864 ms
1508 bytes from 1.1.1.2: seq=5 ttl=64 time=7.310 ms
1508 bytes from 1.1.1.2: seq=6 ttl=64 time=8.994 ms
1508 bytes from 1.1.1.2: seq=7 ttl=64 time=7.186 ms
1508 bytes from 1.1.1.2: seq=8 ttl=64 time=8.529 ms
1508 bytes from 1.1.1.2: seq=9 ttl=64 time=6.909 ms
1508 bytes from 1.1.1.2: seq=10 ttl=64 time=8.364 ms
1508 bytes from 1.1.1.2: seq=11 ttl=64 time=6.984 ms
1508 bytes from 1.1.1.2: seq=12 ttl=64 time=8.477 ms
1508 bytes from 1.1.1.2: seq=13 ttl=64 time=9.8071 ms
1508 bytes from 1.1.1.2: seq=14 ttl=64 time=8.104 ms
--- 1.1.1.2 ping statistics ---
15 packets transmitted, 15 packets recived 0% packet loss
-------------------------------------------------------------------------------
CN5160-Tapachula*> vlan 509 file ping -c15 -s1500 1.1.1.2  
1508 bytes from 1.1.1.2: seq=0 ttl=64 time=13.685 ms
1508 bytes from 1.1.1.2: seq=1 ttl=64 time=9.597 ms
1508 bytes from 1.1.1.2: seq=2 ttl=64 time=8.945 ms
1508 bytes from 1.1.1.2: seq=3 ttl=64 time=7.901 ms
1508 bytes from 1.1.1.2: seq=4 ttl=64 time=6.984 ms
1508 bytes from 1.1.1.2: seq=5 ttl=64 time=9.112 ms
1508 bytes from 1.1.1.2: seq=6 ttl=64 time=8.272 ms
1508 bytes from 1.1.1.2: seq=7 ttl=64 time=7.568 ms
1508 bytes from 1.1.1.2: seq=8 ttl=64 time=6.598 ms
1508 bytes from 1.1.1.2: seq=9 ttl=64 time=8.424 ms
1508 bytes from 1.1.1.2: seq=10 ttl=64 time=7.460 ms
1508 bytes from 1.1.1.2: seq=11 ttl=64 time=6.785 ms
1508 bytes from 1.1.1.2: seq=12 ttl=64 time=5.830 ms
1508 bytes from 1.1.1.2: seq=13 ttl=64 time=7.861 ms
1508 bytes from 1.1.1.2: seq=14 ttl=64 time=7.346 ms
--- 1.1.1.2 ping statistics ---
15 packets transmitted, 15 packets recived 0% packet loss
---------------------------------------------------------------------------------

---------------------------------------------------------------------------------

5160-SanCristobal*> vlan 209 file ping -c15 -s1500 1.1.1.2                                                 
PING 1.1.1.2 (1.1.1.2): 1500 data bytes
1508 bytes from 1.1.1.2: seq=0 tt1=64 time=13.333 ms
1508 bytes from 1.1.1.2: seq=1 tt1=64 time=6.008 ms
1508 bytes from 1.1.1.2: seq=2 tt1=64 time=3.689 ms
1508 bytes from 1.1.1.2: seq=3 tt1=64 time=5.208 ms
1508 bytes from 1.1.1.2: seq=4 tt1=64 time=3.696 ms
1508 bytes from 1.1.1.2: seq=5 tt1=64 time=5.024 ms
1508 bytes from 1.1.1.2: seq=6 tt1=64 time=3.544 ms
1508 bytes from 1.1.1.2: seq=7 tt1=64 time=4.835 ms
1508 bytes from 1.1.1.2: seq=8 tt1=64 time=3.197 ms
1508 bytes from 1.1.1.2: seq=9 tt1=64 time=7.629 ms
1508 bytes from 1.1.1.2: seq=10 tt1=64 time=5.830 ms
1508 bytes from 1.1.1.2: seq=11 tt1=64 time=7.779 ms
1508 bytes from 1.1.1.2: seq=12 tt1=64 time=6.096 ms
1508 bytes from 1.1.1.2: seq=13 tt1=64 time=7.030 ms
1508 bytes from 1.1.1.2: seq=14 tt1=64 time=5.535 ms
--- 1.1.1.2 ping statistics ---
15 packets transmitted, 15 packets recived 0% packet loss

---------------------------------------------------------------------
CN5160-Tapachula*> vlan 309 file ping -c15 -s1500 1.1.1.2                                                 
PING 1.1.1.2 (1.1.1.2): 1500 data bytes
L508 bytes from 1.1.1.2: seq=0 tt1=64 time=7.685 ms
L508 bytes from 1.1.1.2: seq=1 tt1=64 time=6.889 ms
L508 bytes from 1.1.1.2: seq=2 tt1=64 time=6.016 ms
L508 bytes from 1.1.1.2: seq=3 tt1=64 time=5.199 ms
L508 bytes from 1.1.1.2: seq=4 tt1=64 time=4.318 ms
L508 bytes from 1.1.1.2: seq=5 tt1=64 time=3.452 ms
L508 bytes from 1.1.1.2: seq=6 tt1=64 time=5.410 ms
L508 bytes from 1.1.1.2: seq=7 tt1=64 time=4.515 ms
L508 bytes from 1.1.1.2: seq=8 tt1=64 time=3.646 ms
L508 bytes from 1.1.1.2: seq=9 tt1=64 time=6.690 ms
L508 bytes from 1.1.1.2: seq=10 tt1=64 time=5.014 ms
L508 bytes from 1.1.1.2: seq=11 tt1=64 time=7.134 ms
L508 bytes from 1.1.1.2: seq=12 tt1=64 time=6.175 ms
L508 bytes from 1.1.1.2: seq=13 tt1=64 time=5.321 ms
L508 bytes from 1.1.1.2: seq=14 tt1=64 time=4.434 ms
--- 1.1.1.2 ping statistics ---
15 packets transmitted, 15 packets recived 0% packet loss

