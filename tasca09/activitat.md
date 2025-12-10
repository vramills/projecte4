# T09: Servidor fitxers Linux. NFS

Començarem amb la preparació del servidor, i per això crearem dos grups per al client; devs i admins.

<img src="img/1.png">

I comprovem que s’han creat correctament amb la comanda grep.

<img src="img/2.png">

Creem un usuari dev01 que és membre del grup devs.

<img src="img/3.png">

I fem el mateix amb admin01 i el grup admins.

<img src="img/4.png">

Ara creem un directori per als projectes de desenvolupament.

<img src="img/5.png">

I un altre per a les eines d’administració.

<img src="img/6.png">

I modifiquem els permisos de manera que els developers tinguin control total sobre els seus projectes i els administradors sobre les seves eines.

<img src="img/7.png">