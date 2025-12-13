# T07: Accés remot. Serveis d’assistència remota (tasca en parelles)

## Fase 1: Anàlisi comparativa i selecció de la solució

El primer pas és decidir quina eina utilitzarà EverPia. Pel que hem fet una anàlisi de mercat i un breu informe comparatiu entre les diferents eines d’assistència remota que hi ha al mercat. Un cop feta aquesta anàlisi, hem seleccionat l’eina que millor s’adapta a les necessitats de l’empresa i hem justificat la nostra elecció.

## Taula Comparativa d’Eines d’Assistència Remota

| Criteri | TeamViewer | AnyDesk | Google (Chrome) Remote Desktop | LogMeIn |
|-------|------------|---------|--------------------------------|---------|
| Facilitat d’ús (client) | Requereix descarregar l’aplicació o mòdul QuickSupport. L’usuari ha de facilitar un ID i una contrasenya. | Instal·lació ràpida i lleugera. ID visible i fàcil de comunicar. | Molt senzill si l’usuari té compte Google. Connexió via navegador i PIN. | Accés mitjançant aplicació o enllaç. Pensat per a entorns empresarials. |
| Instal·lació / Portable | Mòdul QuickSupport sense instal·lació completa | Instal·lació lleugera | No requereix instal·lació d’escriptori | Requereix instal·lació de l’agent |
| Windows | ✅ | ✅ | ✅ | ✅ |
| macOS | ✅ | ✅ | ✅ | ✅ |
| Linux | ✅ | ✅ | ✅ | No |
| Dispositius mòbils | ✅ | ✅ | ✅ | ✅ |
| Ús comercial permès en versió gratuïta | No | No | ✅ | No |
| Model de preu | Subscripció per tècnic | Subscripció (més econòmica) | Gratuït | Subscripció (cost elevat) |
| Limitacions de la versió gratuïta | Tall de sessions i detecció d’ús comercial | Funcions avançades limitades | Funcionalitats bàsiques | No disposa de versió gratuïta |

## Justificació de l’Eina Seleccionada

Després d’analitzar les diferents opcions disponibles, es recomana `AnyDesk` com a eina oficial d’assistència remota per a EverPia. Aquesta solució combina facilitat d’ús per a l’usuari final, compatibilitat amb entorns mixtos i un model de llicència assequible. Així, permet als tècnics oferir suport ràpid, segur i eficient, sense complicacions per al client i amb un bon equilibri entre funcionalitat, rendiment i cost.

---

## Fase 2: Creació de les Guies d'Ús (Documentació)

Un cop seleccionada l'eina a la Fase 1, ara crearem la documentació oficial per al seu ús. Aquesta documentació és crucial i tindrà dues parts: una guia per als tècnics d'assistència i una guia per als usuaris finals.

## Guia per als Tècnics d'Assistència Remota amb AnyDesk

### Introducció

Aquesta guia està destinada als tècnics d'assistència remota d'EverPia per utilitzar `AnyDesk` de manera eficient i segura.

### Passos per a l'Ús d'AnyDesk

1. **Descàrrega i Instal·lació**
   - Descarrega AnyDesk des del lloc oficial: [https://anydesk.com](https://anydesk.com).
   - Instal·la l'aplicació seguint les instruccions proporcionades.

2. **Connexió a un Client**
   - Obre AnyDesk i demana al client que et proporcioni el seu ID d'AnyDesk.
   - Introdueix l'ID al camp "Remote Desk" i fes clic a "Connect".
   - Espera que el client accepti la connexió.
   - Un cop connectat, utilitza les eines disponibles per oferir assistència.

3. **Funcions Clau**
   - **Transferència de Fitxers**: Utilitza la funció de transferència de fitxers per enviar o rebre documents.
   - **Xat Integrat**: Comunica't amb el client mitjançant el xat integrat per resoldre dubtes.
   - **Captura de Pantalla**: Fes captures de pantalla per documentar problemes o solucions.