<h1>GIT & Github quickstart</h1>

![In case of fire: 1) git commit 2) git push 3) leave building](/instructions.jpg)

<h2>Zadanie do wykonania:</h2>
  <p>
  
  <ol>
  <li>Załóż konto na GitHubie</li>
  <li>Zainstaluj GIT</li>
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
  
    git push origin nazwa-twojego-lokalnego-branchu-z-punktu-4
  <li>Na GitHubie w zakładce Pull Requests utwórz nowy Pull Request aby scalić wprowadzone przez Ciebie zmiany z głównym branchem repozytorium</li>
  </ol>
  </p>



<h2>Git</h2>

<p>

  Link do pobrania gita: https://git-scm.com/downloads
</p>

<h3>Klonowanie repozytorium</h3>

<p>
  
  Aby sklonować repozytorium, odpalamy folder do którego chcemy pobrać jego zawartość w terminalu i uruchamiamy komendę:  
```
git clone link-do-repozytorium  
```  
  Przykładowo, aby sklonować to konkretne repozytorium, podajemy komendę:  
  ```
  git clone https://github.com/ImpulsMarsRover/impuls-git-fundamentals
```
</p>


<h3>Wprowadzanie zmian w repozytorium</h3>
<p>

  Aby wybrać pliki, które mają zostać uwzględnione w commicie (konkretnym zapisie w historii zmian) używamy komendy `add`.  
  `git add nazwa-pliku` dodaje konkretny plik  
  `git add *` dodaje wszystkie zmienione pliki, 

</p>

<p>

  Aby utworzyć commit, po dodaniu plików komendą `add`, używamy komendy:  
  `git commit -m "wiadomosc-opisujaca-wprowadzone-zmiany"`
  Podając informację opisującą zmiany, które wprowadziliśmy. Proces commitowania może wyglądać tak:


```
git status
git add *
git commit -m "dodane-jakies-zmiany"
git log
```
Komenda `git status` zwraca aktualny stan repozytorium - zmiany w plikach oraz czy te zmiany są uwzględnione w przygotowywanym commicie. `qit log` wyswietla historię zmian lokalnego repozytorium.
</p>

<h3>Wrzucanie commitów na github</h3>
<p>
  
  Aby wrzucić wprowadzone przez nas zmiany na githuba, używamy komendy `git push`.  
  `git push` - wrzuca commit z domyślnymi ustawieniami (domyślny branch / "rozgałęzienie")
  Komendę git push można dodatkowo rozszerzyć o parametry określające serwer na ktory mają zostać wrzucone dane oraz branch do ktorego mają trafić. Przykładowo domyślnie komenda `git push` w przypadku tego repozytorium zadziała następujaco:  
  `git push https://github.com/ImpulsMarsRover/hello_impuls.git master`, wrzucając zmiany na ten serwer, do branchu o nazwie master.
  
</p>

<h3>Rozgałęzianie projektu - branch</h3>
<p>
  W systemie kontroli wersji GIT można rozgłąziać projekt, tak aby ułatwić pracę nad dodawaniem nowych funkcjonalności itp. W ten sposób, początkowo zmiany wprowadzane są tylko w rozgałęzieniu i w razie awarii projektu można jeszcze łatwiej wrócić do stanu sprzed awarii.
</p>
<p>

  Aby utworzyć nowy branch / rozgałęzienie można skorzystać z komendy:  
  `git checkout -b nazwa-nowego-rozgalezienia`  
  lub:  
  `git branch nazwa-nowego-rozgalezienia`
  
  przy czym warto korzystać z zasad clean code i podać znaczącą nazwę dla tekeigo rozgałęzienia - np. laser-zaglady jeśli nowy feature ma dodać laser zagłady do robota.

  Komenda `git branch` bez argumentów zwraca branche obecne w lokalnym repozytorium.  
</p>

<p>
  
  Aby przełączać między branchami, można wykorzystać komendę `git switch`:  
  `git switch nazwa-branchu-do ktorego-chcemy-przejsc`
</p>

<p>

  Aby wrzucić branch na githuba, należy przyjść do branchu który chcemy wrzucić oraz skorzystać z pełnej komendy git push:  
  `git push serwer-na-ktory-wrzucamy branch-do-ktorego-wrzucamy`, np żeby wrzucić lokalny branch new-branch-test:  
  ```
  git push origin new-branch-test
```
Można uniknąć podawania argumentów, ustawiając "upstream" dodajac parametr `-u` wrzucając pierwszy commit na serwer.  
***UWAGA*** - po przejsciu do innego branchu, chcąc wrzucić na serwer lokalne zmiany trzeba zdefiniować upstream na aktualny branch albo za każdym razem podawać nazwę branchu na serwerze do którego mają trafić zmiany
```
git push -u http://www.github.com/konto-uzytkownika/repozytorium-uzytkownika branch-do-ktorego-wrzucamy
```
Adres serwera mozna również zastąpić zdefiniowana nazwą, np. origin jak powyżej.
Origin to zdefiniowana nazwa serwera. Podczas klonowania zazwyczaj powstaje automatycznie jako "origin", jeśli tak się nie stanie możemy dodać ją komendą `remote add`:  
  `git remote add origin https://github.com/ImpulsMarsRover/hello_impuls.git` gdzie link jest linkiem do konkretnego np. repozytorium na githubie

  Aby połączyć główny branch z nowym rozgłązieniem (praca nad nowymfeature skończona itp), należy przejść do branchu do którego chcemy wprowadzić zmianny np. komendą git switch oraz użyć komendy merge, podając nazwę branchu,z którego chcemy zaimportować zmiany

```
git branch
git switch master
git merge new-feature
```

</p>

<h3>Pobieranie zmian zapisanych na serwerze</h3>

<p>

  Aby pobrać zmiany zapisane na serwerze - przez nas samych jeśli coś nie wyszło albo przez kogoś innego żeby uniknąć problemów, odpalamy komendę:  
  ```
  git pull
```
</p>


<h2>Github - tricki</h2>

<h3>Projects</h3>

<p>
  Na githubie możemy utworzyć "projekt", gdzie można utworzyć przyjemną w obsłudze listę rzeczy do zrobienia w projekcie.
  Jeśli nad projektem pracuje kilka osób, można im przydzielać zadania z poziomu githubowego projektu.
  Zadania na liście to do mogą być zautomatyzowane - np. na podstawie Issues (nowy issue - nowy wpis na to do, zamknięty issue - odhaczenie na liście to do).
  Więcej informacji: https://docs.github.com/en/issues/planning-and-tracking-with-projects  
</p>

<h3>Issues</h3>

<p>

  Issues to miejsce,w którym można zgłaszać problemy z działaniem programu, bugi lub automatyzować rozwój projektu.
</p>

<h3>Releases</h3>

<p>

  Po zakończeniu pracy nad programem można utworzyć release.  
  Przykładowo jeśli zachodzą jakieś ważne zmiany, możemy wtedy rozróżnić projekt np. na wersję 1.0 i 2.0, gdzie:

  <ul>
    <li>1.0 byłaby wersją np. na płytkę PCB zaprojektowaną w 2021 roku</li>
    <li>2.0 byłaby wersją np. na płytkę PCB zaprojektowaną w 2023 roku</li>
  </ul>

  Do release można wrzucić np. finalny kod źródłowy aktualny dla tych etapów, pliki binarne (np. .hex dla mikrokontrolerów, .exe itp dla PC), dokumentacje dotyczące konkretnych wersji, instalatory oraz narzędzia służące do stworzenia tej wersji (np. instalator IDE w starszej wersji obsługującej starszy kompilator)
</p>
