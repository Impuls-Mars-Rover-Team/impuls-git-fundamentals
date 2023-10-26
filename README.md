# hello_impuls
<h2>Klonowanie repozytorium</h2>

<p>
  
  Aby sklonować repozytorium, odpalamy folder doktórego chcemy pobrać jego zawartość w terminalu i uruchamiamy komendę:  
  `git clone link-do-repozytorium`  
  Przykładowo, aby sklonować to konkretne repozytorium, podajemy komendę:  
  `git clone https://github.com/ImpulsMarsRover/hello_impuls.git`
</p>


<h2>Wprowadzanie zmian w repozytorium</h2>
<p>

  Aby wybrać pliki, które mają zostać uwzględnione w commicie (konkretnym zapisie w historii zmian) używamy commendy `add`.  
  `add nazwa-pliku` dodaje konkretny plik  
  `add *` dodaje wszystkie zmienione pliki
</p>

<p>

  Aby utworzyć commit, po dodaniu plików komendą `add`, używamy komendy:  
  `git commit -m wiadomosc-opisujaca-wprowadzone-zmiany`
  Podając informację opisującą zmiany, które wprowadziliśmy
</p>

<h2>Wrzucanie commitów na github</h2>
<p>
  
  Aby wrzucić wprowadzone przez nas zmiany na githuba, używamy komendy `git push`.  
  `git push` - wrzuca commit z domyślnymi ustawieniami (domyślny branch / "rozgałęzienie")
  Komendę git push można dodatkowo rozszerzyć o parametry określające serwer na ktory mają zostać wrzucone dane oraz branch do ktorego mają trafić. Przykładowo domyślnie komenda `git push` w przypadku tego repozytorium zadziała następujaco:  
  `git push https://github.com/ImpulsMarsRover/hello_impuls.git master`, wrzucając zmiany na ten serwer, do branchu o nazwie master.
  
</p>

<h2>Rozgałęzianie projektu - branch</h2>
<p>
  W systemie kontroli wersji GIT można rozgłąziać projekt, tak aby ułatwić pracę nad dodawaniem nowych funkcjonalności itp. W ten sposób, początkowo zmiany wprowadzane są tylko w rozgałęzieniu i w razie awarii projektu można jeszcze łatwiej wrócić do stanu sprzed awarii.
</p>
<p>

  Aby utworzyć nowy branch / rozgałęzienie można skorzystać z komendy:  
  `git checkout -b nazwa-nowego-rozgalezienia`  
  lub:  
  `git branch nazwa-nowego-rozgalezienia`
  
  przy czym warto korzystać z zasad clean code i podać znaczącą nazwę dla tekeigo rozgałęzienia - np. laser-zaglady jeśli nowy feature ma dodać laser zagłady do robota
</p>

<p>
  
  Aby przełączać między branchami, można wykorzystać komendę `git switch`:  
  `git switch nazwa-branchu-do ktorego-chcemy-przejsc`
</p>

<p>

  Aby wrzucić branch na githuba, należy przyjść do branchu który chcemy wrzucić oraz skorzystać z pełnej komendy git push:  
  `git push serwer-na-ktory-wrzucamy branch-do-ktorego-wrzucamy`, np żeby wrzucić lokalny branch new-branch-test:  
  `git push origin new-branch-test`.

  Origin to zdefiniowana nazwa serwera. Podczas klonowania zazwyczaj powstaje automatycznie jako "origin", jeśli tak się nie stanie możemy dodać ją komendą `remote add`:  
  `git remote add origin https://github.com/ImpulsMarsRover/hello_impuls.git` gdzie link jest linkiem do konkretnego np. repozytorium na githubie
</p>
