# LPOS
LPOS (Lokalt Patientovervågningssystem) er et overvågningssystem som er lavet til at overvåge indlagte patienters helbred på en afdeling i et hospital.
Der er to undersystemer:

- En overvågningsenhed
  - Sensorer der tilknyttes patienten
  - En knap til at tilkalde en sygeplejerske
- En infoskærm
  - Oversigt over alle patienter i afdelingen
  - Notifikationer ved tilkaldelse
  - Alarmer når patienterne rammer en grænseværdi

De to undersystemer kommunikerer over et lokalt netværk vha. MQTTS.

## Dokumentation
Fuld dokumentation af systemerne kan findes under [Wiki linket](https://github.com/inuitviking/LPOS/wiki) på Github.

Derudover kan kode for de to undersystemer findes følgende steder (Github):

- [LPOS enhed](https://github.com/inuitviking/LPOS-enhed)
- [LPOS-infoscreen](https://github.com/inuitviking/LPOS-infoscreen)
- [docker-images](https://github.com/inuitviking/docker-images)

Som kan ses i hvert undersystem, er der meget mere arbejde i undersystemerne end man lige regner med, hvor rigtig meget af det er opsætning og konfiguration.
Der er også to arkiverede Github repositories, da de blev for roddet, og skulle splittes ad; se listen ovenfor. Disse arkiverede repositories vil ikke være dokumenteret.
Arkiveret betyder at disse repositories bliver ikke brugt, hverken i projektet eller til udvikling.

Disse repositories kan findes her:
- [LPOS-infoskærm](https://github.com/inuitviking/LPOS-infosk-rm)
- [LPOS-infoskærm-compose](https://github.com/inuitviking/LPOS-infosk-rm-compose)
