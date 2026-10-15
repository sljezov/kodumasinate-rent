# Kaitsmise juhis ja nõuete kaetus

## Lühike tutvustus oma sõnadega

„Kavandasin väikese kodumasinate rendiettevõtte veebirakenduse. Selle peamine eesmärk on vältida sama seadme topeltbroneerimist ja anda ülevaade rendi elutsüklist. Klient valib seadme ning perioodi, töötaja kinnitab taotluse ja registreerib väljastamise ning tagastamise. Valisin iteratiivse arenduse ja Scrumi, et kontrollida kasutajatega ärireegleid väikeste sammude kaupa. Tehniliselt piisab ühest kihilisest rakendusest ja andmebaasist.”

Kohanda see tekst enda sõnavarale ja veendu, et oskad iga väidet näitega selgitada.

## Näitamise järjekord

1. Ava README ja selgita probleemi, kasutajaid ning MVP piire.
2. Võrdle koskmudelit iteratiivse mudeliga. Selgita, et Scrum korraldab iteratiivset tööd, aga ei ole arhitektuur.
3. Ava Projects-tahvel. Näita US-03 vastuvõtukriteeriume ning esimese sprindi viit tööd ja nende 24 punkti.
4. Ava `.drawio` lähtefail diagrams.net-is. Jälgi brauserist andmebaasini broneeringu andmevoogu ja muuda ühe komponendi teksti.
5. Selgita, miks monoliit sobib väikesele meeskonnale ja millal võiks teenuste eraldamine olla põhjendatud.
6. Näita GitHubi commit'ide ajalugu ja too üks näide iga SemVer-numbri muutusest.

## Küsimused, millele tasub vastus läbi mõelda

- Kuidas erinevad seadmemudel ja konkreetne eksemplar?
- Mis juhtub, kui kaks klienti vajutavad korraga viimase seadme broneerimise nuppu?
- Miks ei piisa saadavuse kontrollimisest ainult brauseris?
- Mida teha, kui seade tagastatakse rikkis ja sellel on järgmine broneering?
- Miks ei ole esimese sprindi tulemus veel kogu MVP?
- Kuidas muutub plaan, kui klient soovib keset sprinti kojuvedu?
- Milline osa dokumentatsioonist kirjeldab tehtud kavandamist ja milline tulevast arendust?

## Hindamiskriteeriumide kaart

| Ülesande osa | Tõend |
|---|---|
| 1. Elutsükkel, kaks mudelit, valik ja nõuete muutmine | [Arendusprotsess](02-arendusprotsess.md) |
| 2. Metoodika, vähemalt kuus kasutajalugu, prioriteedid, esimene periood ja töövahend | [12 kasutajalugu](03-backlog.md), [sprindiplaan](02-arendusprotsess.md), [Projects](https://github.com/users/sljezov/projects/4) |
| 3. Vähemalt kaks vahendit, modelleerimine, võrdlus ja muutmise valmidus | [CASE-vahendid](05-case-vahendid.md), drawio lähtefail ja GitHubi tahvel |
| 4. Rakenduse tüüp, arhitektuur, skeem, andmevoog ja alternatiiv | [Arhitektuur](04-arhitektuur.md) ja [muudetav skeem](../diagrams/arhitektuur.drawio) |
| 5. GitHub, vähemalt viis sisulist commit'i ja SemVer | [Ajalugu](https://github.com/sljezov/kodumasinate-rent/commits/main/), [versiooniplaan](06-versiooniplaan.md) |
| 6. Esitatav link ja materjalide leitavus | [Repositoorium](https://github.com/sljezov/kodumasinate-rent), [README](../README.md) |

## Enne esitamist

- Kontrolli õpetaja mahu-, tähtaja- ja tehisintellekti kasutamise tingimusi.
- Vaata üle eeldused: üks rendipunkt, päevapõhine rent, järeletulemine ja kohapeal tasumine.
- Harjuta skeemi avamist ja muutmist enda brauseris ning loo liigutamist tahvlil.
- Veendu, et mõlemad GitHubi lingid avanevad õpetajale ning oskad valikuid enda sõnadega põhjendada.
