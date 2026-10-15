# CASE-vahendid

CASE tähendab tarkvaraarenduse tegevusi toetavaid arvutipõhiseid vahendeid. Selles projektis kasutame modelleerimiseks **diagrams.net-i** ning tööde kavandamiseks ja jälgimiseks **GitHub Projectsi** koos GitHub Issuesiga. Git säilitab dokumentide ja skeemi muudatuste ajaloo.

## Kasutamine projektis

| Vahend | Toetatav tegevus | Projekti konkreetne tulemus |
|---|---|---|
| diagrams.net | Komponentide, piiride ja seoste modelleerimine; visuaalne ülevaatus | [Muudetav arhitektuuriskeem](../diagrams/arhitektuur.drawio) ja [SVG-eelvaade](../diagrams/arhitektuur.svg) |
| GitHub Projects + Issues | Kasutajalood, prioriseerimine, sprindivalik, vastuvõtukriteeriumid ja töö edenemine | [13 tööga tahvel](https://github.com/users/sljezov/projects/4): 12 kasutajalugu ja tehniline eeldus |
| Git / GitHub repositoorium | Dokumentatsiooni ja skeemi versioonimine ning muudatuste ülevaatus | Vähemalt viis eri sisuga commit'i, materjalide ühine asukoht ja seos töödega |

## Modelleerimise CASE-vahendite võrdlus

| Omadus | diagrams.net | PlantUML |
|---|---|---|
| Tööviis | Kujundeid ja nooli muudetakse graafilises redaktoris | Diagramm kirjeldatakse tekstilise lähtekoodina ja renderdatakse |
| Tugevus | Kiire visuaalne paigutus ning lihtne diagrammi kaitsmisel muuta | Tekstimuudatusi on Git-is lihtne lugeda ja diagramme saab automaatselt genereerida |
| Puudus | XML-faili muudatusi on keerulisem käsitsi võrrelda ja liita | Vajab süntaksi õppimist; täpne paigutus sõltub renderdajast |
| Sobivus siin | Valitud arhitektuuri esitamiseks ja komponendi kiireks lisamiseks | Hea alternatiiv, kui olulisemaks muutub automaatne genereerimine või palju UML-diagramme |

Valin diagrams.net-i, sest selles töös on tähtis arusaadav komponentide skeem ja võimalus seda kaitsmisel kohapeal muuta. PlantUML-i võrreldakse alternatiivina; selle kasutamist projektis ei väideta. GitHub Projects täiendab diagrammitööriista tööde juhtimisega, kuid ei asenda süsteemi modelleerimist.

## Skeemi muutmise harjutus kaitsmiseks

1. Laadi repositooriumist `diagrams/arhitektuur.drawio` alla ja ava [diagrams.net](https://app.diagrams.net/). Vali seadmesse salvestamine ning **File → Open From → Device**.
2. Vali „Äriloogikakiht” ja muuda selle teksti. Skeemi kastid, tekstid ja nooled peavad olema eraldi valitavad.
3. Harjutuse näitena lisa väljapoole rakenduse piiri „E-posti teenus (tulevane US-11)” ning ühenda see äriloogikaga. Selgita, et see on uus nõue ja muudab algset MVP skeemi.
4. Salvesta muudetud fail `.drawio` kujul ning ekspordi uus SVG-eelvaade sama nimega. Eelvaade ja lähtefail peavad kirjeldama sama arhitektuuri.
5. Vaata Git diff üle ja tee sisuline väiketähtedega commit. Harjutusfaili ei pea põhilahendusse lisama, kui teavitusi MVP-sse ei võeta.

Tahvli näitena ava US-03, selgita P0-prioriteeti ja samaaegse broneerimise kriteeriumi ning filtreeri Sprint 1 tööd. Kui näitad kaardi liigutamist demona, taasta kavandatud töö olek Todo; demo ei tähenda funktsiooni valmimist.

Allikad: [draw.io failivormid](https://www.drawio.com/doc/faq/save-file-formats), [PlantUML-i komponendidiagrammid](https://plantuml.com/component-diagram), [GitHub Projectsi dokumentatsioon](https://docs.github.com/en/issues/planning-and-tracking-with-projects). Vahendite sobivuse hinnang on tehtud selle kodutöö vajaduste järgi.
