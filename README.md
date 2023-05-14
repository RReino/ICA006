# ICA006
**ICA006 Dokumentatsioon, Grupp 1**
![serveripuu](https://user-images.githubusercontent.com/99139232/238201955-e6bd4bcd-160e-48bd-9323-e9a9700304ec.PNG)
## Serverite andmed

**Kasutajanimi:** node01/node02/node03/lab
**Parool:** 1234 (k.a root)
## 1. RAID
2x raid 0 (2 ketast raidi kohta) 
Suuruses: 146.74 GB
## 2. Linuxi installeerimine
Linux Image [link](https://ubuntu.com/download/server) (Ubuntu Server 20.04 LTS)
## 3. CEPH install 
**CEPH versioon** : [15.2.17 Octopus](https://docs.ceph.com/en/latest/releases/octopus#v15-2-17-octopus)
 - Genereeritud SSH-key node01 peal ning kopeeritud(ssh-copy) see
   kõikidele masinatele.
 - Installitud CEPH kõikidele masinatele.
 - Konfigureeritud monitor ja manager daemon node01s.
 - Konfigureeritud OSD igale masinale.
 - Kontrollitud CEPHI staatust.
## 4. CEPH plokk seadme kasutamine [lab]
 - Kopeeritud node01 SSH public key virtuaalserverisse
 - Installitud **Ceph Common**
 - Kopeeritud vajalikud failid virtuaalserverisse [**ceph.conf, ceph.client.admin.keyring**]
 - Tehtud plokk seade ning mountitud see virtuaalserveri kettale.

### Kustutamine

    rbd unmap /dev/rbd/rbd/rbd01

### Plokk seade
   
     rbd rm rbd01 -p rbd

### Pool

    ceph osd pool delete rbd rbd --yes-i-really-really-mean-it

## 5. Veebiaplikatsiooni ja andmebaasi käivitamine
### Veebiaplikatsioon

 - Installitud Apache veebiserver
 - Installitud MySQL andmebaasi server
 - Installitud PHP
 - Kausta valmistamine domeeni
 - Loodud algeline lehekülg
 - Loodud virtuaalne hosti fail ja aktiveeritud
 - Virtuaalse hosti konfigureerimine
 - Loodud andmebaas lehe jaoks
### Anomaaliad
 - CEPH kettad on alles ka peale formatit.
 - CEPH installerid ei ole samma versiooni.
 - Linuxi installimisega vahepeal peab uuendama updaterit, vahepeal mitte.
