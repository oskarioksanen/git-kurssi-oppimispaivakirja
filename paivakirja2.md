# Oppimispäiväkirja: Hajautettu git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet, jotka vaikuttivat tehtävän suorittamiseen?__

Osion tehtävissä haastavaa oli etärepositorion asettaminen oletusarvoiseksi etärepositoriohaaraksi. Eli tehtävän 5 kohdassa 6-8 välillä `git status` komentoa ajaessa ei tapahtunut mitään muutosta. Tämä johtui varmaankin siitä, että kohdassa 3, kun puskin paikallisen haarani etärepositorioon, en käyttänyt `git push` komennossa valitsinta `-u` / `--set-upstream`. Tällöin paikallinen haarani ei todennäköisesti seurannut mitään etärepositoriohaaraa, jolloin paikallisessa repositoriossani ei näkynyt, että se olisi etärepositorion `origin/main` haaraa perässä vaikka etärepositorion `origin/main` haaraan oli tehty muutoksia. Tein kuitenkin tehtävän uudestaan siten, että ajoin paikallisessa repositoriossani komennon `git push -u origin main` valitsinta, jolloin tehtävän 5 kohdassa 8 `git status` komento sanoi, että paikallinen haarani on etärepositorion `origin/main` haaraa perässä.

Tehtävässä helppoa oli GitHub-projektin luominen ja sinne uusien tiedoston luominen. Myös muutosten hakeminen etärepositoriosta paikalliseen repositorioon oli suhteellisen helppoa.

Selvitin yllä mainitsemani ongelmat lukemalla kurssin materiaalin uudestaan läpi huolellisemmin. 

## Osiossa käyttämäni Git-komennot

| Komento | Kuvaus |
| --------| ------ |
| git remote add origin <url> | Yhdistää paikallisen repositorion verkossa olevaan etärepositorioon (sijaitsee <url> osoitteessa), jonka nimi on origin.  |
| git remote | Listaa etärepositoriot. |
| git remote rename | Uudelleennimeää etärepositorion. |
| git remote rm | Poistaa etärepositorion. |
| git remote show <etärepositorion nimi> | Listaa <etärepositorion nimi> etärepositorion tiedot. |
| git fetch <etärepositorio> | Lataa <etärepositorio> etärepositorion tiedot paikalliseen repositorioon. |
| git branch -r | Listaa etärepositorion haarat. |
| git checkout | Vaihtaa haaraa (`git switch`) sekä ajaa komennon `git restore`. |
| git merge | Yhdistää valitun haaran aktiiviseen haaraan. |
| git pull | Hakee haaran tiedot etärepositoriosta (`git fetch`) ja yhdistää tiedot paikallisiin haaroihin (`git merge`). |
| git push <etärepositorio> <paikallinen_haara> | Vie paikallisen haaran (<paikallinen_haara>) tiedot etärepositorioon (<etärepositorio>). |
| git push --all | Vie kaikki paikalliset haarat etärepositorioon. |
| git push -u <etärepoistorio> <paikallinen_haara> | Vie paikallisen haaran tiedot etärepositorioon ja asettaa vietävän paikallisen haaran oletusarvoiseksi etärepositorion haaraksi. |