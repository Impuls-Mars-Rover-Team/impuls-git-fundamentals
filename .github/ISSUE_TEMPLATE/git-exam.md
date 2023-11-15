---
name: GIT exam
about: Assign a collaborator to take the GIT exam
title: "[GIT EXAM]"
labels: GIT exam
assignees: ''

---

<ol>
  <li>Załóż konto na GitHubie</li>
  <li>Zainstaluj GIT</li>
  <li>Otwórz w terminalu / CMD / Wierszu Polecenia / Powershellu / Bashu / Z-Shellu folder w którym chcesz umieścić folder z repozytorium</li>
  <li>Sklonuj to repozytorium</li>
    
    git clone https://github.com/ImpulsMarsRover/impuls-git-fundamentals.git
  <li>Utwórz nowy branch o nazwie będącej np Twoją nazwą użytkownika</li>

    git checkout -b "nazwa-nowego-branchu"
  <li>Zedytuj plik main.c, dodając w komentarzu w "Hello section" swoja nazwę użytkownika i powitanie: </li> 
    
    * @twojaNazwaUżytkownikaNaGitHubie: hello impuls

   <li>Dodaj wprowadzone zmiany do historii wersji:</li>

     git add .
    
  <li>Dodaj commit o nazwie "hello twojNazwaUżytkownika", podając swoją nazwę użytkownika na githubie:</li>
    
    git commit -m "hello twoja-nazwa-użytkownika"
  <li>Wrzuć commit na GitHuba do branchu o takiej samej nazwie jak Twojego lokalnego branchu</li>
  
    git push origin nazwa-twojego-lokalnego-branchu-z-punktu-5
  <li>Na GitHubie w zakładce Pull Requests utwórz nowy Pull Request aby scalić wprowadzone przez Ciebie zmiany z głównym branchem repozytorium</li>

  <li>Poczekaj na sprawdzenie i zatwierdzenie przez admininstratora zmian </li>
  <li>Dobra robota!</li>
  </ol>
