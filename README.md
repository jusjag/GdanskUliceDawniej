
# Mapa dawnych nazw ulic Wrzeszcza i okolic (docelowo: calego Gdańska).

#### Pomysł: 
Mimo, że mieszkam we Wrzeszczu od dawna, czytając o jego historii nadal czasem gubię się w przedwojennych nazwach poszczególnych ulic. Dawne mapy, przytaczane w książkach, często różnią się od obecnego kształtu.<br>
"Przydałaby się jakaś interaktywna mapa z obiema nazwami na raz" - pomyślałam.<br>
A potem zdałam sobie sprawę, że przecież potrafię sama taką zrobić!

## 1. Źródła informacji:

#### Ślady ulic 
Plik ze śladami oraz nazwami ulic pobrałam z Geoportalu. Za pomocą QGISa zawędziłam dane do ulic wyłącznie na terenie Gdańska, a następnie eksportowałam całość do pliku geoJSON. Dzięki zachowaniu w pliku ulic z całego miasta będzie możliwa ewentualna późniejsza rozbudowa mapy o kolejne dzielnice. Osobno eksportowałam plik CSV z listą nazw ulic, aby połączyć obecne nazwy z historycznymi.

#### Lista ulic Wrzeszcza, Strzyży i okolic
Wykorzystałam listę ulic dostępną na stronie <a href="https://czystemiasto.gdansk.pl/zdizgdanskfiles/image/gdansk_ulice_sektory_201307.pdf">czystemiasto.gdansk.pl</a> (tak, to ta od wywozu śmieci 😄). Lista zawiera listę ulic oraz dzielnic, do których należą.

#### Lista historycznych nazw ulic Gdańska (i Sopotu)
Dostępna na stronie <a href="www.danzig-online.pl/page7.html">danzig-online.pl</a>.

## 2. Potęga Power Query
Plik z Geoportalu ma pełne nazwy ulic (Np. Mikołaja Reja), plik z nazwami historycznymi głównie nazwy skrócone (Reja), do połączenia obu wykorzystałam plik od Czyste Miasto Gdańsk, który ma podane obie wersje. Do połączenia tego w całość wystarczyły dwa proste joiny... i dużo, dużo ręcznej roboty przy dopasowywaniu wierszy:
- usuwanie duplikatów (gdy dana ulica miała więcej niż jedną nazwę, pojawia się na liście wielokrotnie);
- łączenie nazw ulic, których Power Query nie skojarzył - głównie w przypadku różnic w pisowni.

## 3. Szczegóły dot. nazw ulic
Praca własna. Opieram się głównie na: Gedanopedii, Wikipedii oraz książce <i>Dolny Wrzeszcz i Zaspa</i> autorstwa J. Daniluka i J. Wasilewskiego, a także archiwum nieistniejącej już Akademii Rzygaczy.

## 4. Mapa i dashboard w Tableau Public
Całość składa się z dwóch plików: wspomnianego wyżej geoJSONa ze śladami i nazwami ulic (z całego miasta), oraz arkusza Google z nazwami obecnymi, historycznymi oraz dodatkowymi informacjami. W chwili obecnej mapa filtruje jedynie ulice z Wrzeszcza, Strzyży, oraz kilka ulic z pogranicza dzielnic (np. ulica Hynka, należąca już do Zaspy).<br>

## 5. Dalsze plany
- naprawić błędy. Na przykład odkryć, dlaczego Aleja Żołnierzy Wyklętych nie wyświetla się wcale, a Hynka ma dziurę w środku 😄
- rozszerzyć mapę o kolejne dzielnice, a może nawet całe miasto?
- i o kolejne informacje na temat ulic, ich nazw i patronów
- nauczyć się edytować plik ze śladami ulic tak, aby te dłuższe podzielić na fragmenty odpowiadające poszczególnym dzielnicom.
<br>
Dziękuję za uwagę 😊
