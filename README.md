
# Mapa dawnych nazw ulic Wrzeszcza i okolic (docelowo: calego Gdańska).

#### Pomysł: 
Mimo, że mieszkam we Wrzeszczu od dawna, czytając o jego historii nadal czasem gubię się w przedwojennych nazwach poszczególnych ulic. Dawne mapy, przytaczane w książkach, często różnią się od obecnego kształtu.<br>
"Przydałaby się jakaś interaktywna mapa z obiema nazwami na raz" - pomyślałam.<br>
A potem zdałam sobie sprawę, że przecież potrafię sama taką zrobić!

## 1. Źródła informacji:

#### Ślady ulic 
Plik ze śladami oraz nazwami ulic pobrałam z Geoportalu (link). Za pomocą QGISa zawędziłam dane do ulic wyłącznie na terenie Gdańska, a następnie eksportowałam całość do pliku geoJSON. Dzięki zachowaniu w pliku ulic z całego miasta będzie możliwa ewentualna późniejsza rozbudowa mapy o kolejne dzielnice.

#### Lista ulic Wrzeszcza, Strzyży i okolic
Wykorzystałam listę ulic dostępną na stronie <a href="https://czystemiasto.gdansk.pl/zdizgdanskfiles/image/gdansk_ulice_sektory_201307.pdf">czystemiasto.gdansk.pl</a> (tak, tej od wywozu śmieci 😄). Lista zawiera przyporządkowanie ulic do poszczególnych dzienic.

#### Lista historycznych nazw ulic Gdańska (i Sopotu)
Dostępna na stronie <a href="www.danzig-online.pl/page7.html">danzig-online.pl</a>.

## 2. Potęga Power Query
Dzięki temu, że w pliku pobranym z Geoportalu znajdują się zapisane nazwy poszczególnych ulic, do połączenia wszystkich powyższych źródeł wystarczył klasyczny inner join z opcją <i>fuzzy matching</i>... i dużo, dużo ręcznej roboty przy dopasowywaniu do siebie pozostałych nazw ulic:
- usuwanie duplikatów (gdy dana ulica przed 1945 rokiem miała więcej, niż jedną nazwę, pojawia się na liście wielokrotnie);
- łączenie nazw ulic, których Power Query nie skojarzył - głównie w przypadku różnic w pisowni.

## 3. Szczegóły dot. nazw ulic
To już własna, ręczna, żmudna praca. Opieram się głównie na: Gedanopedii, Wikipedii oraz książce <i>Dolny Wrzeszcz i Zaspa</i> autorstwa J. Daniluka i J. Wasilewskiego.

## 4. Mapa i dashboard w Tableau Public
Całość składa się z dwóch plików: wspomnianego wyżej geoJSONa ze śladami i nazwami ulic (z całego miasta), oraz arkusza Google z nazwami obecnymi, historycznymi oraz dodatkowymi informacjami. W chwili obecnej mapa filtruje jedynie ulice z Wrzeszcza, Strzyży, oraz kilka ulic z pogranicza dzielnic (np. ulica Hynka, należąca już do Zaspy).<br>
Taka strategia umożliwi mi bardzo proste, niewymagające wiekszych ingerencji w strukturę dashboardu rozbudowywanie mapy o dalsze informacje czy nawet kolejne dzielnice.

## 5. Dalsze plany
- naprawić błędy. Na przykład odkryć, dlaczego Aleja Żołnierzy Wyklętych nie wyświetla się wcale, a Hynka ma dziurę w środku 😄
- rozszerzyć mapę o kolejne dzielnice
- i o kolejne informacje na temat ulic, ich nazw i patronów
- edytować plik ze śladami ulic tak, aby te dłuższe podzielić na fragmenty odpowiadające poszczególnym dzielnicom.
