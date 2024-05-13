
# Sigma Drive

## 1. Opis Gry
Sigma Drive to gra stworzona na konkurs "invent your game 2024", inspirowana "ryan gosling drive meme". Jest to nieskończona pierwszoosobowa gra wyścigowa, polegająca na kierowaniu samochodem na prostej drodze. Celem w grze jest bycie sigmą, zdobywanie wyniku za niebezpieczną jazdę, oraz zdobywanie pieniędzy i ulepszanie samochodu. Powodzenia na drodze.


## 2. Instrukcja Kompilacji
- Otwórz (lub zainstaluj) Unity Hub
- W prawym górnym rogu kliknij "Add" i wybierz folder "Sigma Drive Project"
- Zainstaluj Unity 2022.3.17f1 jeśli nie jest zainstalowane
- Otwórz "Sigma Drive Project"
- Po uruchomieniu edytora projektu przejdź do File->Build Settings
- W "Build Settings" w prawym dolnym rogu kliknij "Build" lub "Build And Run"
- Wybierz folder w którym będzie znajdowała się skompilowana gra
- Po zakończeniu kompilacji uruchom grę jeśli nie uruchomiła się automatycznie


## 3. Instrukcja Uruchomienia
- W folderze "Sigma Drive" znajduje się skompilowana wersja gry
- Aby uruchomić grę należy otworzyć plik "Sigma Drive.exe"


## 4. Poradnik
### a. Sterowanie
W Sigma Drive można grać za pomocą klawiatury i myszki lub kontrolera

Klawiatura:
- Użyj myszki, WSAD lub strzałek aby nawigować menu
- Wciśnij lmb lub enter aby wybrać
- Wciśnij esc aby wyjść
- Użyj W / S albo ArrowUp / ArrowDown aby przyśpieszać / hamować
- Użyj A / D albo ArrowLeft / ArrowRight aby sterować samochodem
- Wciśnij Spację aby spauzować

Kontroler:
- Użyj lewej gałki aby nawigować menu
- Wciśnij dolny przycisk aby wybrać
- Wciśnij prawy przycisk aby wyjść
- Użyj Spustów Kontrolera aby przyśpieszać / hamować
- Użyj Lewej Gałki to aby sterować samochodem
- Wciśnij Przycisk Start aby spauzować

### b. Interfejs
Menu:
- W menu możesz przejść do ustawień gdzie możesz zmienić głośność gry lub muzyki, zmienić język (aktualnie angielski i polski), oraz ponownie zobaczyc poradnik
- W lewym górnym rogu jest wyświetlany Najlepszy Wynik
- Na prawo od Najlepszego Wyniku jest są wyświetlane twoje pieniądze, które zdobywa się podczas grania i można je wykorzystać do zakupu ulepszeń samochodu
- Ulepszenia samochodu to Moc, Sterowność, Hamowanie i Wytrzymałość, mają one poziomy 1-12 i można wybrać dowolny zakupiony poziom
- W menu można wybrać porę dnia (dzień/noc) oraz poziom trudności (łatwy - ruch jednostronny, średni - ruch dwustronny, trudny - ruch jednostronny w przeciwnym kierunku)

Gra:
- W lewym górnym rogu jest wyświetlana Wytrzymałość, postaraj się utrzymać ją powyżej 0. Wytzymałość można stracić uderzając w samochody lub inne obiekty.
- Po środku na prawo od wytrzymałości Wyświetlany jest Wynik. Wynik można zdobywa się za dystans i niebezpieczną jazdę np. bliskie wyprzedzenie lub zniszczenie obiektu.
- Na prawo od Wyniku jest Mnożnik Wyniku. Można go zwiększyć jeśli jedziesz powyżej 70kmh, poprzez niebezpieczną jazdę, szybką jazdę oraz jazdę po złej stronie ulicy
- Na prawo od mnożnika wyświetlane są informacje np. o zniszczeniu obiektu
- W prawym dolnym rogu jest wyświetlana prędkość i bieg, znajduje się też tam przycisk pauzy

### c. Porady
- Pamientaj, bądź sigmą
- Im szybciej jedziesz, tym większy jest mnożnik wyniku
- Jeżeli jedziesz poniżej 70kmh twój mnożnik się resetuje
- Mnożnik zwiększa się x2 gdy jedziesz złą stroną ulicy
- Wynik i Mnożnik Można też zwiększyć bliskimi wyprzedzeniami, zarysowaniem i niszczeniem aut, niszczeniem przeszkód a także przejeżdżaniem przez przejścia, czerwone światła oraz dziury w drodze
- Jadąc można zebrać ulepszenia: (zwiększenie mnożnika, zwiększenie przędkości, naprawa)
- Możesz wjechać na chodnik oraz jechać do tyłu (nie, nie da się wypaść za mapę cofając, nie próbuj)
- Nie zniszcz swojego samochodu (opcjonalne)
- wszystkie dane gry są zapisywane w gameData.json, możesz je zmieniaćna własną odpowiedzialność


## 5. Szczegóły
### a. Sterowanie Samochodem Gracza
- Samochód gracza porusza się na osi Z (przód) i X (bok), oraz nie może się obracać
- Maksymalna prędkość jaką można osiągnąć to ok. 360kmh
- Samochód posiada 6 biegów które są automatycznie dopasowywane do mocy
- bieg 6 jest używany jedynie po zebraniu zwiększenia prędkości
- po zmianie biegu samochód jest na biegu neutralnym przes 0.3s, po 0.8s może znowu zmienić bieg
- prędkość cofania to ok. 25kmh
- Gdy wytrzymałość spadnie do 0 przez 0.5s możesz wciąż sterować samochodem, po 2s pojawia się Game Over
- Jeśli w 2s po straceniu wytrzymałości zbierzesz naprawę to możesz wciąż jechać

### b. Ulepszenia
- Cena ulepszeń to 1000 * 1.5^n gdzie n to poziom ulepszenia - 2
- Moc ma bazową wartość 102 i z każdym ulepszeniem zwiększa się o 10. Moc zwiększa maksymalną prędkość i przyśpieszenie.
- Sterowność ma bazową wartość 7 i z każdym ulepszeniem zwiększa się o 0.5. Sterowność zwiększa przyśpieszenie sterowania i maksymalną prędkość sterowania.
- Hamowanie ma bazową wartość 50 i z każdym ulepszeniem zwiększa się o 20. Zwiększa moc hamowania.
- Wytrzymałość ma bazową wartość 100 i z każdym ulepszeniem zwiększa się o 20. Zwiększa ilość punktów wytrzymałości

### c. Przeszkody i Wytrzymałość
- Dla uderzenia z przodu damage to różnica prędkości X + różnica prędkości Z
- Dla uderzenia z boku damage to różnica prędkości X + (różnica prędkości X * 0.1)
- Przeszkody mają Mnożnik damagea oraz max szkodę gdzie max damage jest sprawdzana przed pomnożeniem przez mnożnik
- Minimalna damage dla samochodu gracza to 2
- damage wyrządzona dla gracza to (damage||max damage) * mnożnink - 2
- Przeszkody mają minimalną szkodę do zniszczenia, jeśli damage jest mniejsza, przedamage nie zostanie zniszczona, a damage zostanie odjęta od damage do zniszczenia
Wszystkie przeszkody:

| Nazwa         | Mnożnik       | Max damage    | Damage do zn  |  
| ------------- |:-------------:|:-------------:|:-------------:|
| BarrierLight  | 0.5           | 60            | 3             |
| BarrierHeavy  | 2             | 100           | 20            |
| Bollard       | 0.5           | 40            | 3             |
| Cone          | 0.5           | 30            | 1             |
| Tire          | 0.5           | 30            | 1             |
| Bench         | 0.5           | 50            | 5             |
| TrashCan      | 0.5           | 40            | 5             |
| Sign          | 0.5           | 50            | 4             |
| Lantern       | 2             | 100           | 15            |
| TrafficLight  | 2             | 100           | 15            |

- Są też 3 specjalne przeszkody
    - Dziura - im szybciej przez nią przejedziesz, tym mniej zadaje damagea
    - Przejście - nie zadaje damagea, po przejechaniu powyżej 70kmh daje punkty
    - Światła - nie zadaje damagea, po przejechaniu na czejownym daje punkty (W przejściu ze światłami zaliczają się jedynie światła)

W grze są 3 grupy przeszkód:
- Przeszkody drogowe np. barierki - na każdym poziomie (poziom to ok. 200M) 1 losowa przeszkoda jest spawnowana na losowej pozycji. Lista Przeszkód:
    - 2 Bollards
    - 2 Tire Stacks
    - 3 Cones
    - 4 Bollards
    - Light Barrier
    - Heavy Barrier
    - Cones with Hole
    - Light Barrier with Hole
    - Heavy Barrier with Hole
    - Hole
- Przeszkody chodnika np. lampy - na każdym poziomie są spawnowane losowe przeszkody chodnika po obu stronach. Lista Przeszkód:
    - Nothing
    - Lanterns
    - Benches
    - Signs
    - Lanterns + Benches
    - Lanterns + Signs
- Przeszkody poziomu np. Przejście - na każdym poziomie jest 20% szansy na zespawnowanie losowej przeszkody poziomu. Lista Przeszkód:
    - Crossing
    - Traffic Lights
    - Traffic Lights with Crossing

### d. Samochody
- Jest 9 różnych samochodów, w tym:
    - 6 samochodów
    - 2 busy
    - 1 van
- Na każdym poziomie są spawnowane losowe samochody po równo po obu stronach na losowych pozycjach
- Bazowa ilość samochodów to 2, co 8 poziomów liczba jest zwiększana o 2 aż do 10
- Wszystkie samochody mają inną bazową prędkość (ok. 1), przy spawnowaniu jest ona zmieniana o -0.2 do 0.5
- samochody mogą zmieniać pas losowo (2% co 1-2s ) lub w specjalnych przypadkach
- samochód zmienia pas na losowy gdy obie strony jadą w tą samą stronę, jeśli nie, zmienia pas na drugi z jego strony
- Jeśli przed samochodem znajduje się inny samochód, samochód zwolni do prędkości innego i spróbuje zmienić pas co 2-6s (nie zmieni pasa jeśli jest zablokowany)
- Jeśli przed samochodem znajduje się przejścię, samochód zwolni o połowę
- Jeśli przed samochodem znajdują się światła, samochód zachamuje jeśli światło jest czerowne
- Jeśli przed samochodem znajduje się gracz, samochód zachamuje i spróbuje zmienić pas co 2-6s
- Jeśli przed samochodem znajduje się przeszkoda, samochód zachamuje i spróbuje zmienić pas co 0.1s
- Jeśli samochód uderzy w przeszkodę, zniknie
- Jeśli samochód uderzy w inny samochód, zniknie zniszczony samochód, jeśli żaden nie jest zniszczony, znikną oba

- Damage jest kalkulowany tak samo jak w przypadku przeszkód, ale samochody nie mają max damage
- Jeśli damage jest mniejszy od damage do zniszczenia, samochód zostanie zarysowany a damage zostanie odjęty od damage do zniszczenia
- jeśli damage jest wystarczający, samochód zostanie zniszczony, przestanie jechać i zniknie w 3s

| Typ           | Mnożnik       | Damage do zn  |  
| ------------- |:-------------:|:-------------:|
| samochód      | 1.5           | 15            |
| van           | 2             | 22            |
| bus           | 2.5           | 30            |

### e. Ulepszenia do zebrania
- W grze są 3 ulepszenia do zebrania
- Na każdym poziomie jest 40% na spawn ulepszenia do zebrania
- Zwiększenie Prędkości zwiększa moc o 20% przez 10s
- Zwiększenie Mnożnika zwiększa mnożnik o x1
- Naprawa dodaje 20% punktów wytrzymałości

### f. Wynik i Mnożnik
- Każdy zdobyty wynik jest mnożony przed mnożnik
- Wynik można zdobywać za dystans, co 0.1s
- Cofając się i wracając nie zdobędziesz wyniku za dystans

- Mnożnik wyniku to bazowy mnożnik * mnożnik za prędkość * mnożnik za złą stronę
- Gdy jedziesz złą stroną mnożnik wyniku jest mnożony x2
- Mnożniki za prędkość to:
    - 100 - x2
    - 200 - x3
    - 300 - x4
- bazowy mnożnik można zwiększać przez niebezpieczną jazdę
- bazowy mnożnik ma min wartość x1 i max wartość x10
- bazowy mnożnik jest zmniejszany co 2s:
    - większy od x7, -0.4
    - większy od x5, -0.3
    - większy od x3, -0.2
    - mniejszy od x3, -0.1

Wynik i Mnożnik można zdobywać za niebezpieczną jazdę:

| Nazwa                              | Wynik         | +Mnożnik      |  
|:----------------------------------:|:-------------:|:-------------:|
| Zniszczenie busa                   | 350           | 1.4           |
| Zniszczenie vana                   | 250           | 1             |
| Zniszczenie samochodu              | 200           | 0.8           |
| Zarysowanie samochodu              | 50            | 0.2           |
| Bliskie wyprzedzenie               | 50            | 0.2           |
| Zniszczenie BarrierHeavy           | 250           | 1             |
| Zniszczenie Lantern, TrafficLight  | 125           | 0.5           |
| Zniszczenie Lantern, TrafficLight  | 125           | 0.5           |
| Zniszczenie Bench, TrashCan, Sign  | 75            | 0.3           |
| Zniszczenie BarrierLight           | 75            | 0.3           |
| Zniszczenie Bollard                | 50            | 0.2           |
| Zniszczenie Cone, Tire             | 25            | 0.1           |
| Przejechanie Na czerwonym          | 250           | 0.5           |
| Przejechanie Przez przejście       | 100           | 0.2           |
| Przejechanie Przez Dziurę          | 50            | 0.2           |






