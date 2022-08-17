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

De to undersystemer kommunikerer over et lokalt netværk vha. MQTTS.

## Dokumentation
Fuld dokumentation af systemerne kan findes under [Wiki linket](https://github.com/inuitviking/LPOS/wiki) på Github.

Derudover kan kode for de to undersystemer findes følgende steder (Github):

- [LPOS enhed](https://github.com/inuitviking/LPOS-enhed)
- [LPOS infoskærm](https://github.com/inuitviking/LPOS-infosk-rm)
- [LPOS infoskærm compose](https://github.com/inuitviking/LPOS-infosk-rm-compose)
