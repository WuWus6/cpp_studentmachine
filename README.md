Opis ogólny:
Poniższy kod napisanego w C++ wykorzystuje bibliotekę Google Test (gtest) do porównania wydajności instrukcji warunkowych if-else oraz switch w scenariuszu testowym. Program mierzy czas wykonania funkcji z if-else oraz switch dla tej samej liczby iteracji, a następnie sprawdza, czy suma wyników obu operacji jest równa. Czas wykonania jest mierzony za pomocą biblioteki chrono w mikrosekundach.

Opis funkcji:
Funkcja compareIf(int value)

Funkcja przyjmuje liczbę całkowitą value jako argument i na podstawie instrukcji if-else zwraca odpowiednią wartość:
10 dla value == 1
20 dla value == 2
30 dla value == 3
40 dla wszystkich innych wartości
Zastosowanie: Ta funkcja symuluje działanie zagnieżdżonych instrukcji warunkowych if-else.
Funkcja compareSwitch(int value)

Funkcja przyjmuje liczbę całkowitą value jako argument i na podstawie instrukcji switch zwraca odpowiednią wartość:
10 dla value == 1
20 dla value == 2
30 dla value == 3
40 dla wszystkich innych wartości
Zastosowanie: Ta funkcja jest odpowiednikiem funkcji compareIf, ale używa konstrukcji switch zamiast if-else.
Opis testu wydajnościowego:
Test BenchmarkTest, IfElseBenchmark
Ten test wykorzystuje pętle, aby wykonać oba podejścia (if-else oraz switch) dla tej samej liczby iteracji (w tym przypadku 10,000).

Pomiar czasu:

Czas wykonania funkcji compareIf oraz compareSwitch jest mierzony przy pomocy funkcji z biblioteki chrono.
Czas wykonywania operacji jest zapisywany w mikrosekundach i wyświetlany na ekranie.
Struktura testu:

Pomiar czasu dla if-else:
Funkcja compareIf jest wykonywana w pętli 10,000 razy z wartościami od 0 do 3 (dzięki i % 4), co pozwala symulować różne przypadki.
Pomiar czasu dla switch:
Funkcja compareSwitch jest wykonywana w analogiczny sposób dla tych samych wartości.
Porównanie wyników:
Test sprawdza, czy suma wyników z obydwu funkcji jest identyczna, używając makra ASSERT_EQ. Jeśli suma wyników z if-else oraz switch różni się, test zakończy się niepowodzeniem.
Wyświetlanie wyników:

Po zakończeniu testów, program wyświetla czas wykonania każdej operacji (w mikrosekundach) na ekranie.
Szczegóły dotyczące głównej funkcji main:
Funkcja main inicjalizuje framework Google Test i uruchamia wszystkie testy za pomocą RUN_ALL_TESTS().
Argumenty przekazane do funkcji main umożliwiają skonfigurowanie i uruchomienie testów w standardowy sposób dla frameworka Google Test.
Przykład działania:
Program wywołuje test, który wykonuje 10,000 iteracji dla obu funkcji (compareIf i compareSwitch).
Program mierzy czas wykonania każdej z funkcji i wyświetla wynik w mikrosekundach.
Na koniec test sprawdza, czy wyniki obliczeń obu funkcji są takie same. Jeśli tak, test kończy się sukcesem.
Przykładowy wynik działania programu może wyglądać następująco:

sql
Skopiuj kod
Czas wykonania instrukcji if-else: 1200 mikrosekund
Czas wykonania instrukcji switch: 1000 mikrosekund
[==========] Running 1 test from 1 test suite.
[----------] Global test environment set-up.
[----------] 1 test from BenchmarkTest
[ RUN      ] BenchmarkTest.IfElseBenchmark
[       OK ] BenchmarkTest.IfElseBenchmark (2 ms)
[----------] 1 test from BenchmarkTest (2 ms total)
[----------] Global test environment tear-down
[==========] 1 test from 1 test suite ran. (2 ms total)
[  PASSED  ] 1 test.
Zastosowanie:
Kod demonstruje różnice w wydajności pomiędzy if-else i switch przy prostych operacjach i niewielkiej liczbie przypadków.
Może być stosowany do nauki technik optymalizacji kodu, testowania wydajności lub w sytuacjach, gdzie ważna jest decyzja, która z tych konstrukcji jest szybsza.






