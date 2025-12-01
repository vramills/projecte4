# T01: DRP: còpies de seguretat. Estudi cas client

## Introducció
La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, caldrà que treballeu els aspectes del tema i ho fareu mitjançant una dinàmica cooperativa.

## Presentació del cas client
"Muntatges i Serveis Tècnics SL" és una petita empresa dedicada a la instal·lació i manteniment d'equips industrials.

### Infraestructura Tècnica
- **Servidor de Fitxers (Ubuntu Server):** Conté tota la documentació crítica:
  - Documents de Projectes: Plànols, especificacions tècniques (300 GB, creixement moderat).
  - Bases de Dades (Comptabilitat i Clients): Crítiques i d'ús diari (20 GB, canvi constant).
  - Carpetes Personals dels Usuaris: Per a la feina diària (100 GB).
- **10 Equips Clients (Windows 10/11):** Els usuaris treballen majoritàriament amb fitxers del servidor, però alguns tècnics guarden de forma temporal informes i altres arxius importants a la carpeta *Documents*.
- **Connexió a Internet:** Fibra òptica de 600 Mbps (simètrica).

### Requisits de Recuperació
- **Temps de Recuperació (RTO):** Les dades de Comptabilitat/Clients han d'estar disponibles en menys de 4 hores.
- **Pèrdua de Dades Admesa (RPO):** Es pot admetre una pèrdua màxima de 24 hores per a la majoria de dades, però les dades de Comptabilitat/Clients no poden perdre més de 4 hores de treball.
- **Retenció:** Cal guardar les dades amb un historial d'almenys un mes.

---

## Fase 1: Treball individual
De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

### **1. Què copiar? (Priorització)**  
**Pregunta:** Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.  

S’haurien de copiar les dades més crítiques del servidor que en aquest cas són la dels documents de projectes, bases de dades i les carpetes personals dels usuaris, mentre que dels clients, hauríem de fer la còpia únicament de la carpeta *Documents*, ja que emmagatzema allà ocasionalment dades.

---

### **2. Periodicitat i Tipus de Còpia**  
**Pregunta:** Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.  

Tenint en compte el **Temps de Recuperació (RTO)** i la **Pèrdua de Dades Admesa (RPO)**, hauríem de fer les següents còpies:

#### Servidor de Fitxers (Ubuntu Server)
- **Documents de Projectes:**  
  - Còpia **incremental diària** per capturar els canvis diaris sense duplicar tot el volum de dades.  
  - Còpia **completa setmanal** per tenir un punt estable per a restauracions ràpides i segures.  
  - Còpia **completa mensual** per tenir un historial mínim d’un mes.  

- **Bases de Dades (Comptabilitat i Clients):**  
  - Còpia **incremental cada 4 hores** per a respectar el Temps de recuperació i minimitzar la pèrdua de dades.  
  - Còpia **diferencial diària**, ja que facilita la restauració; només cal combinar la completa setmanal amb la diferencial.  
  - Còpia **completa setmanal**, funciona com un punt base fiable per restauracions en cas de fallada greu.  
  - Còpia **completa mensual** per a tenir un historial i seguretat davant esdeveniments majors.  

- **Carpetes Personals dels Usuaris:**  
  - Còpia **incremental diària**, ja que captura els canvis diaris sense ocupar molt espai.  
  - Còpia **completa setmanal**, ja que permet restauració fàcil en cas de pèrdua d’arxius.  
  - Còpia **completa mensual**, ja que completa l’historial mensual de dades.

#### 10 Equips Clients (Windows 10/11)
- Còpia **incremental diària**, ja que alguns tècnics guarden informes i arxius importants temporalment; així es minimitza la pèrdua de dades sense fer còpies completes de tot l’equip.

---

### **3. Mitjans i Ubicació**  
**Pregunta:** Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1)?  

Com a **mitjà de còpia de seguretat**, recomanaria:

- Un **NAS** com a destinació principal de les còpies incrementals i diferencials, ja que permet una restauració ràpida i centralitzada amb snapshots.  
- Fer ús de **discs durs externs** per còpies completes setmanals, ja que és un tipus de mitjà diferent i còpia física separada dins l’empresa.  
- I una **solució al núvol com AWS** per còpies completes mensuals (off-site), ja que permet fer còpies en un punt fora del lloc on es troba el servidor, de manera que hi ha protecció davant robatoris, incendis o desastres.

**Ubicació de les còpies:**

- Al **NAS** la còpia més recent, ja que permet una restauració fàcil.  
- Als discs **durs externs** faria les còpies completes setmanals, guardades en un lloc segur dins l’empresa.  
- I al **núvol** faria còpies completes mensuals, fora del lloc, per assegurar redundància i protecció davant desastres majors.

---

## Fase 2: Treball per parelles

### 2. Elaboració d'una Proposta Unificada
Heu de consensuar i dissenyar el vostre propi **Esquema 3-2-1 de Còpies** (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

| Element | Proposta de la Parella | Justificació |
|--------|-----------------------|-------------|
| **Dades Crítiques** | - Bases de Dades (Comptabilitat i Clients) <br> - Documents de Projectes <br> - Carpetes Personals <br> - Carpeta *Documents* dels clients Windows | Les BD tenen dades de canvi constant i necessiten RTO/RPO molt baixos. Documents de Projectes i Carpetes Personals tenen gran volum però menys criticitat temporal. Els equips només necessiten arxius puntuals. |
| **Periodicitat (BD)** | - Incremental cada 4 hores <br> - Diferencial diària <br> - Completa setmanal <br> - Completa mensual | Garanteix la pèrdua màxima de 4 h (RPO). Les còpies diàries i setmanals generen punts de restauració estables i historial mensual. |
| **Tipus de Còpia (BD)** | - Incrementals per capturar canvis constants <br> - Diferencial setmanal per restauració ràpida <br> - Completes com a base fiable | Restauració flexible: les incrementals cobreixen el dia, la diferencial facilita restauració i la completa ofereix punt segur. |
| **Mitjà 1 (Local)** | - NAS intern per a còpies incrementals i diferencials | Restauració ràpida i centralitzada. Alta velocitat en xarxa interna i snapshots. |
| **Mitjà 2 (Extern)** | - Disc dur extern per còpia setmanal <br> - Núvol per còpia mensual | Compleix la regla 3-2-1: mitjà diferent i còpia off-site protegida davant robatori, incendi o desastre físic. |
