# Git ja versiooniplaan

## Git-i kasutamine

Dokumente ja muudetavat `.drawio` skeemi hoitakse [GitHubi repositooriumis](https://github.com/sljezov/kodumasinate-rent). Kavandamise muudatused salvestatakse sisuliste osadena: lähteülesanne, arendusprotsess, kasutajalood, arhitektuur, CASE-võrdlus ja versiooniplaan.

Commit'i teema ja sisu kirjutatakse väiketähtedega. Näiteks `lisa prioriseeritud kasutajalood ja vastuvõtukriteeriumid` ütleb, mida muudeti. Täpseid tegelikke kirjeid näeb [commit'ide ajaloos](https://github.com/sljezov/kodumasinate-rent/commits/main/) või käsuga `git log --oneline`. Vähemalt viis commit'i peavad väljendama eri sisuga tööd, mitte ühe faili kunstlikku tükeldamist.

Edasises arenduses tehakse iga töö jaoks eraldi haru, näiteks `feature/us-03-broneerimine`. Pull request viitab issue'le, sisaldab muudatuse selgitust ja kontrolli tulemusi ning liidetakse pärast ülevaatust `main` harusse. See on kavandatav arenduspraktika; kodutöö dokumentatsiooni koostamine ei tõenda selle töövoo läbimist.

## SemVer-i kasutamise kokkulepe

Rakenduse tulevased väljalasked järgivad kuju **MAJOR.MINOR.PATCH**. SemVer eeldab avaliku liidese määratlemist: selle projekti puhul on see dokumenteeritud väliste integratsioonide liides ja ekspordiformaadid, kui need lisanduvad. Brauseri HTML-lehe sisemine struktuur ei ole garanteeritud integratsiooniliides. Esialgu on rakendus serveris renderdatud veebirakendus ning väliseid integratsioone ei ole.

| Muutus | Näide | Põhjendus |
|---|---|---|
| PATCH: `1.0.0 → 1.0.1` | Parandatakse sama päeva rendihinna arvutusviga | Tagasiühilduv veaparandus; lubatud liides ja käitumisleping jäävad kehtima |
| MINOR: `1.0.1 → 1.1.0` | Lisatakse vabatahtlik tagastamise e-kirja meeldetuletus | Uus funktsioon säilitab olemasoleva kasutuse ja liideste ühilduvuse; PATCH lähtestub |
| MAJOR: `1.4.2 → 2.0.0` | Kui v1 CSV-eksport on avaldatud ja dokumenteeritud, asendatakse selle kuupäevavorming ning eemaldatakse vana vorming | Senised integratsioonid vajavad muudatust; MINOR ja PATCH lähtestuvad |

MAJOR-numbrit ei tõsteta üksnes seetõttu, et töö oli suur või kasutajaliides sai uue kujunduse. MAJOR-näite ekspordiliides on tulevikustsenaarium, mitte MVP olemasolev funktsioon. Enne selle avaldamist tuleb väljade nimed, tüübid ja tähendus täpselt dokumenteerida.

## Kavandatud väljalasked

| Versioon | Sisu ja valmidus |
|---|---|
| `0.1.0` | Esimese sprindi töötav inkrement testkeskkonnas; ebastabiilne arendusversioon |
| `0.2.0` | Töötaja kinnitus, väljastamine, tagastamine ja inventarihaldus; kontrollitav MVP kandidaat |
| `1.0.0-rc.1` | Funktsioonide ulatus fikseeritud, piloot ja väljalaske kontroll; eelväljalase |
| `1.0.0` | Piloot heaks kiidetud, põhivoo nõuded täidetud, varundus ja taastamine kontrollitud; esimene stabiilne väljalase |
| `1.0.1` | Vajadusel tagasiühilduvad veaparandused |
| `1.1.0` | Meeldetuletused, kui nende arendus ja kontroll on lõpetatud |

Versioonid `0.x.y` tähistavad algset arendust ning nende liidesed võivad muutuda. `rc` tähendab release candidate'i. Need versioonid on **plaan**, mitte olemasolevad rakenduse väljalasked. Käesolevale dokumentatsioonile ei panda eksitavat rakenduse `v1.0.0` silti.

## Väljalaske töövoog

1. Valmis tööd, läbivad kontrollid ja Product Owneri kinnitus määravad väljalaske sisu.
2. Määratakse ühilduvusele vastav versioon ning lisatakse väljalaskemärkmetesse uued võimalused, parandused ja võimalikud katkestavad muudatused.
3. Valitud commit märgistatakse näiteks Git tag'iga `v1.0.0` ja sellest luuakse GitHub Release. Versioon viitab konkreetsele muutumatule koodiseisule.
4. Sama kontrollitud ehitus viiakse testkeskkonnast tootmisse. Versioon kuvatakse rakenduse infovaates ja seotakse veateadetega.
5. Enne migratsiooni tehakse varukoopia, kontrollitakse käivitusjärgset põhivoogu ja järgitakse arhitektuuridokumendi tagasipöördumisplaani. Avaldatud versiooni sisu ei kirjutata üle; parandus saab uue versiooninumbri.

Allikas: [Semantic Versioning 2.0.0](https://semver.org/). Versioonide funktsionaalne sisu on selle projekti väljalaskeplaan.
