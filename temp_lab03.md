## Dot plot

### Zad. 1
> Informacje na temat techniki dot-plot znajdują się w [prezentacji](http://combio.pl/courses/bioseq.amupie/?lecture=6) (slajdy: 39-68).

Korzystając z techniki dot-plot porównaj sześć par sekwencji DNA w pliku [dotplot.xlsx](http://www.combio.pl/files/dotplot.xlsx). Zinterpretuj każdy z sześciu wyników (a-f) pod kątem: zgodności/niezgodności sekwencji, insercji oraz sekwencji powtórzonych i palindromowych. Wypełniony arkusz dołącz do sprawozdania.


## Przyrównanie sekwencji - podstawowe informacje

### Zad. 2
Wejściowe sekwencje DNA:

```
>dna1
GATACTA
>dna2
GATTTCAA
```

Przyrównanie pary sekwencji (dwie formy zapisu):

```
dna1   GA-TACTA-                       dna1   GA-TACTA-
       || |.| |                        dna2   GATTTC-AA
dna2   GATTTC-AA
```

Odpowiedz na pytania:

1. Ile wynosi długość powyższego przyrówania?
   > Długość przyrównania obejmuje wszystkie znaki w przyrównania (w tym przerwy).
2. Na ilu pozycjach przyrównania nukleotydy są:
   * zgodne/dopasowane (*match*)
   * niezgodne/niedopasowane (*mismatch*)?
3. Ile wynosi procent identyczności przyrównanych sekwencji?
   > **Procent identyczności** = liczba identycznych nukleotydów / długość przyrównania * 100
4. Ile wynosi wartość punktacji (*score*) przyrównania sekwencji? Przyjmij poniższy system punktacji:
   * elementy zgodne (*match*): `2`
   * elementy niezgodne (*mismatch*): `-1`
   * przerwa (*gap*): `-2`


### Zad. 3
Poniżej znajduje się przyrównanie dwóch sekwencji białkowych.

```
s1   MSSEATGEW                       s1   MSSEATGEW
     ||.:.:| |                       s2   MSKQISG-W
s2   MSKQISG-W
```

Odpowiedz na pytania:

1. Ile wynosi procent *identyczności* przyrównywanych sekwencji?
2. Punktacja dopasowania/niedopasowania każdego aminokwasu zależy od użytej macierzy substytucji. Najczęściej używa się macierzy BLOSUM62 (`ftp://ftp.ncbi.nlm.nih.gov/blast/matrices/BLOSUM62`). Ile wynosi wartość punktacji w tej macierzy dla:
   * dopasowania `M-M`
   * niedopasowania `E:Q`
   * niedopasowania `S.K`
   * niedopasowania `A.I`?
3. Ile wynosi procent *podobieństwa* przyrównywanych sekwencji?
   > **Procent podobieństwa** sekwencji aminokwasowych jest zawsze większy lub równy od procentu identyczności. Podobieństwo, oprócz identycznych reszt aminokwasowych, uwzględnia również substytucje aminokwasów podobnych (tj. takie substytucje aminokwasów, które są dodatnio punktowane w użytej macierzy substytucji, w tym przypadku macierzy BLOSUM62).
   > W przypadku sekwencji nukleotydowych podobieństwo jest tym samym co identyczność.
4. Podaj wartość *score* całego przyrównania przy zastosowaniu macierzy BLOSUM62 i kary za przerwę: `-10`.


## Programowanie dynamiczne - algorytm


### Zad. 4
> https://www.youtube.com/watch?v=BYdTqq8AGgc (5min18sec)

Wykonaj na kartce przyrównanie globalne dwóch sekwencji DNA, `ATG` i `GGAATGG`, przy pomocy **algorytmu Needlemana-Wunscha**. 

Przyjmij system punktacji: 

* match: `+3`
* mismatch: `-1`
* gap: `-2`

W odpowiedzi podaj uzyskane dopasowania oraz wartość ich punktacji.


### Zad. 5
> https://www.youtube.com/watch?v=F1YId_z4pc8 (2min18sec)

Wykonaj przyrównanie lokalne sekwencji z poprzedniego zadania (ten sam system punktacji) przy pomocy **algorytmu Smitha-Watermana**. W odpowiedzi podaj uzyskane dopasowanie oraz wartość jego punktacji.



## Programy needle i water


### Zad. 6
Poniżej znajduje się sekwencja genomowa genu insuliny ponocnicny trójpręgowej oraz sekwencja CDS tego genu. 

```
>J02989.1:DNA Owl monkey (A.trivirgatus) insulin gene, genomic
GGCCTAGCTAGGGCTGCTGTCCTGGGGTGGGCTGGGAATGGGCAGCCATCAGGCAGGGGCCCCCTCACTC
CCCTACCCCGACAACCTCGGCCCACCCATGGGGGCATCTCGGGCAACCAGAGATAGAGGGCAGGGGTCTG
GGGACAGCAGCGTGAAGAGCCCCGCCCTGCAGCCTCCCGCACTCCTGGTCTAATGTGGAAAGTGGCCCAG
ATGAGGGCTTTGCTCTCCTGGAGACATTTGCCCCCAGCTGTGAGCAGGGACAGGACTGGCCACCAGCGCC
TGGTTAAGACTCTAATGACCACCCCTCCCGGCCCTGAGGAAGAGGTGCTGACGACCAAGGAGATATTCCC
GCAGACCCAGCAGCCGGGAAATGATCTGGAAAGTGCAGCCTCAGCCCCCAGCCATCTGCCAGCCCCTGCA
CCTCAGGCCCTAATGGGCCAGGCGGCAAGGTTGGCAGGTAGGGGAGATGGGCTCTGGGCCTATAAAGCCA
GCAGGGACCCAGCAGCCCTCACGCCCGGGACCAGCTGCATCACAGGAGGCCAGCGAGCAGGTCTGTTCCA
AGGGCCTTCGAGCCAGTCTGGGCCCCAGGGCTGCCCCACTCGGGGTTCCAGAGCAGTTGGACCCCAGGTC
TCAGCGGGAGGGTGTGGCTGGGCTCTGAAGCATTTGGGTGAGCCCAGGGGCTCAGGGCAGGGCACCTGCC
TTCAGCGGCCTCAGCCTGCCTGTCTCCCAGGTCTCTGTCCTTCCACCATGGCCCTGTGGATGCACCTCCT
GCCCCTGCTGGCGCTGCTGGCCCTCTGGGGACCCGAGCCAGCCCCGGCCTTTGTGAACCAGCACCTGTGC
GGCCCCCACCTGGTGGAAGCCCTCTACCTGGTGTGCGGGGAGCGAGGTTTCTTCTACGCACCCAAGACCC
GCCGGGAGGCGGAGGACCTGCAGGGTGAGCCCCACCGCCCCTCCGTGCCCCCGCCGCCCCCAGCCACCCC
CACTCCCGCTGCTCCCACCCAGCCTGGGCAGAAGGGGACAGGAGGCTGCTACCAGTAGGGAGACAGGTGG
ACTTTTTAAAAAGAAATGAAGTTCTCTTGGTCACATCCTGAAAGTGACCAGCTCCCTGTGGCCCCGGCAG
AATCTCAGCCTGAGGACGGTATTGGCTTCGGCAGCTGAGCTCCGAGATACCTCGGAGGGCACGGCAGGGT
AGGGTCCTCCCTCCACGTGCCCCTCGAGCAAATGCCTCGCAGCCCACTTCTCCACCCTCACCTGAGGACC
GCAGCTTCCAGTGTTTTGTTGAGTACATCAAGTCCTGGGTGACCTGCGGTCACAGGGTGCCCCACGCTGC
CTGCCTGTGGCAAATGCCCCATGGCACCCTGAGGAAGGCATGGCTGCTGCCACGGTGGGCCAGACCCCTG
TCCCCGGGCTTCATGACAGCCTCCATAGTCAGGAAATGGGGCAGGCACTGGTGACAGGCCCTGGAAAGAC
GTACCGGGGGTACCCGTTCAGCCTCCTGCCATGGCACCACCCAGGGCATTGAAGTCCTGTATGTCCACAC
CCAGTGTGGGGCACCCTTCCTCAACCTGGGCCCAGCTCGGCTGAGGGGGTGAGGGCGTGACCTGGGGCTG
GCGGGCAGGCGGGCACCATCTCTCCCTGACTGTGCCATCCTGCGTGCCTCTTCCTCGCCGCTGTTCCGGA
CCTGCTCTGCGTGGCTCGCCCTGGCAGTGGGGCAGGTGGAGCTGGGTGGGGGCTCTATCACGGGCAGCCT
GCCACCCTTGGAGGGTCCCATGCAGAAGCGTGGCGTCGTGGATCAGTGCTGCACCAGCATCTGCTCCCTC
TACCAGCTGCAGAACTACTGCAACTAGACTGGGCCCACAGCGACCCCGTGCCCACTGCCACCTGCACCAG
CACCTGCTCCCTCTACCAGCTGGAGAACCACAGCTGGCTGCGGCCCACAGCAGGCCCAAATGCGGCCCTG
CACCCTCCTCACCTGCACATGAGTGATGGAATAAAGCCTTGAACCAGCTCTGCTGTGCTGTTTGCGTGTT
TGGGGGGCCCTGGGCAGACCCCGCCGTCCTGGCACTGTTATGAGCCCCTCCCAGCTCTCTCCAAGCTCTC
GCCCGGCCTGCAG

>J02989.1:CDS Owl monkey (A.trivirgatus) insulin gene, complete cds
ATGGCCCTGTGGATGCACCTCCTGCCCCTGCTGGCGCTGCTGGCCCTCTGGGGACCCGAGCCAGCCCCGG
CCTTTGTGAACCAGCACCTGTGCGGCCCCCACCTGGTGGAAGCCCTCTACCTGGTGTGCGGGGAGCGAGG
TTTCTTCTACGCACCCAAGACCCGCCGGGAGGCGGAGGACCTGCAGGTGGGGCAGGTGGAGCTGGGTGGG
GGCTCTATCACGGGCAGCCTGCCACCCTTGGAGGGTCCCATGCAGAAGCGTGGCGTCGTGGATCAGTGCT
GCACCAGCATCTGCTCCCTCTACCAGCTGCAGAACTACTGCAACTAG
```

Korzystając z internetowej wersji programów **needle** i **water** (<a href="http://www.ebi.ac.uk/Tools/psa/">http://www.ebi.ac.uk/Tools/psa/</a>) wykonaj - w dwóch kartach przeglądarki - przyrównanie powyższych sekwencji.

1. Z ilu egzonów składa się badany gen insuliny?
2. Podaj pozycję początku i końca egzonów na sekwencji genomowej.
3. Dlaczego procent identyczności przyrównania w programie needle jest niższy niż w water?
4. Ponownie przyrównaj te sekwencje programem water, tym razem zmniejszając karę za otwarcie przerwy = `1`. 
   * W jaki sposób zmniejszenie kar za otwarcie przerw wpłynęło na to dopasowanie?
5. Wykonaj przyrównanie jak w poprzednim punkcie zwiększając kary za stosowanie przerw: otwarcie przerwy = `25`, wydłużenie przerwy = `5`.
   * W jaki sposób zwiększenie kar za stosowanie przerw wpłynęło na to dopasowanie?
6. Jak nazywa się model karania za przerwy przyjmujący dwa parametry: otwarcie i wydłużenie przerwy?
7. Jak nazywa się model karania za przerwy, który używałe/aś w zadaniach 1-4?


### Zad. 7
W bazie UniProt znajdź rekord acylfosfatazy u: człowieka (ID: `P14621`), *Escherichia coli* (ID: `P0AB65`) oraz *Salmonella sp.* (ID: `A0A1F2J9N6`). Wykorzystując program needle wykonaj przyrównanie następujących par sekwencji:

Organizm 1 | Organizm 2
--- | ---
*Escherichia coli* | *Salmonella sp.*
*Escherichia coli* | człowiek

1. Które przyrównanie odznacza się wyższym poziomem podobieństwa sekwencji i ile wynosi?
2. Czy wynik przyrównań jest zgodny z Twoimi oczekiwaniami na temat mutacji sekwencji?
3. Podaj kilkuaminokwasowy fragment sekwencji najbardziej zachowany w trzech analizowanych sekwencjach.
    * Jaka może być przyczyna zachowania tego fragmentu?
4. Jaka macierz substytucji aminokwasowych została użyta w tych przyrównaniach?



### Zad. 8
Z bazy UniProt pobierz sekwencje aminokwasowe globin `CTT-Z` i `CTT-VIIA` z *Chironomus thummi thummi* i zapisz je w osobnych plikach w formacie FASTA. 

Wykonaj przyrównanie tych sekwencji używając lokalnie zainstalowanych programów `needle` i `water` z pakietu EMBOSS.

1. Zapisz oba przyrównania do plików: `ctt.needle` i `ctt.water`.
2. Podaj oba polecenia użyte do uruchomienia programów.
3. Jaka macierz substytucji aminokwasowych została użyta w tych przyrównaniach?


### Zad. 9
Użyj lokalnie zainstalowanego programu `needle` i wykonaj przyrównanie sekwencji z zad. 7 stosują macierze substytucji: `EBLOSUM30`, `EBLOSUM62`, `EBLOSUM90`. Zapisz wynik każdego dopasowania. 

Odpowiedz na pytania:

1. Dlaczego procent podobieństwa sekwencji jest niższy przy użyciu macierzy przeznaczonych dla blisko spokrewnionych sekwencji?
2. Dlaczego w przyrównaniach wykonanych przy użyciu macierzy `EBLOSUM90` występuje więcej insercji/delecji mimo, że kara za przerwę nie ulega zmianie a obie sekwencje mają zbliżoną długości (`161` i `163` aminokwasy)?
3. Które z przyrównań - Twoim zdaniem - tłumaczy w najbardziej prawdopodobny sposób zmiany, jakie wystąpiły w obu sekwencjach?


## Programowanie

### Zad. 10*
W pliku [p53.fasta](./data/p53.fasta) znajduje się 10 sekwencji białka p53 różnych organizmów. Napisz skrypt, który uruchomi program *needle* dla każdej pary sekwencji z pliku i wyniki zapisze do pliku `p53.fasta.needle` w następującym formacie:

```
#id1            #id2               ident    simil    score
NP_000537.3     XP_002827020.2     97.7     98.2     2070.0
NP_000537.3     XP_016786959.2     91.0     91.5     1983.5
NP_000537.3     XP_003912321.1     95.7     96.9     2037.0
...
```
