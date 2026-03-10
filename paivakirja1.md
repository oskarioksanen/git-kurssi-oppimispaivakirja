# Oppimispäiväkirja: Paikallinen git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet?__

Olen käyttänyt Git-versionhallintaa aikaisemmin opinnoissani, joten ensimmäisen osion tehtävät olivat suhteellisen helppoja. Opin kuitenkin monia uusia asioita, kuten talletettujen muutosten perumisesta sekä haarojen yhdistämisen pikakelauksesta. Minua auttoi oppimaan lähinnä kurssin materiaali ja siellä annetut hyvät esimerkit. Esteet selvitin lukemalla kurssin materiaalia sekä käyttämällä Googlea.

## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| git init | Alustaa repositorion |
| git clone | Kopioi olemassa olevan repositorion omalle koneelle |
| git status | Kertoo työhakemiston tiedostojen Git-tilan (mitä muutoksia tiedostoihin on tehty ja mitä seuraamattomia tiedostoja työhakemistossa on) |
| git add | Lisää tiedoston / koko hakemiston tiedostot, joita ei seurata tai joihin on tehty muutoksia, seuraavaan muutokseen. |
| git commit | Tekee talletuksen lisätyistä tiedostoista. |
| git log | Näyttää talletusten historian. |
| git diff | Näyttää työhakemiston tiedostoihin tehdyt muutokset verrattuna viimeisimpään talletukseen |
| git rm | Poistaa tiedoston työhakemistosta ja Git-hallinnasta. |
| git mv | Nimeää tiedoston tai siirtää tiedoston toiseen hakemistoon |
| git tag | Lisää viimeisimpään talletukseen tunnisteen. |
| git checkout | Siirtyy tietyn talletuksen tilanteeseen. |
| git switch <haara> | Vaihtaa <haara> haaraan. |
| git reset | Peruuttaa tiedoston lisäämisen seuraavaan talletukseen. |
| git restore | Peruuttaa työtilaan tehdyt muutokset, joita ei ole talletettu. |
| git revert <talletus> | Peruuttaa <talletus> talletuksen muutokset. |
| git branch | Luo uuden haaran. |
| git branch -l | Listaa haarat. |
| git merge <haara> | Yhdistää <haara> haaran nykyiseen haaraan (haaraan, jossa ollaan tällä hetkellä). |
| git merge --no-ff <haara> | Yhdistää <haara> haaran nykyiseen haaraan ilman pikakelausta (versionhistoriaan tulee erillinen yhdistämistalletus). |