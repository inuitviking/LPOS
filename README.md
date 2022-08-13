# LPOS
LPOS (Lokalt Patientovervågningssystem) er et overvågningssystem som er lavet til at overvåge indlagte patienters helbred på en afdeling i et hospital.
Der er to undersystemer:

- En overvågningsenhed
  - Sensorer der tilknyttes patienten
  - En knap til at tilkalde en sygeplejerske
- En infoskærm
  - Oversigt over alle patienter i afdelingen
  - Notifikationer ved tilkaldelse
  - Alarmer når patienterne ramme en grænseværdi

De to undersystemer kommunikerer over et lokalt netværk vha. Secure MQTT.

## Hvordan gør man MQTT sikkert?
MQTT er ikke kendt for sin sikkerhed, men vha. Mosquitto's implementation af SMQTT, har vi følgende funktioner:

- [`mosquitto_passwd`](https://mosquitto.org/man/mosquitto_passwd-1.html)
- [`mosquitto-tls](https://mosquitto.org/man/mosquitto-tls-7.html)

Med de to funktioner som mosquitto tilbyder, kan vi sikre at kommunikationen mellem overvågningsenheden og infoskærmen er krypteret, både med certifikater og brugere med krypteret adgangskoder.

`mosquitto_passwd` kører samme standard som Linux hvad vedr. adgangskoder. Der kan læses merer om det [her](https://linux.die.net/man/3/crypt).

`mosquitto-tls` konfigureres vha. af openssl, og certifikater og nøgler genereres på forhånd med tilstrækkelige bit størrelser. Det eneste krav er, at en arduino kan trække det. Der vil blive brugt et selvsigneret certifikat pr. afdeling (dog med samme autoritetscertifikat), og kan uploades til en Arduino MKR WiFi 1010 som vist [her](https://support.arduino.cc/hc/en-us/articles/360016119219-How-to-add-certificates-to-Wifi-Nina-Wifi-101-Modules-).

På de førnævnte måder, kan vi sørge for at kun de nødvendige enheder kan forbinde til infoskærmen, samt undgår vi også Man-in-the-Middle angreb, da det vil være nærmest umuligt at sniffe hvad der bliver sendt frem og tilbage mellem enhederne og infoskærmen.

## Dokumentation
Fuld dokumentation af systemerne kan findes under [Wiki linket](https://github.com/inuitviking/LPOS/wiki) på Github.

Derudover kan kode for de to undersystemer findes følgende steder (Github):

- [LPOS enhed](https://github.com/inuitviking/LPOS-enhed)
- [LPOS infoskærm](https://github.com/inuitviking/LPOS-infosk-rm)
- [LPOS infoskærm compose](https://github.com/inuitviking/LPOS-infosk-rm-compose)
