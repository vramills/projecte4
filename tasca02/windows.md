# T02: Còpies de Seguretat a Windows 11 amb Duplicati

Ara configurarem les còpies de seguretat a Windows 11 amb Duplicati utilitzant un disc dur addicional de 10 GB.

<img src="img/1.png">

A l’inici veiem el nou disc afegit al sistema.

<img src="img/2.png">

---

## 1. Creació i format del disc

Acceptem formatar el disc amb esquema **GPT**.

<img src="img/3.png">

Creem un **Volum simple** per preparar el disc.

<img src="img/4.png">

Seguim els passos de l’assistent:

<img src="img/5.png">
<img src="img/6.png">
<img src="img/7.png">

Assignem com a etiqueta del volum: **Dades**.

<img src="img/8.png">

Un cop creat, el disc ja apareix a l’Explorador.

<img src="img/9.png">
<img src="img/10.png">

---

## 2. Instal·lació de Duplicati

Baixem l’instal·lador des del web oficial.

<img src="img/11.png">

Iniciem la instal·lació i seguim els passos:

<img src="img/12.png">
<img src="img/13.png">
<img src="img/14.png">

Fem clic a **Instal·lar**.

<img src="img/15.png">

Acceptem les sol·licituds del sistema i finalitzem la instal·lació.

<img src="img/16.png">
<img src="img/17.png">

---

## 3. Configuració inicial

En obrir Duplicati, ens demana definir una **contrasenya d’administració**.

<img src="img/18.png">

Amb això ja podem crear còpies de seguretat.

---

## 4. Creació d’una còpia de seguretat local

Anem a **Backups → Add**.

<img src="img/19.png">

Seleccionem **New Backup**.

<img src="img/20.png">

Assignem el nom `Còpia disc secundari` i una contrasenya.

<img src="img/21.png">

Configurem el destí al disc **Dades**.

<img src="img/22.png">

Seleccionem les carpetes que volem copiar, per exemple **Documents**.

<img src="img/23.png">

Programem la còpia perquè s’executi **cada hora cada dia**.

<img src="img/24.png">

Configurem que es guardin **totes les versions**.

<img src="img/25.png">

Configuració completada.

<img src="img/26.png">

---

## 5. Prova de còpia local

A la carpeta Documents, creem una carpeta **Prova** i un arxiu **Important.txt**.

<img src="img/27.png">

Executem la còpia manualment amb **Start**.

<img src="img/28.png">

Esborrem la carpeta Documents per fer la prova de restauració.

<img src="img/29.png">

---

## 6. Restauració local

Accedim a **Restores → Start**.

<img src="img/30.png">

Seleccionem la còpia i fem clic a **Restore**.

<img src="img/31.png">

Seleccionem la carpeta que volem recuperar i continuem.

<img src="img/32.png">

Restaurarem a la ubicació original.

<img src="img/33.png">

Fem clic a **Submit**.

<img src="img/34.png">

La restauració s’ha completat amb èxit.

<img src="img/35.png">

---

## 7. Còpia de seguretat a Google Drive

Crearem ara una còpia externa al núvol, programada cada dia a les 18:00.

<img src="img/36.png">

Comencem configurant la còpia. El destí serà **Google Drive**.

<img src="img/37.png">

Posem de ruta de la còpia la carpeta **Documentos** i fem clic a **AuthID** per vincular el nostre compte.

<img src="img/38.png">

En fer clic en **AuthID** se'ns obre una finestra per vincular el compte de Google on volem fer la còpia.

<img src="img/39.png">

Autoritzem que **Duplicati tingui permisos** per administrar el nostre Google Drive.

<img src="img/40.png">

Un cop vinculat el compte, fem clic de nou a **AuthID** per obtenir el codi d’autorització.

<img src="img/41.png">

Se’ns obre una web on podrem veure el codi que hem d’utilitzar.  

<img src="img/42.png">

Enganxem el codi a l’entrada **código de autorización**.

<img src="img/43.png">

Duplicati crea la carpeta **Documents** si no existeix.

<img src="img/44.png">

Seleccionem l’origen a copiar.

<img src="img/45.png">

Programem la còpia a les **18:00 cada dia**.

<img src="img/46.png">

Deixem la resta de configuracions per defecte.

<img src="img/47.png">

Iniciem la primera còpia prement **Start**.

<img src="img/48.png">

Un cop completada, podrem veure que s’ha creat la carpeta **Documents** a Google Drive amb els arxius de la còpia.

<img src="img/49.png">

Esborrem la carpeta **Prova** dins **Documentos** per provar la restauració.

<img src="img/50.png">

---

## 8. Restauració des de Google Drive

Per iniciar la restauració, anem a **Restores → Start**.

<img src="img/51.png">

Seleccionem la còpia de seguretat **Còpia Google Drive** i fem clic a **Restore**.

<img src="img/52.png">

Seleccionem la carpeta **Prova** per restaurar-la.

<img src="img/53.png">

Li indiquem que volem que els arxius es restaurin en la **ubicació original**.

<img src="img/54.png">

Veiem que la restauració dels arxius s’ha completat correctament.

<img src="img/55.png">
<img src="img/56.png">
