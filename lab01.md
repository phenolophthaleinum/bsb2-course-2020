# Linux - podstawy obsługi

> Zadania powinny zostać wykonane w terminalu przy pomocy poleceń powłoki.
Do każdego z poniższych punktów należy podać polecenie Linuxa, które umożliwiło rozwiązania zadania.


## Zad. 1 (Poruszanie się w drzewie katalogów)

1. Otwórz terminal. Podaj pełną ścieżkę katalogu domowego, w którym się znajdujesz.
2. Wyświetl listę wszystkich plików i katalogów znajdujących się w bieżącym katalogu.
3. Przejdź do katalogu `Desktop`.
4. Wróć do poprzedniego katalogu.
5. Przejdź do korzenia systemu plików (ścieżka `/`).
6. Wyświetl listę wszystkich plików i katalogów znajdujących się w tej ścieżce.
7. Jednym poleceniem przejdź do katalogu domowego.
8. Wpisz polecenia `ls -l`. Co określa parametr `-l`?
9. Na podstawie dokumentacji polecenia ls (`man ls`) wyjaśnij, co robi polecenie `ls -alpth`.
10. Co otrzymasz w wyniku polecenia `ls /var/`?

## Zad. 2 (Obsługa wiersza poleceń) [nie wymaga odpowiedzi]

1. Wpisz `cd D` i nie naciskaj klawisza Enter. Naciśnij dwa razy klawisz `Tab`.
2. Wpisz `cd De` i naciśnij klawisz `Tab`.
2. Naciśnij kilka razy klawisz strzałki do góry. Następnie naciśnij klawisz strzałki w dół.
3. Wpisz polecenie `history`.
4. Zaznacz myszką jedno z ostatnich poleceń (np. `ls -alpth`).
   * Skopiuj polecenie używając klawiszy `Ctrl + Shift + C`.
   * Wklej polecenie używając klawiszy `Ctrl + Shift + V` lub używając środkowego przycisku myszy.
5. Wpisz polecenie `clear`.
6. Naciśnij klawisz `Ctrl`+`r` i wpisz `alp` w celu znalezienia użytego wcześniej polecenia `ls -alpth`.
7. Wpisz polecenie `ls -alpth` i nie naciskaj klawisza Enter. Sprawdź skróty klawiszowe `Ctrl`+`a` i `Ctrl`+`e`.


## Zad. 3 (Tworzenie katalogów i plików)

1. Przejdź do katalogu `Desktop` i utwórz w nim katalog `lab01`.
2. Przejdź do katalogu `lab01` i utwórz w nim katalog `text`.
3. Przejdź do katalogu `text` i utwórz w nim pusty plik `README.txt`.

```
lab01/
└── text/
    └── README.txt
```

4. Otwórz plik `README.txt` w edytorze tekstu `nano`.
   * W treści pliku wpisz `hello`. 
   * Zapisz zmiany w pliku.
   * Zakończ pracę z edytorem tekstu.
5. Korzystając z polecenia `cat` wyświetl zawartość pliku `README.txt`.
6. Przejdź do katalogu `lab01` i z tej ścieżki wyświetl zawartość pliku `README.txt`.


## Zad. 4 (Kopiowanie, przenoszenie, usuwanie katalogów i plików)

1. Co otrzymasz w wyniku polecenia `cp text/README.txt ./`?
2. Co otrzymasz w wyniku polecenia `cp text/README.txt ./readme.txt`?
3. Usuń plik `readme.txt`.
4. Zmień nazwę pliku `README.txt` na `README.md` w katalogu `lab01`.
5. Utwórz kopię katalogu `text` nazywając go `text_backup`.
6. Usuń katalog `text`.
7. Przenieś plik `README.md` do katalogu `text_backup`.

```
lab01/
└── text_backup/
    ├── README.md
    └── README.txt
```

## Zad. 5 (Kompresja i dekompresja plików/katalogów, Pobieranie plików z internetu)

1. Spakuj katalog `text_backup` poleceniem `tar -zcvf text_backup.tar.gz text_backup`.
   * Korzystając z dokumentacji, wyjaśnij, za co odpowiadają użyte przełączniki `-z`, `-c`, `-v`, `-f`.
2. Korzystając z polecenia `wget` pobierz skompresowane archiwum znajdujące się pod adresem `http://www.combio.pl/files/sequences10.tar.gz`.
3. Rozpakuj pobrany plik poleceniem `tar -zxvf sequences10.tar.gz`. Co otrzymałeś/aś?
4. Usuń skompresowane archium `sequences10.tar.gz`.
4. Wyświetl na ekran zawartość pliku `seq01.fasta`.
5. Jednym poleceniem wyświetl na ekran zawartosć pliku `seq01.fasta` i `seq02.fasta`.
6. Jednym poleceniem wyświetl na ekran zawartość wszystkich rozpakowanych plików.

```
lab01/
├── seq01.fasta
├── seq02.fasta
├── seq03.fasta
├── seq04.fasta
├── seq05.fasta
├── seq06.fasta
├── seq07.fasta
├── seq08.fasta
├── seq09.fasta
├── seq10.fasta
├── text_backup/
│   ├── README.md
│   └── README.txt
└── text_backup.tar.gz
```

## Zad. 6 (Przekierowanie)

1. Przekieruj zawartość 10 plików z sekwencjami do jednego pliku `all.fasta`.
2. Jednym poleceniem usuń wszystkie 10 plików `seq01-seq10.fasta`.
3. Sprawdź wynik działania poniższych komend i odpowiedz co robią znaki `>` i `2>`?
   * `ls -l > out.txt 2> error.log`
   * `ls -z > out.txt 2> error.log`


```
lab01/
├── all.fasta
├── error.log
├── out.txt
├── text_backup/
│   ├── README.md
│   └── README.txt
└── text_backup.tar.gz
```

## Zad. 7 (Przeglądanie zawartości plików)

Pobierz plik `http://www.combio.pl/files/apoptosis.tsv`. W tym pliku znajduje się lista nazw białek zaangażowanych w proces apoptozy (zaprogramowana śmierć komórki) u różnych organizmów. 

Podgląd pierwszych 5 linii pliku:

```
#Entry  Entry name      Length  Organism
Q562C9  MTND_RAT        179     Rattus norvegicus (Rat)
P68250  1433B_BOVIN     246     Bos taurus (Bovine)
Q4R572  1433B_MACFA     246     Macaca fascicularis (Crab-eating macaque) (Cynomolgus monkey)
A4K2U9  1433B_PONAB     246     Pongo abelii (Sumatran orangutan) (Pongo pygmaeus abelii)
```

1. Przejrzyj zawartość pobranego pliku poleceniem `less`.
   * Klawisz `f` lub `spacja` umożliwiają oglądanie pliku strona po stronie.
   * Klawisz `b` wraca do poprzedniej strony.
   * `/Homo` powoduje wyszukanie wyrazów zawierającyh frazę `Homo`. Klawisz `n` umożliwia przechodzenie po kolejnych znalezionych frazach.
   * Klawisz `q` zamyka program.
2. Użyj polecenia `wc` i odpowiedz, ile linii zawiera ten plik?
3. Wyświetl 7 pierwszych linii tego pliku.
4. Wyświetl 7 ostatnich linii tego pliku.

## Zad. 8 (Przeszukiwanie zawartości plików tekstowych)

1. Wyświetl wszystkie linie pliku `apoptosis.tsv`, które zawierają frazę `Homo sapiens`.
2. Ile białek człowieka znaleziono?
3. Wyświetl listę wszystkich białek oprócz tych należących do myszy.
4. Co będzie wynikiem polecenia `grep 'Human\|Mouse' apoptosis.tsv`?
5. Przekieruj wynik poprzedniego polecenia do pliku `human_mouse-apoptosis.tsv`.

## Zad. 9 (Potokowanie)

1. Co otrzymamy w wyniku polecenia `grep 'Human' apoptosis.tsv | wc -l`?
2. Wyświetl zawartość pliku `apoptosis.tsv` uszeregowaną ze względu na identyfikator białka.
3. Wyświetl zawartość pliku `apoptosis.tsv` uszeregowaną ze względu na nazwę organizmu.
4. Uszereguj listę ze względu na długość sekwencji białka (malejąco).
5. Wyświetl listę białek należących do człowieka uszeregowaną ze względu na długość sekwencji białka (rosnąco).
6. Uszereguj listę tak, aby w obrębie każdego organizmu (rosnąco), nazwy białek były uszeregowane ze względu na długość sekwencji (malejąco).
7. Wyświetl kolumnę zawierającą organizmy.
8. Wyświetl kolumnę zawierającą organizmy, ale tak aby podana była tylko nazwa rodzajowa gatunku (pierwszy wyraz).
9. Zmodyfikuj komendę #7, aby wyświetlić listę niepowtarzających się gatunków.
10. Zmodyfikuj komednę #9, aby obok nazwy gatunku znajdowała się liczba należących do niego białek.
11. Wyświetl zawartość pliku `apoptosis.tsv` tak aby widoczne były tylko trzy kolumny: `Id`, `Name`, `Organism`.

## Zad. 10
W pliku `http://www.combio.pl/files/various.multi` znajdują się rekordy sekwencji w formatach GenBank i EMBL/ENA. Odpowiedz na poniższe pytania.

1. Ile w sumie rekordów znajduje się w tym pliku?
2. Ile jest rekordów dla każdego formatu? (dwa osobne polecenia)
3. Z jakich organizmów pochodzą te rekordy?


## Zad. 11 
Plik `http://www.combio.pl/files/many.fasta` zawiera sekwencje w formacie FASTA pochodzące z różnych baz danych. Odpowiedz na poniższe pytania.

1. Ile sekwencji znajduje się w tym pliku?
2. Podaj nazwy baz danych, z których pochodzą te sekwencje.
   > Nazwy baz danych znajdują się między znakami `|` (np. `dbj`, `gb`).
3. Ile sekwencji pochodzi z poszczególnych baz danych?
4. Czy wśród rekordów z bazy RefSeq znajdują się jakieś białkowe rekordy?
   > Wskazówka: Co jest charakterystyczną cechą identyfikatorów białkowych bazy RefSeq?