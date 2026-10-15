# Lähteülesanne

## Probleem ja eesmärk

Väikesel kodumasinate rendiettevõttel on mitut tüüpi seadmeid, mõnda mudelit mitu eksemplari. Telefonibroneeringute ja eraldi tabeli kasutamisel võib sama seade saada mitu broneeringut. Töötaja peab käsitsi kontrollima tagastusi ja hooldusvajadust.

Veebirakendus koondab saadavuse, broneeringud ja renditoimingud. Esimese versiooni edu hinnatakse piloodis: testides ei teki kattuvaid kinnitatud broneeringuid, töötaja saab näha kõiki väljastatud seadmeid ning klient suudab juhendamiseta esitada broneerimistaotluse. Piloodi siht on vähemalt 4 edukat ülesande täitmist 5 proovikasutajast. Need on eesmärgid, mitte juba mõõdetud tulemused.

## Rollid

| Roll | Vajadus ja õigused |
|---|---|
| Külastaja | Vaatab seadmeid, hindu ja saadavust |
| Klient | Logib sisse, esitab broneeringu, näeb oma broneeringuid ja tühistab lubatud broneeringu |
| Renditöötaja | Kinnitab või lükkab tagasi taotlusi, registreerib väljastamise ja tagastamise, märgib seadme hooldusse |
| Administraator | Haldab seadmeid, hindu ja töötajate rolle; võib täita ka renditöötaja ülesandeid |

## Esimese versiooni piirid

Üks rendipunkt ning üks seade ühe broneeringu kohta. Klient valib mudeli ja kuupäevad; süsteem eraldab konkreetse eksemplari. Näiteks on mudel „tekstiilipesur X” ja eksemplar „TP-003”. Mudelil on kirjeldus ja päevahind; eksemplaril inventarinumber ja tehniline olek.

Saadavus, sisselogimine, broneerimine, töötaja kinnitus, väljastamine, tagastamine, tühistamine ja hooldusse märkimine moodustavad MVP. E-kirja meeldetuletused ja aruanded lisanduvad hiljem. Veebimakset, automaatset viivisearvestust ega kojuvedu MVP ei sisalda.

## Ärireeglid

1. Rent on kalendripäevade kaupa. Nii algus- kui ka lõppkuupäev arvestatakse hinna sisse. Sama päeva rent kestab ühe tasulise päeva. Hinnasnapshot = päevade arv × broneerimise hetke päevahind.
2. Rendiperioodi lõpp ei või olla enne algust ning algus ei või olla minevikus. Kuupäevad tõlgendatakse rendipunkti ajavööndis Europe/Tallinn.
3. Sama eksemplari blokeerivad olekud on „ootab kinnitamist”, „kinnitatud” ja „väljastatud”. Tagastuspäeval seadet uuesti välja ei rendita: varaseim järgmine algus on järgmisel päeval. Kaks perioodi kattuvad, kui uus algus ≤ olemasolev lõpp ja uus lõpp ≥ olemasolev algus.
4. Broneeringu loomisel eraldatakse vaba eksemplar atomaarse andmebaasitehinguga. Kui kaks klienti broneerivad korraga viimase eksemplari, õnnestub ainult üks taotlus. Teisele kuvatakse saadavuse muutumise teade.
5. Töötaja vaatab ootel taotlused üle ühe tööpäeva jooksul. Tagasilükkamine või kliendi tühistamine vabastab perioodi. Tähtaja ületanud ootel taotlused vajavad töötaja otsust; MVP ei tühista neid automaatselt.
6. Väljastada saab ainult kinnitatud broneeringu. Töötaja registreerib kohapeal tasumise ja seadme seisukorra. Süsteem ei töötle pangakaardiandmeid.
7. Tagastamisel märgitakse seisukord. Korras seade muutub saadavaks vastavalt kalendrireeglile; rikkis seade läheb hooldusse. Hilinenud tagastusega väljastatud eksemplar ei ole uueks väljastamiseks saadaval. Töötaja lahendab mõjutatud tulevased broneeringud kliendiga ja võimalusel eraldab teise vaba eksemplari.
8. Klient saab tühistada ootel või kinnitatud broneeringu enne rendi alguskuupäeva. Sama päeva erandid lahendab töötaja ja põhjendus salvestatakse.
9. Hinnakirja muutus ei muuda varem broneeritud hinda. Töötaja otsused ja olekumuutused salvestatakse koos tegija ning ajatempliga.
10. Seadme hooldusse märkimisel näidatakse mõjutatud tulevasi broneeringuid. Neid ei kustutata; töötaja korraldab asenduse või tühistamise koos põhjendusega.

## Kvaliteedinõuded ja kontroll

| Nõue | Kavandatud kontroll |
|---|---|
| Klient näeb ainult enda broneeringuid | API õiguste test kahe eri kliendiga |
| Topeltbroneerimine on välistatud | Kahe samaaegse taotluse integratsioonitest ja andmebaasipiirang |
| Põhivoog töötab telefonis | Käsitsi katse 360 px laiuses vaates ja klaviatuuriga |
| Otsused on jälgitavad | Oleku muutmise järel kontrollitakse tegijat, aega ja põhjendust |
| Andmeid saab taastada | Igapäevane varukoopia; enne pilooti taastamiskatse eraldi keskkonda |
| Saadavuse päring on piisavalt kiire | Siht: 95% päringutest alla 2 s testkeskkonnas 50 samaaegse kasutaja ja 1000 eksemplari korral |

Isikuandmetena kavandatakse nimi, e-post ja telefon. Ligipääs on rollipõhine. Säilitustähtajad ja lepingutekst täpsustatakse enne päris kasutuselevõttu; kodutöö ei väida juriidilist vastavust kontrollituks.
