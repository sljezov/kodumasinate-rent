# Kasutajalood ja tööde nimekiri

Tööde haldamise keskkond: [GitHub Projects – Kodumasinate rent](https://github.com/users/sljezov/projects/4). Iga allolev kasutajalugu on eraldi GitHub issue ja lisatud tahvlile. [Sprint 1 vaade](https://github.com/users/sljezov/projects/4/views/2) kuvab ainult esimese sprindi viit tööd. Kohalik nimekiri kirjeldab lähteplaani; edasise arenduse operatiivne seis asub tahvlil.

Prioriteedid: **P0** = MVP jaoks vältimatu; **P1** = oluline järgmine täiendus; **P2** = hilisem lisaväärtus. Sama prioriteediga tööde järjekord on allolevas tabelis. Punktid väljendavad suhtelist keerukust, mitte töötunde.

| ID | Kasutajalugu | Prioriteet | Punktid | Planeeritud periood |
|---|---|---|---:|---|
| [US-01](https://github.com/sljezov/kodumasinate-rent/issues/1) | Kliendina soovin näha renditavaid kodumasinaid ja päevahindu, et valida sobiv seade. | P0 | 3 | Sprint 1 |
| [US-02](https://github.com/sljezov/kodumasinate-rent/issues/2) | Kliendina soovin kontrollida mudeli saadavust valitud kuupäevadel ja rendihinda, et oma renti planeerida. | P0 | 5 | Sprint 1 |
| [US-03](https://github.com/sljezov/kodumasinate-rent/issues/3) | Kliendina soovin esitada vaba seadme broneerimistaotluse, et see periood endale reserveerida. | P0 | 8 | Sprint 1 |
| [US-04](https://github.com/sljezov/kodumasinate-rent/issues/4) | Kliendina soovin näha oma broneeringuid ja nende olekut, et teada, kas võin seadmele järele tulla. | P0 | 3 | Sprint 1 |
| [US-05](https://github.com/sljezov/kodumasinate-rent/issues/5) | Renditöötajana soovin taotlusi kinnitada või põhjendusega tagasi lükata, et hallata tegelikku väljastamist. | P0 | 3 | Sprint 2 kandidaat |
| [US-06](https://github.com/sljezov/kodumasinate-rent/issues/6) | Renditöötajana soovin registreerida seadme väljastamise ja kohapeal tasumise, et teada, kelle käes seade on. | P0 | 3 | Sprint 2 kandidaat |
| [US-07](https://github.com/sljezov/kodumasinate-rent/issues/7) | Renditöötajana soovin registreerida tagastamise ja seadme seisukorra, et lõpetada rent ja märgata hooldusvajadust. | P0 | 5 | Sprint 2 kandidaat |
| [US-08](https://github.com/sljezov/kodumasinate-rent/issues/8) | Kliendina soovin enne rendi alguskuupäeva broneeringu tühistada, et vabastada seadme teistele klientidele. | P0 | 3 | Sprint 2 kandidaat |
| [US-09](https://github.com/sljezov/kodumasinate-rent/issues/9) | Administraatorina soovin hallata seadmemudeleid, eksemplare ja päevahindu, et kataloog vastaks tegelikule inventarile. | P0 | 5 | Sprint 2 kandidaat |
| [US-10](https://github.com/sljezov/kodumasinate-rent/issues/10) | Renditöötajana soovin märkida eksemplari hooldusse või uuesti töökorda, et rikkis seadet ei saaks rentida. | P0 | 3 | Sprint 2 kandidaat |
| [US-11](https://github.com/sljezov/kodumasinate-rent/issues/11) | Kliendina soovin saada enne tagastamispäeva e-kirja meeldetuletuse, et seade õigel ajal tagastada. | P1 | 5 | Hiljem |
| [US-12](https://github.com/sljezov/kodumasinate-rent/issues/12) | Ettevõtte omanikuna soovin näha rendikäibe ja seadmete kasutuse aruannet, et kavandada seadmete juurdeostu. | P2 | 5 | Hiljem |

**[EN-01](https://github.com/sljezov/kodumasinate-rent/issues/13) – tehniline eeldus (P0, 5 punkti, Sprint 1):** arenduskeskkond, andmebaasimigratsioonid, testkeskkond ja autentimine/rollipõhine ligipääs. See on kasutajalugusid võimaldav tehniline töö, mitte kasutajaloo asemel arvestatav lugu. Eeldab testkontosid kliendile ja töötajale; paroolid on räsitud ning õigusi kontrollib server.

## Vastuvõtukriteeriumid

### US-01 – kataloog

- Klient näeb iga aktiivse mudeli nime, kirjeldust ja päevahinda eurodes.
- Mudel võib olla kataloogis ka siis, kui selle kõik eksemplarid on hetkel rendis; saadavus sõltub perioodist.
- Mitteaktiivne mudel ei ilmu uue rendi valikusse; varasem broneering jääb nähtavaks.

### US-02 – saadavus ja hind

- Klient valib algus- ja lõppkuupäeva; mineviku algus ja algusest varasem lõpp annavad arusaadava veateate.
- Vaba mudel tähendab, et vähemalt üks töökorras eksemplar on kogu perioodiks vaba. Ootel ja kinnitatud broneeringud blokeerivad perioodi; välja antud ja hilinenud seadet ei lubata uueks väljastamiseks.
- 10.–12. novembri rent päevahinnaga 20 eurot maksab 60 eurot. Samapäevane rent maksab 20 eurot.
- Hind ja saadavus kontrollitakse uuesti broneerimise hetkel, sest kataloogivaade ei reserveeri seadet.

### US-03 – broneerimine

- Sisselogitud klient saab valida mudeli ja perioodi ning kinnitada taotluse; puuduv telefon küsitakse enne esitamist.
- Edu korral tekib unikaalse numbriga broneering olekus „ootab kinnitamist”, eraldatud eksemplari ja lukustatud hinnaga. Kuupäevad blokeeritakse kohe.
- Viimase vaba eksemplari kaks samaaegset kattuvat taotlust annavad ühe õnnestumise ja ühe selge konfliktiteate; kontroll toimub andmebaasis.

### US-04 – minu broneeringud

- Klient näeb enda broneeringu numbrit, mudelit, perioodi, hinda ja olekut.
- Teise kliendi broneeringule URL-i või API kaudu ligi ei pääse.
- Ootel taotlusel öeldakse selgelt, et rendipunkti tulek eeldab töötaja kinnitust.

### US-05 – otsus

- Töötaja näeb ootel taotlusi vanimast alates ja saab neid kinnitada või tagasi lükata.
- Tagasilükkamine nõuab põhjendust ning vabastab perioodi.
- Otsuse tegija ja aeg salvestatakse; tavaklient ei saa töötaja toimingut teha.

### US-06 – väljastamine

- Väljastada saab ainult kinnitatud broneeringu töökorras ja tegelikult kohal oleva eksemplari.
- Töötaja salvestab üleandmise aja, seadme seisukorra ning tasutud summa ja makseviisi; kogutud andmed ei sisalda pangakaardiandmeid.
- Broneering muutub väljastatuks. Kui varasem klient pole seadet tagastanud, toiming blokeeritakse ja töötaja saab selge teate.

### US-07 – tagastamine

- Tagastada saab ainult väljastatud seadme. Registreeritakse aeg ja seisukord ning broneering lõpetatakse.
- Rikke märkimine muudab eksemplari hoolduses olevaks ja näitab mõjutatud tulevasi broneeringuid.
- Hilinenud rent kuvatakse töötajale eristatult; automaatset viivist MVP ei arvuta.

### US-08 – tühistamine

- Klient saab enda ootel või kinnitatud broneeringu tühistada enne alguskuupäeva.
- Tühistatud broneering jääb ajalukku ning selle periood vabaneb.
- Väljastatud broneeringu või teise kliendi broneeringu tühistamise katse lükatakse tagasi.

### US-09 – kataloogi haldus

- Administraator lisab mudeli, päevahinna ja unikaalse inventarinumbriga eksemplari.
- Negatiivset hinda ega korduvat inventarinumbrit ei lubata.
- Hinnamuutus ei muuda varasemate broneeringute hinnasnapshot'i; kasutatud eksemplar eemaldatakse valikust arhiveerimise, mitte ajaloo kustutamise kaudu.

### US-10 – hooldus

- Hoolduses olev eksemplar ei osale uue broneeringu saadavusarvestuses.
- Hooldusse märkimine nõuab põhjust ja näitab kattuvaid tulevasi taotlusi; töötaja lahendab need asenduse või põhjendatud tühistamisega.
- Hooldusest vabastamine ei tühista olemasolevaid broneeringuid ega tee juba reserveeritud perioodi vabaks.

### US-11 – meeldetuletus

- Kinnitatud või väljastatud rendile saadetakse päev enne lõppkuupäeva meeldetuletus, kui see on endiselt aktiivne.
- Sama broneeringu sama päeva meeldetuletust ei saadeta topelt; ebaõnnestunud saatmine logitakse ja seda saab korrata.
- Tühistatud või juba tagastatud rendile teadet ei saadeta.

### US-12 – aruandlus

- Omanik saab valida perioodi ning näha väljastamisel registreeritud laekumiste kogusummat ja eksemplaride rendipäevi.
- Tühistatud taotlusi ei käsitleta käibena ning koondandmeid näeb ainult vastava õigusega roll.
- Aruanne ei asenda raamatupidamist; valemid ja kuupäevade tähendus on vaates kirjeldatud.

## Sõltuvused ja töö jälgimine

EN-01 võimaldab US-03 ja US-04. US-01 → US-02 → US-03 → US-05 → US-06 → US-07 kirjeldab põhivoo arendust. US-09 haldusliides võib tulla teises sprindis, sest esimene kasutab ettevalmistatud testandmeid. US-10 peab olema valmis enne pilooti. US-11 ja US-12 tulevad pärast põhivoo stabiilsuse kontrolli.

Tahvlil kasutatakse esialgu olekut Todo. Sprint 1 väärtus on määratud ainult esimese sprindi neljale loole ja EN-01 tööle; Sprint 2 on kandidaatplaan, mille kinnitab järgmine planeerimine. Arenduse käigus võetakse töö In Progress olekusse ja seotakse muudatuse pull request'iga. Done tähendab Definition of Done'i täitmist, mitte üksnes dokumendi olemasolu.
