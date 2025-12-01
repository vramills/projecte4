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

---

## Fase 3: Treball en grup

### 1. Debat i Selecció
Cada parella presenta el seu esquema. El grup debat els pros i contres de cada proposta (cost, temps de recuperació, seguretat, simplicitat).

### 2. Disseny de la Política Final
El grup ha de redactar la **Política de Còpies de Seguretat Definitiva** que presentaran a l'empresa "Muntatges i Serveis Tècnics SL".

---

### 1) Dades Objecte de Còpia

| Tipus | Objecte de Còpia | Criticitat | Comentari |
|-------|-----------------|------------|-----------|
| **Servidor de Fitxers (Ubuntu)** | Bases de Dades (Comptabilitat i Clients) | Alta | Canvi constant, RPO 4h, RTO 4h |
|  | Documents de Projectes | Mitjana | Gran volum, canvis moderats |
|  | Carpetes Personals dels Usuaris | Mitjana | Canvis diaris |
| **Equips Clients (Windows 10/11)** | Carpeta *Documents* | Mitjana | Alguns informes i arxius temporals |

---

### 2) Cronograma Setmanal Detallat

| Dia | Dades | Tipus de Còpia | Mitjà |
|-----|-------|----------------|-------|
| Dilluns | Bases de Dades | Incremental cada 4h | NAS |
|  | Documents de Projectes | Incremental diari | NAS |
|  | Carpetes Personals | Incremental diari | NAS |
|  | Clients Windows | Incremental diari | NAS |
| Dimarts | Bases de Dades | Incremental cada 4h | NAS |
|  | Documents de Projectes | Incremental diari | NAS |
|  | Carpetes Personals | Incremental diari | NAS |
|  | Clients Windows | Incremental diari | NAS |
| Dimecres | Bases de Dades | Incremental cada 4h | NAS |
|  | Documents de Projectes | Incremental diari | NAS |
|  | Carpetes Personals | Incremental diari | NAS |
|  | Clients Windows | Incremental diari | NAS |
| Dijous | Bases de Dades | Incremental cada 4h | NAS |
|  | Documents de Projectes | Incremental diari | NAS |
|  | Carpetes Personals | Incremental diari | NAS |
|  | Clients Windows | Incremental diari | NAS |
| Divendres | Bases de Dades | Diferencial diària + Completa setmanal | NAS + Disc dur extern |
|  | Documents de Projectes | Completa setmanal | Disc dur extern |
|  | Carpetes Personals | Completa setmanal | Disc dur extern |
|  | Clients Windows | Incremental diari | NAS |
| Dissabte | Bases de Dades | Incremental cada 4h | NAS |
|  | Documents de Projectes | Incremental diari | NAS |
|  | Carpetes Personals | Incremental diari | NAS |
|  | Clients Windows | Incremental diari | NAS |
| Diumenge | Bases de Dades | Completa mensual | Cloud (AWS) |
|  | Documents de Projectes | Completa mensual | Cloud (AWS) |
|  | Carpetes Personals | Completa mensual | Cloud (AWS) |

---

### 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

| Categoria | Mitjà | Ubicació | Responsabilitat |
|-----------|-------|---------|----------------|
| Mitjà 1 (Local) | NAS intern | Sala de Servidors, accés restringit | Administrador TI |
| Mitjà 2 (Extern) | Disc dur extern (setmanal) | Armaris segurs a l’empresa | Administrador TI |
| Ubicació Fora de Lloc | Cloud (AWS) | Servei Cloud, dades xifrades | Administrador TI i responsable de seguretat |

Aquest esquema compleix la regla 3-2-1: tenim 3 còpies (NAS, disc extern, cloud), 2 mitjans diferents (NAS + disc extern/cloud), i 1 fora de lloc (Cloud).

---

### 4) Estratègia de Recuperació (RTO/RPO)

**Bases de Dades (Comptabilitat/Clients):**  
- **RPO 4 h:** Còpies incrementals cada 4 hores per minimitzar pèrdua de dades.  
- **RTO 4 h:** Restauració prioritària des del NAS o, si cal, des del disc dur extern. El cloud actua com a última via en cas de desastre major.

**Documents de Projectes / Carpetes Personals / Clients Windows:**  
- **RPO 24 h:** Còpies incrementals diàries asseguren que només es perd un dia de treball.  
- **RTO ≤ 24 h:** Restauració ràpida des del NAS per incidents menors.

**Procediment en cas de fallada:**  
1. Restaurar dades crítiques (BD) des del NAS.  
2. Si el NAS no està disponible, utilitzar disc extern.  
3. En cas de desastre total, recuperar còpia mensual des del Cloud.
