## NCBI Enrez Direct / E-utilities

> Pakiet NCBI Entrez Direct umożwlia dostęp do baz danych serwisu NCBI przy użyciu wiersza poleceń. Dokumentacja pakietu: [NCBI Entrez Direct](https://www.ncbi.nlm.nih.gov/books/NBK179288/).


### Zad. 1
W terminalu wpisz poniższe polecenie `einfo` z pakietu NCBI Entrez Direct:

```bash
einfo -dbs
```

1. Ile baz danych jest obsługiwanych przez pakiet?
2. Wyświetl informacje o nukleotydowej bazie danych:

   ```bash
   einfo -db nucleotide
   ```

   * Jak nazywa się format danych, który otrzymałe/aś?
   * Ile sekwencji nukleotydowych znajduje się w tej bazie (`Count`)?
3. Ile artykułów znajduje się w bazie PubMed?


### Zad. 2
W przeglądarce internetowej otwórz stronę NCBI, wybierz bazę *Protein* i przejdź do zaawansowanego wyszukiwania (*Advanced*). Utwórz zapytanie w celu znalezienia wszystkich białek kodowanych przez gen o nazwie *TNRC6A*, pochodzących z człowieka i bazy daych RefSeq. 

1. Podaj użyte zapytanie (pole `Search details`). 
2. Ile rekordów znaleziono?


### Zad. 3
W terminalu uruchom poniższe polecenie.

```bash
esearch -db protein -query "TNRC6A[Gene Name] AND Homo sapiens[Organism] AND refseq[Filter]"
```

1. Ile rekordów znaleziono?

Uruchom poniższe polecenia:

```bash
esearch -db protein -query "TNRC6A[Gene Name] AND Homo sapiens[Organism] AND refseq[Filter]" | \
xtract -outline
```

```bash
esearch -db protein -query "TNRC6A[Gene Name] AND Homo sapiens[Organism] AND refseq[Filter]" | \
xtract -pattern ENTREZ_DIRECT -element Count
```

2. Do czego służy polecenie `xtract`?


### Zad. 4
Uruchom poniższe polecenie.

```bash
esearch -db protein -query "TNRC6A[Gene Name] AND Homo sapiens[Organism] AND refseq[Filter]" | \
efetch -format fasta
```

1. Do czego służy polecenie `efetch`?
2. Zmodyfikuj polecenie, aby wyświetlić sekwencje w formacie GenBank.


### Zad. 5
Korzystając z poleceń `esearch` i `efetch` wyszukaj sekwencje białkowe w formacie FASTA, które mają w tytule wyraz `caspase` i pochodzą z *Bacillus subtilis*.

1. Ile białek znaleziono?
2. Podaj użyte polecenie.


### Zad. 6
Korzystając z poleceń `esearch` i `efetch` przeszukaj nukleotydową bazę i wyświetl w formacie GenBank wszystkie cząsteczki mRNA ludzkiego genu o nazwie *TNRC6A* pochodzące z bazy RefSeq. 

1. Ile sekwencji znaleziono?
2. Podaj użyte polecenie.

Kolejno modyfikuj polecenie przy użyciu potoków Linuxa, aby odpowiedzieć na następujące pytania:

3. Na którym chromosomie znajdują się znalezione geny?
4. Jaka jest łączna liczba egzonów tych transkryptów?
5. Wyświetl linie rekordów zaczynające się od `LOCUS` i uszereguj je ze względu na malejącą długość sekwencji.
   
   ```
   LOCUS       NM_001351850            8526 bp    mRNA    linear   PRI 28-DEC-2017
   LOCUS       NM_014494               8495 bp    mRNA    linear   PRI 28-DEC-2017
   LOCUS       XM_017023143            8363 bp    mRNA    linear   PRI 06-JUN-2016
   LOCUS       NM_001330520            8348 bp    mRNA    linear   PRI 28-DEC-2017
   LOCUS       XM_017023144            7034 bp    mRNA    linear   PRI 06-JUN-2016
   ...
   ```

4. Wyświetl listę niepowtarzających się identyfikatorów do bazy PubMed odnoszących się do znalezionych rekordów.
    
    ```
    PUBMED   11950943
    PUBMED   12831532
    PUBMED   13130130
    PUBMED   26446993
    PUBMED   27009120
    ...
    ```


### Zad. 7
Uruchom poniższe polecenie:

```bash
esearch -db nucleotide -query "TNRC6A[Gene Name] AND Homo sapiens[Organism] \
 AND refseq[Filter] AND mrna[Filter]" | efetch -format docsum
```

Do powyższego polecenia dołącz polecenie `xtract`, aby uzyskać poniższe wyniki:

```
1370468299  XM_017023152  6771  mRNA  linear  human 2020/03/02
1370468297  XM_024450233  6828  mRNA  linear  human 2020/03/02
1370468296  XM_017023150  8390  mRNA  linear  human 2020/03/02
1370468294  XM_024450232  8426  mRNA  linear  human 2020/03/02
1370468293  XM_017023148  8429  mRNA  linear  human 2020/03/02
1370468292  XM_017023145  8537  mRNA  linear  human 2020/03/02
1370468291  XM_017023144  7277  mRNA  linear  human 2020/03/02
1370468289  XM_024450231  8606  mRNA  linear  human 2020/03/02
1034594316  XM_017023154  6981  mRNA  linear  human 2020/03/02
1034594315  XM_005255257  6977  mRNA  linear  human 2020/03/02
1034594313  XM_017023153  6977  mRNA  linear  human 2020/03/02
1034594298  XM_017023146  7019  mRNA  linear  human 2020/03/02
1676319460  NM_001351850  8506  mRNA  linear  human 2020/02/29
1676317404  NM_001330520  8344  mRNA  linear  human 2020/02/29
1519243019  NM_014494     8491  mRNA  linear  human 2020/02/28
```

### Zad. 8
Przy pomocy narzędzi `esearch`, `efetch`, `xtract` i `sort` utwórz jedno polecenie, które wyszuka w bazie `gene` wszystkie geny o nazwie *BRCA2* u naczelnych, tak aby wyświetlić poniższą listę (tj. identyfikator, nazwa genu, organizm) uszeregowaną ze względu na nazwę organizmu.

```
105726195 BRCA2 Aotus nancymaae
100397509 BRCA2 Callithrix jacchus
103267329 BRCA2 Carlito syrichta
108310783 BRCA2 Cebus capucinus imitator
105587897 BRCA2 Cercocebus atys
103214248 BRCA2 Chlorocebus sabaeus
...
```

### Zad. 9
Utwórz polecenie `efetch` wyświetlające sekwencje FASTA o numerach dostępu: `NP_476567` i `NP_476565`.


### Zad. 10
Wyświetl abstrakty artykułów bazy PubMed dotyczących schizofrenii i opublikowanych w ciągu ostatnich 30 dni. Podaj użyte polecenie. Ile artykułów znaleziono?

> Wskazówka: Ograniczenie wyników ze względu na czas opublikowania umożliwi narzędzie [efilter](https://www.ncbi.nlm.nih.gov/books/NBK179288/#chapter6.Searching_and_Filtering).


### Zad. 11
Korzystając z narzędzia [elink](https://www.ncbi.nlm.nih.gov/books/NBK179288/#chapter6.Writing_Commands_on_Multiple_Li) wyszukaj wszystkie sekwencje białkowe, o których mowa w artykułach o schizofrenii z ostatnich 60 dni. Podaj użyte polecenie oraz liczbę sekwencji.


### Zad. 12
Podaj polecenie `efetch`, które wyświetli abstrakty trzech artykułów o identyfikatorach: `24102982`, `21171099`, `17150207`.


## Programowanie (dla chętnych)


## Zad. 13
W pliku [vertebrates.txt](http://www.combio.pl/files/vertebrates.txt) znajdują się nazwy gatunkowe kilku kręgowców. Napisz skrypt, który dla każdego organizmu z pliku wyszuka (korzystając z E-Utilities) sekwencje białkowe genu TNRC6A z bazy RefSeq. Znalezione sekwencje w obrębie organizmu powinny zostać zapisane do pliku tekstowego w formacie FASTA. Na przykład, sekwencje białkowe TNRC6A dla organizmu *Mus musculus* powinny zostać zapisane w pliku `mus_musculus.fasta`. Uwzględnij w skrypcie sugestię NCBI, aby nie przekraczać trzech zapytań do bazy w ciągu 1 sekundy.