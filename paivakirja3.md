# Oppimispäiväkirja: Git projektissa

__Mitä hyötyä voisi olla versionhallinnasta, jos kehität projektia yksin?__

- Versionhallinnan avulla voi palata aina edelliseen toimivaan versioon. 
  - Ei tarvitse murehtia siitä, että uudet muutokset rikkoisivat ohjelman.
  - Kirjoitettua koodia on helppo siistiä ja tehdä ohjelman logiikkaa 
  selkeämmäksi ilman pelkoa siitä, että samalla hajottaa ohjelman.

- Versionhallinnan avulla ohjelman kehittäminen usealla tietokoneella on helppoa.
  - Yhdellä tietokoneella tehdyt muutokset voi aina viedä etärepositorioon,
  jolloin toisella tietokoneella voi helposti jatkaa siitä mihin on viimeksi 
  jäänyt vetämällä muutokset etärepositoriosta paikalliseen repositorioon.
  - Näin ollen ohjelmia voi kehittää paikasta riippumatta, kunhan on laite, jolla
  kirjoittaa koodia.
  - Mahdollisesti suurin hyöty on se, että ei tarvitse pelätä, että ohjelman
  koodit häviäisi laitteen hajotessa, mikäli ohjelman koodit on viety
  etärepositorioon.

- Ohjelman  julkaisuversion (=päähaaran) voi pitää aina toimivana 
versionhallinnan avulla.
  - Uudelle toiminnallisuudelle voi aina luoda oman haaran, jolloin ominaisuutta
  voi kehittää rauhassa riippumatta päähaaran toiminnasta.
  - Mikäli julkaisuversion toiminnallisuuteen on tehtävä korjaus, muutos on 
  helposti tehtävissä riippumatta siitä, missä kunnossa kehityshaara on.

- Versionhallinnan avulla projektin dokumentointia ja muutoshistoriaa luodaan 
automaattisesti talletusviestejen muodossa.
  - Talletusviesteistä voi tutkia, mitä muutoksia on tehty ja milloin. Lisäksi 
  talletusviesteistä selviää, minkä takia kyseiset muutokset on tehty 
  (siis toivottavasti, mikälitalletusviestit ovat kuvaavia).
  - Lisäksi projektin edistymistä on helppo seurata.

__Mitä hyötyä voisi olla versionhallinnasta, jos projektissa on useita kehittäjiä?__

- Versionhallinnan avulla ohjelman samanaikainen kehittäminen on mahdollista.
  - Ilman versionhallintaa, tämä olisi todella monimutkaista sillä kehittäjät
  voisivat helposti poistaa huomaamatta toisten tekemiä muutoksia. Myös muutosten
  yhdistäminen olisi todella vaikeaa, ellei olisi sovittu selkeästi, mitä osia
  koodissa toinen muuttaa ja mitä puolestaan toinen.
  - Päällekkäisten muokkausten (ns. konfliktien) estäminen olisi huomattavasti
  vaikeampaa. Git-versionhallinta pysäyttää etärepositorioon vientiprosessin, 
  mikäli kaksi kehittäjää on muokannut samaa riviä. Tällöin kehittäjien on 
  kommunikoitava keskenään ja selvitettävä kumman muutokset säilytetään tai miten
  riviä täytyisi muuttaa, jotta se palvelisi molempia.

- Yhdistämispyyntöjen avulla koodin laadunvalvonta helpottuu.
  - Toiset kehittäjät / tekoäly voivat tarkistaa muutosten laadun ja käskeä 
  kehittäjää muuttamaan / korjaamaan koodia ennen kuin se yhdistetään päähaaraan.
  - Tämän avulla on helppo varmistua, että kaikki noudattavat sovittuja ohjeita 
  sekä sovittua ohjelmointityyliä esimerkiksi.

- Versionhallinnan avulla muutosten tekijä voidaan selvittää.
  - Versionhallinnan avulla voidaan selvittää, kuka on tehnyt kyseisen muutoksen 
  ja miksi muutos on tehty ohjelmaan (talletusviesti). Mikäli talletusviestistä 
  ei selviä, miksi muutos on tehty, kehittäjältä itseltään voidaan kysyä.

- Versionhallinnan avulla ohjelman ominaisuuksien kehittäminen on helppo jakaa 
usealle henkilölle.
  - Jokaisesta ominaisuudesta voidaan tehdä oma haara, jolloin kehittäjät voivat
  rauhassa kehittää ja testata oman ominaisuuden toimintaa ilman pelkoa, että 
  rikkoisi päähaaran koodin. 
  - Yksi projektin jäsen voi vastata pelkästään päähaaran toimminnasta ja siitä, 
  että uudet toiminnallisuudet eivät esimerkiksi riko päähaaran toimintaa.

__Miten järjestäisit projektitiimin versionhallinnan 3-4 hengen ohjelmistoprojektikurssilla? Laadi tiimiläisille lyhyt ohje, miten projektissa toimitaan.__

### RoboCop-projekti

Tervetuloa RoboCop-projektiin. Käytämme projektin versionhallinnassa yhteisiä 
sääntöjä, jotta projektin versionhallinnan historia pysyy siistinä. Yhteisten julkaisusääntöjen avulla vältämme myös ohjelman julkaisuversion turhia kaatumisia sekä bugeja.

#### 1. Päähaaran (main) muutokset
- Päähaaraan vietävä koodi on oltava aina testattua ja toimivaa, joten älä vie rikkinäistä koodia päähaaraan. 
- Päähaaraan ei myöskään koskaan suoraan tehdä muutoksia, vaan muutokset tehdään aina yhdistämispyyntöjen avulla.
  - Yhdistämispyynnön tarkastajiksi on aina valittava vähintään yksi toinen projektin kehittäjä tarkastamaan koodimuutokset.
  - Näin vältymme turhien huolimattomuusvirheiden pääsystä päähaaraan.

#### 2. Ominaisuushaarat
- Jokainen uusi ominaisuus ja korjaus tehdään omassa haarassaan.
- Haarat nimetään seuraavalla periaatteella: 
  - Ominaisuushaarat: `feature/<kuvaava nimi>`.
  - Korjaushaarat: `fix/<kuvaava nimi>`.
- Uuden haaran luominen ohje:
  1. Varmista, että paikallinen repositorio on ajan tasalla päähaaran kanssa: `git pull # Päähaarassa`
  2. Luo uusi haara (esimerkissä ominaisuus): `git switch -c feature/<ominaisuus>`
  3. Puske koodit ominaisuus- / korjaus-haaran etärepositorioon: `git push -u origin <ominaisuus>`
  4. Kun ominaisuus / korjaus on valmis, älä yhdistä haaraa päähaaraan suoraan, vaan tee yhdistämispyyntö.
  5. Kun yhdistämispyyntö on tarkastettu ja hyväksytty, hyväksy yhdistämispyyntö  ja yhdistä ominaisuushaara päähaaraan.

#### 3. Talletusviestit
- Talletusviestit kirjoitetaan englanniksi.
- Talletusviestien tekemisessä noudatetaan Conventional Commits -ohjetta (https://www.conventionalcommits.org/en/v1.0.0/).
- Esimerkki talletusviestistä, kun käyttöliittymän "Näytä kello" -napin toiminnallisuus on korjattu:
  - fix(UI): show time button functionality

#### 4. Konfliktit
- Mikäli pystyt ratkaisemaan konfliktin ilman, että poistat toisten tekemiä toiminnallisuuksia, ratkaise konflikti itse.
- Mikäli et ole varma, miten ratkaista konflikti, kysy projektin muilta osallistujilta apua yhteisellä Slack-kanavalla.


__Kommenttini opintojaksosta, esim. sisällöstä, materiaalista, työmäärästä, hyödyllisyydestä, työmäärästä. Mitä toivoisit olevan enemmän, mitä vähemmän?__

Mielestäni opintojakso oli todella informatiivinen ja opettavainen. Kurssin sisältö oli jaoteltu hyvin ja kurssin materiaali tuki mielestäni hyvin kurssin osaamistavoitteita sekä kurssin tehtäviä. Työmäärä oli mielestäni sopiva siihen nähden, että kurssi on 2 opintopisteen arvoinen. Olen itse käyttänyt hieman git:iä työelämässä sekä aiemmisssa opinnoissani ja mielestäni tämä kurssi antaa hyvät edellytykset git-versionhallinnan käyttämiseen. Minulle olisi varmasti ollut hyötyä käydä jo aikaisemminkin vastaava kurssi, koska tällöin olisin välttynyt monilta ongelmilta gitin käytössä. Kurssi ei kuitenkaan ollut itselleni mitenkään liian helppo vaan mielestäni tämä kurssi antaa sopivia haasteita myös henkilöille, jotka ovat käyttäneet git-versionhallintaa käytännössä, mutta eivät ole perehtyneet git-versionhallinnan toimintaan tarkemmin.

Toivoisin, että kurssilla käsiteltäisiin jatkossa myös `git rebase` -toimintoa, sillä olen huomannut sen olevan mainio työkalu käytännössä. Myös erilaisten ongelmatilanteiden ratkaiseminen kuten monimutkaisten konfliktien tai mergestä / pullista seuranneiden ongelmien (detached HEAD esim.) ratkaiseminen toisi lisää työkaluja git-versionhallinnan soveltamiseen työelämässä / käytännössä. Lisäksi henkilökohtaisesti koin mielenkiintoiseksi avoimen lähdekoodin projektien osion, joten olisin lukenut siitä lisää esimerkkejä, kuten kuinka voisi itse osallistua suuriin avoimen lähdekoodin projekteihin ja mistä projekteista olisi hyvä aloittaa.

Mielestäni oppimispäiväkirjan kirjoittaminen vei hieman turhan liikaa aikaa. Koen että tämä aika olisi ollut hyödyllisempää käyttää git-versionhallinnan käytön opetteluun lukemalla lisää teoriaa tai tekemällä lisää tehtäviä. Toinen vaihtoehto voisi olla harjoitustyö, jossa opiskelija tutustuisi esim. committien kirjoittamiseen (erilaisten standardoitujen tapojen avulla, kuten angular conventional commit) ja opettelisi käyttämään muutoslokia sekä versioimaan ohjelmistoja. Tämän lisäksi opiskelijoille voitaisiin kertoa, mitä hyötyä näiden hallitsemisesta on.