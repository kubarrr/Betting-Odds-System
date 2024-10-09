# Betting-Odds-System

<h4>Dane które zbieramy:</h4>
<ul>
  <li>Statystyki meczowe (zrobione dla PL 21-24)</li>
  <li>Dane stadionów (dodać wymiary boisk niektóych stadionów)</li>
  <li>Dane pogodowe (do zrobienia)</li>
  <li>Dane zawodników (do zrobienia)</li>
  <li>Dane tekstowe do analizy sentymentu (do zastanowienia)</li>
</ul>


Wstępny pomysł na sieć (Model 1 V1):
Input 1: Statystyki meczowe z poprzednich 5-10 meczów
Input 2: Agregacja statystyk meczowych z ostatnich 30-50 meczów
Input 3: Motywacja/zmęczenie drużyny: ilość dni od ostatniego meczu, waga meczu, ilość dni do kolejnego kluczowego meczu, itp.
Input 4: Dane pogodowe/stadionowe z odpowiednim embeddingiem
Input 5: Sentyment z mediów, opcjonalnie przepuszczony przez LTSM
Input 6: Dane dotyczące zawodników -> Dodatkowy model do tego lub jakaś miara wpływu nieobecnych zawodników względem obecnych

- 6 inputów przepuszczamy przez Dense layers (niektóe ewnetualnie przez LTSM, ale nie wiem jeszcze jak to dokłądnie działa xd)
- Łączymy dane za pomocą concatenate
- Kilka dense layers z coraz mniejszą ilością neuronów
- Na koniec Softmax layer z 3 wyjściami odpowiadającymi prawdopodobieństwu wygranej gospodarzy/remisu/wygranej gości


