# Guia per fer còpies amb Duplicati a Windows 11

## 1. Preparació de la màquina virtual i el disc dur

1. Instal·lem la màquina virtual en Windows 11 i afegim un disc dur de 10 GB per a emmagatzemar les còpies de seguretat.  

   <img src="img/1.png">

2. A la màquina virtual, obrim el menú **“Crear y formatear particiones del disco duro”** i formatem el nou disc.  

   <img src="img/2.png">

3. Acceptem formatar el disc amb **GPT**.  

   <img src="img/3.png">

4. Creem un nou **volum simple** perquè el disc estigui llest per escriure-hi dades.  

   <img src="img/4.png">

5. Seguim els passos de l’assistent:  
   - **Següent**  

     <img src="img/5.png">
   - **Següent**  

     <img src="img/6.png">
   - **Següent**  

     <img src="img/7.png">

6. Assignem com a **etiqueta del volum** el nom **Dades** per identificar-lo fàcilment.  

   <img src="img/8.png">

7. Fem clic a **Finalitzar** per completar la creació del volum.  

   <img src="img/9.png">

8. Ara el disc apareix a l’**Explorador de archivos** juntament amb el disc del sistema.  

   <img src="img/10.png">

---

## 2. Instal·lació de Duplicati

1. Accedim a la pàgina web de **Duplicati** i descarreguem el programa.  

   <img src="img/11.png">

2. Obrim l’instal·lador i seguim els passos habituals:  
   - **Següent**  

     <img src="img/12.png">
     <img src="img/13.png">
     <img src="img/14.png">

3. Fem clic a **Instal·lar**  

   <img src="img/15.png">

4. Acceptem les peticions del sistema.  

   <img src="img/16.png">

5. Finalitzem la instal·lació.  

   <img src="img/17.png">

---

## 3. Configuració inicial de Duplicati

1. En obrir-se el panell d’administració, Duplicati demana crear una **contrasenya**.  

   <img src="img/18.png">

2. Un cop creada, podem començar a configurar les còpies de seguretat.  

---

## 4. Creació d’una còpia de seguretat local

1. Anem a **Backups → Add**  

   <img src="img/19.png">

2. Seleccionem **New backup**  

   <img src="img/20.png">

3. Li assignem un nom, per exemple **“Còpia disc secundari”**, i definim una contrasenya.  

   <img src="img/21.png">

4. Seleccionem el destí de la còpia: el disc D anomenat **Dades**.  

   <img src="img/22.png">

5. Escollim les dades a copiar, per exemple **Documentos**.  

   <img src="img/23.png">

6. Programem la còpia perquè es realitzi **cada hora cada dia de la setmana**.  

   <img src="img/24.png">

7. Configurem que es **guardi totes les versions** de la còpia.  

   <img src="img/25.png">

8. La configuració de la còpia està completa.  

   <img src="img/26.png">

---

## 5. Prova de la còpia de seguretat local

1. A la carpeta **Documentos**, creem una carpeta **Prova** amb un arxiu **Important.txt**.  

   <img src="img/27.png">

2. Fem clic a **Start** per realitzar la còpia.  
   - Un cop completada, veurem dues versions: inicial i la nova.  

   <img src="img/28.png">

3. Esborrem la carpeta **Documentos** per provar la restauració.  

   <img src="img/29.png">

---

## 6. Restauració de la còpia local

1. Anem a **Restores → Start**  

   <img src="img/30.png">

2. Seleccionem la còpia **Còpia disc secundari** i fem clic a **Restore**.  

   <img src="img/31.png">

3. Verifiquem que la carpeta que volem restaurar apareix i fem clic a **Continue**.  

   <img src="img/32.png">

4. Indiquem restaurar els arxius **a la mateixa ubicació** i sobreescriure si ja existeixen.  

   <img src="img/33.png">
   <img src="img/34.png">

5. La carpeta es restaura correctament.  

   <img src="img/35.png">

---

## 7. Configuració de còpia a Google Drive

1. Configurem les còpies cada dia a les 18:00 en un medi extern, en aquest cas **Google Drive**.  
   - Seguim el mateix procediment que amb l’altre còpia.  

   <img src="img/36.png">

2. A diferència de l’altra còpia, el destí serà **Google Drive**.  

   <img src="img/37.png">

3. Posem de ruta de la còpia la carpeta **Documentos** i fem clic a **AuthID** per vincular el nostre compte.  

   <img src="img/38.png">

4. En fer clic en **AuthID** se'ns obre una finestra per vincular el compte de Google on volem fer la còpia.  

   <img src="img/39.png">

5. Autoritzem que **Duplicati tingui permisos** per administrar el nostre Google Drive.  

   <img src="img/40.png">

6. Un cop vinculat el compte, fem clic de nou a **AuthID** per obtenir el codi d’autorització.  

   <img src="img/41.png">

7. Se’ns obre una web on podrem veure el codi que hem d’utilitzar.  

   <img src="img/42.png">

8. Enganxem el codi a l’entrada **código de autorización**.  

   <img src="img/43.png">

9. Duplicati detecta que la carpeta **Documents** dins Google Drive no existeix i ens pregunta si volem crear-la. Li diem **Sí**.  

   <img src="img/44.png">

10. Un cop amb la carpeta destí configurada, seleccionem l’origen a copiar (**Documentos**).  

    <img src="img/45.png">

11. Configurem la còpia perquè es faci **cada dia a les 18:00**.  

    <img src="img/46.png">

12. Deixem les configuracions per defecte.  

    <img src="img/47.png">

13. Iniciem la primera còpia prement **Start**.  

    <img src="img/48.png">

14. Un cop completada, podrem veure que s’ha creat la carpeta **Documents** a Google Drive amb els arxius de la còpia.  

    <img src="img/49.png">

15. Esborrem la carpeta **Prova** dins **Documentos** per provar la restauració.  

    <img src="img/50.png">

16. Per iniciar la restauració, anem a **Restores → Start**.  

    <img src="img/51.png">

17. Seleccionem la còpia de seguretat **Còpia Google Drive** i fem clic a **Restore**.  

    <img src="img/52.png">

18. Seleccionem la carpeta **Prova** per restaurar-la.  

    <img src="img/53.png">

19. Li indiquem que volem que els arxius es restaurin en la **ubicació original**.  

    <img src="img/54.png">

20. Veiem que la restauració dels arxius s’ha completat correctament.  

    <img src="img/55.png">
    <img src="img/56.png">
