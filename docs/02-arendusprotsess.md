# Arendusprotsess ja metoodika

## Elutsükkel ideest hoolduseni

| Etapp | Eesmärk | Tegevused ja tulemus |
|---|---|---|
| 1. Probleemi avastamine | Kontrollida, et lahendame tegelikku vajadust | Intervjuu ettevõtte omaniku ja töötajaga, praeguse rendiprotsessi vaatlus; probleem ja edu mõõdikud |
| 2. Nõuete analüüs | Leppida kokku MVP ja ärireeglid | Rollid, kasutajalood, vastuvõtukriteeriumid, hinnastamise ja kattuvuse reeglid; prioriseeritud backlog |
| 3. Modelleerimine ja disain | Vähendada tehnilisi ja kasutatavuse riske | Arhitektuuriskeem, andmemudel, lihtne broneerimisvaate visand; kliendiga üle vaadatud kavand |
| 4. Iteratiivne arendus | Luua väikeste osade kaupa töötav lahendus | Kahenädalased sprindid, kood, ülevaatused ja automaattestid; kontrollitav inkrement |
| 5. Kontroll ja piloot | Veenduda, et lahendus täidab vajaduse | Igas sprindis testimine; enne käivitamist kogu rendivoo, õiguste, samaaegsuse ja taastamise kontroll; piloot ühe töötaja ja prooviklientidega |
| 6. Kasutuselevõtt | Viia kontrollitud versioon päris kasutusse | Seadmete algandmed, töötaja juhendamine, varukoopia, väljalaskemärge ja tagasipöördumisplaan |
| 7. Hooldus ja edasiarendus | Hoida süsteem töökindel ja vajadustega kooskõlas | Vigade jälgimine, turvauuendused, varundus ja tagasiside; uued tööd lähevad backlogsse |

Etapid ei ole ühekordsed lukustatud väravad. Analüüsi, disaini, arendust ja testimist korratakse iga inkremendi jaoks. Testimine ei jää projekti lõppu.

## Protsessimudelite võrdlus

| Aspekt | Koskmudel | Iteratiivne ja inkrementaalne mudel |
|---|---|---|
| Töö korraldus | Nõuded, disain, arendus ja testimine järgnevad suuremate etappidena | Lahendus valmib korduvate tsüklitena ning kasutatav funktsionaalsus kasvab |
| Nõuete sobivus | Sobib hästi, kui nõuded on alguses selged ja stabiilsed | Sobib, kui detailid täpsustuvad kasutajate tagasisidest |
| Tagasiside | Töötava terviku tagasiside saabub sageli hiljem | Töötavat osa saab regulaarselt demonstreerida |
| Muudatused | Hiline muudatus võib nõuda varasemate etappide ümbertegemist | Muudatuse saab hinnata ja järgmise tsükli tööde hulka järjestada |
| Risk | Viga olulises eelduses võib selguda hilja | Varased inkremendid aitavad kontrollida suurimaid riske |
| Puudus | Hiline õppimine ja kallis ümbertegemine | Vajab aktiivset prioriseerimist ning arhitektuuri ja dokumentatsiooni järjepidevat korrastamist |

Valin **iteratiivse ja inkrementaalse mudeli**, sest rendiettevõtte kasutajad saavad broneerimisvoogu proovides täpsustada kinnitamist, tagastamist ja erandolukordi. Topeltbroneerimise riski kontrollime juba esimeses sprindis. Koskmudel oleks põhjendatum fikseeritud ja eelnevalt põhjalikult kontrollitud nõuete korral.

## Arendusmetoodika: Scrum

Protsessimudel kirjeldab lahenduse kujunemist; Scrum annab sellele konkreetse koostöö- ja planeerimisraamistiku. Kavandatud arendusmeeskond koosneb kolmest arendajast. Rendiettevõtte esindaja täidab Product Owneri vastutust ja järjestab Product Backlogi; Scrum Master aitab hoida protsessi toimivana ja eemaldada takistusi. Vastutused on eristatavad, isegi kui väikeses meeskonnas mõni inimene täidab mitut ülesannet.

Valin kahenädalased sprindid. Selge Sprint Goal aitab keskenduda ühele kasutajale väärtust loovale tulemusele. Rendiäris on otstarbekas näidata regulaarselt tervet töövoogu, selle asemel et valmistada pikalt eraldi tehnilisi kihte.

Kodutöö koostamine üksi ei ole päris Scrum-meeskonna töö. Siin kirjeldatud rollid, sündmused ja sprindid on tulevase arenduse plaan; toimunud koosolekuid ega mõõdetud kiirust ei väideta.

### Planeerimine ja jälgimine

- **Product Backlogi täpsustamine:** Product Owner ja arendajad jagavad suuremad lood väiksemaks, lisavad kriteeriumid, hindavad ning korrastavad sõltuvused.
- **Sprint Planning:** Product Owner tutvustab prioriteete; arendajad valivad realistliku töömahu ja koostavad Sprint Backlogi koos Sprint Goaliga.
- **Daily Scrum:** arendajad hindavad kuni 15 minutiga edenemist Sprint Goali suunas ning kohandavad päevaplaani. Takistused märgitakse tahvlile.
- **Sprint Review:** töötajale ja tellijale näidatakse päriselt töötavat inkrementi, kogutakse tagasisidet ning kohandatakse Product Backlogi.
- **Sprint Retrospective:** meeskond valib konkreetse parenduse järgmise sprindi töökorraldusse.

GitHub Projects sisaldab kogu Product Backlogi. Väljad **Status**, **Prioriteet**, **Sprint** ja **Punktid** näitavad töö seisu, väärtust ja mahtu. Tahvli põhiveerud on Todo, In Progress ja Done. Todo sisaldab ka tulevikutöid; esimese sprindi töid eristab Sprint-väli. Issue märgitakse Done alles siis, kui vastuvõtukriteeriumid ja Definition of Done on täidetud. Arendusülesanded on alguses Todo.

Töö edenemist jälgitakse lõpetatud kasutajalugude, allesjäänud töö ja takistuste kaudu. Punkte ei kasutata üksikisiku tulemuslikkuse mõõtmiseks. Esimese sprindi järel hinnatakse tegeliku kogemuse põhjal järgmist mahtu.

### Definition of Done

Kasutajalugu on valmis, kui vastuvõtukriteeriumid on kontrollitud, muudatus on üle vaadatud, asjakohased ühik- ja integratsioonitestid läbivad kontrolli, õigused ja vigased sisendid on käsitletud, vajalik dokumentatsioon on uuendatud ning funktsioon töötab testkeskkonnas. Kataloogi puhul kontrollitakse ka mobiilivaadet; broneerimise puhul samaaegseid taotlusi. Valmis märkimine ei eelda eraldi tootmisse avaldamist iga loo järel.

## Esimene sprint: kaks nädalat

**Sprint Goal:** klient saab vaadata seadmete saadavust ning esitada ja hiljem näha broneerimistaotlust; süsteem välistab sama eksemplari kattuva broneerimise.

Eeldatav maht: US-01 (3), US-02 (5), US-03 (8), US-04 (3) ja tehniline töö EN-01 (5), kokku **24 punkti**. See on esialgne planeerimishinnang kolmele arendajale, mitte lubadus ega ajalooline velocity. Kahe paralleelse broneeringu katse on sprindi kriitiline kontroll. Täielik MVP valmib alles pärast renditöötaja voo lisamist.

| Aeg | Kavandatud tegevused |
|---|---|
| Päev 1 | Sprint Planning, ärireeglite täpsustamine, lugude jagamine tehnilisteks ülesanneteks |
| Päevad 1–3 | EN-01: projekti karkass, andmebaasimigratsioonid, testkeskkond, kliendi ja töötaja sisselogimine ning serveripoolsed õigused; US-01 kataloog |
| Päevad 3–5 | US-02 saadavus, kuupäevade kontroll ja hinnakalkulatsioon; andmebaasi kattuvuspiirangu tehniline kontroll |
| Päevad 5–8 | US-03 broneerimine ja samaaegsuse test; US-04 minu broneeringud koos õiguste kontrolliga |
| Päev 9 | Tervikvoo kontroll, vigade parandamine ja dokumentatsiooni uuendamine |
| Päev 10 | Sprint Review, tagasiside backlogsse ja Sprint Retrospective |

Teine sprint keskendub US-05…US-10 lugudele; lõplik valik ja maht tehakse pärast esimese sprindi tulemusi. E-kirjad ja aruanded ei ole MVP valmimise eeltingimus.

## Kui klient muudab arenduse keskel nõudeid

Näide: tellija soovib lisada kojuveo. Täpsustan, kas vaja on aadresse, tarnepiirkondi, ajavahemikke ja veohinda. Arendajad hindavad mõju andmemudelile, kasutajaliidesele, testidele, ajale ja kulule. Product Owner järjestab uue loo koos teiste töödega ning dokumenteerib otsuse.

Kui muudatus võib oodata, planeeritakse see järgmisse sprinti. Kui see on kiire, arutavad arendajad ja Product Owner sprindi ulatuse muutmist nii, et Sprint Goal säilib; näiteks eemaldatakse mõni samaväärse mahuga vähem tähtis töö. Uut tööd ei lisata märkamatult olemasolevale lubadusele. Kui Sprint Goal muutub kasutuks, võib Product Owner sprindi tühistada. Arhitektuur, vastuvõtukriteeriumid ja tööde hinnangud uuendatakse koos otsusega.

Allikas: [Scrum Guide](https://scrumguides.org/scrum-guide.html). Projekti rollid, töömaht ja näited on selle töö jaoks tehtud kavandamisotsused.
