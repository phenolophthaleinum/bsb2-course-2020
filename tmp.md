## BLAST
Zapoznaj się z algorytmem BLAST:
1. [BLAST - introduction](https://youtu.be/8A-msg23u0w) [6min26sek]
2. [BLAST - seed and extend](https://youtu.be/kAAme1fBanc) [2min11sek]
3. [BLAST - scoring alignments](https://youtu.be/2V9HNxbWUMg) [9min39sek]
4. [BLAST - scoring gaps](https://youtu.be/2YUECI6cLHo) [3min34sek]
5. [BLAST - probability](https://youtu.be/ZldgQTq4IyU) [4min17sek]
6. [BLAST - E-value](https://youtu.be/S3gr8gjKHhc) [8min12sek]
7. [BLAST - algorithms](https://youtu.be/1l2p_Q7QyB4) [6min50sek]

### Zad. 1
Poniżej znajduje się fragment sekwencji mRNA genu insuliny gryzonia koszatniczki pospolitej (*Octodon degus*).

```
>insulin Octodon degus insulin (Ins), mRNA
TGAGGCATTCTCTAACAGGTTCTCGACCCTCCGCCATGGCCCCGTGGATGCATCTCCTCACCGTGCTGGC
CCTGCTGGCCCTCTGGGGACCCAACTCTGTTCAGGCCTATTCCAGCCAGCACCTGTGCGGCTCCAACCTA
TCTGCAGAAGCGCGGCATTGTGGATCAGTGCTGTAATAACATTTGCACATTTAACCAGCTGCAGAACTAC
TGCAATGTCCCTTAGACACCTGCCTTGGGCCTGGCCTGCTGCTCTGCCCTGGCAACCAATAAACCCCTTG
AATGAG
```

Ze strony serwisu NCBI otwórz stronę programu `BLAST`. Wybierz program `Nucleotide BLAST`. W formularzu, w polu `Enter Query Sequence` umieść powyższą sekwencje w formacie FASTA. 

Użyj następujących ustawień:

* W polu `Database` wybierz bazę `Reference RNA sequences (refseq_rna)`.
* W panelu `Program Selection` wybierz `Somewhat similar sequences (blastn)`.
* Uruchom przeszukiwanie BLAST.

#### Odczytywanie wyników

Z listy otrzymanych trafień (panel *Descriptions*) zwróć uwagę na sekwencję, która uzyskała najwyższą wartość punktacji (`Max score`).

1. Podaj numer dostępu sekwencji najbardziej podobnej do sekwencji zapytania.
   * Czy znaleziona sekwencja jest identyczna do sekwencji zapytania?
2. Ile lokalnych przyrównań sekwencji wyznaczył BLAST między sekwencją zapytania a `XM_004627084.1`?
3. O czym mówią parametry `Max score` i `Total score`?
   > Przeczytaj: [NCBI](https://www.ncbi.nlm.nih.gov/Web/Newsltr/V15N2/BLView.html).
4. Ile wynosi procent identyczności między sekwencją zapytania a `XM_004627084.1`?
5. Ile wynosi wartość `Query cover`?
   * O czym informuje ten parametr [NCBI](https://www.ncbi.nlm.nih.gov/Web/Newsltr/V15N2/BLView.html)?
6. Ile wynosi wartość `E-value`?
   * O czym informuje ten parametr?
   > Obejrzyj: [NCBI YouTube](https://youtu.be/nO0wJgZRZJs) (2min33sec) i [NCBI YouTube](https://youtu.be/Z7ek7UoP7Bg) (3min)
7. Ile przerw wprowadzono w tym przyrównaniu?
8. Ile wynosi długość przyrównania?

W zakładce `Search Summary` znajdują się informacje na temat parametrów i bazy danych użytych w tym przeszukiwaniu BLAST. 

9. Ile sekwencji znajduje się w bazie danych, która została przeszukana?

Wejdź w zakładkę `Taxonomy`.

10. Podaj liczbę sekwencji oraz E-value dla sekwencji z orangutana sumatrzańskiego (*Pongo abelii*)?
11. Czy na liście trafień znajdują się sekwencje człowieka?


### Zad. 2
Gen *FOXP2* u naczelnych warunkuje zdolność komunikacji werbalnej. Obecność zaledwie jednej uszkodzonej kopii tego genu u człowieka prowadzi do poważnych zaburzeń artykulacji wyrazów. Twoim zadaniem jest sprawdzenie, czy gen *FOXP2* występuje również u zwierząt innych niż naczelne.

Poniżej znajduje się sekwencja białkowa genu FOXP2 człowieka.

```
>NP_055306.1 forkhead box protein P2 isoform I [Homo sapiens]
MMQESATETISNSSMNQNGMSTLSSQLDAGSRDGRSSGDTSSEVSTVELLHLQQQQALQAARQLLLQQQT
SGLKSPKSSDKQRPLQVPVSVAMMTPQVITPQQMQQILQQQVLSPQQLQALLQQQQAVMLQQQQLQEFYK
KQQEQLHLQLLQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQHPGKQAKEQQQQQQQQQQL
AAQQLVFQQQLLQMQQLQQQQHLLSLQRQGLISIPPGQAALPVQSLPQAGLSPAEIQQLWKEVTGVHSME
DNGIKHGGLDLTTNNSSSTTSSNTSKASPPITHHSIVNGQSSVLSARRDSSSHEETGASHTLYGHGVCKW
PGCESICEDFGQFLKHLNNEHALDDRSTAQCRVQMQVVQQLEIQLSKERERLQAMMTHLHMRPSEPKPSP
KPLNLVSSVTMSKNMLETSPQSLPQTPTTPTAPVTPITQGPSVITPASVPNVGAIRRRHSDKYNIPMSSE
IAPNYEFYKNADVRPPFTYATLIRQAIMESSDRQLTLNEIYSWFTRTFAYFRRNAATWKNAVRHNLSLHK
CFVRVENVKGAVWTVDEVEYQKRRSQKITGSPTLVKNIPTSLGYGAALNASLQAALAESSLPLLSNPGLI
NNASSGLLQAVHEDLNGSLDHIDSNGNSSPGCSPQPHIHSIHVKEEPVIAEDEDCPMSLVTTANHSPELE
DDREIEEEPLSEDLE
```

Użyj serwisu [BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi) (`Protein BLAST`) w celu przeszukania bazy danych RefSeq, ograniczając wyszukiwanie do sekwencji zwierząt (*Metazoa*) i wykluczając z nich sekwencje pochodzące z naczelnych (*Primates*).

Z listy otrzymanych trafień wybierz jedną sekwencję, która najbardziej odpowiada sekwencji *FOXP2*.

1. Z jakiego organizmu pochodzi ta sekwencja?
2. Ile wynosi E-value tego dopasowania?
3. Podaj procent identyczności i podobieństwa tego dopasowania.
4. Ile przerw znajduje się w tym dopasowaniu?

Skorzystaj z zakładki `Taxonomy`.

4. W której gromadzie zwierząt (np. ptaki / ssaki / gady) po raz pierwszy pojawił się (w toku ewolucji) gen FOXP2?


## Lokalny program NCBI BLAST
> **Zainstaluj program BLAST na swoim komputerze. Program BLAST działa na systemach Windows, Linux i MacOS ([pobierz](ftp://ftp.ncbi.nih.gov/blast/executables/blast+/LATEST)).**


### Zad. 3
W pliku [mito_genes.fasta](./data/mito_genes.fasta) znajdują się sekwencje trzech genów mitochondrialnego DNA człowieka (*COX1*, *ND6*, *tRNA-Pro*). W pliku [mito_genomes.fasta](./data/mito_genomes.fasta) znajdują się sekwencje całych genomów mitochondrialnych pochodzące z różnych organizmów (np.: mysz, szympans). Zapisz oba pliki na dysku i umieść je w jednym katalogu. Twoim zadaniem jest użycie lokalnej wersji programu BLAST w celu zidentyfikowania lokalizacji trzech genów w sekwencjach genomowych.

Przygotowanie bazy sekwencji do przeszukania:

```bash
makeblastdb -in mito_genomes.fasta -dbtype nucl
```

Uruchomienie programu blastn:

```bash
blastn -query mito_genes.fasta -db mito_genomes.fasta                # Wyświetlenie wyników na ekran
```

```bash
blastn -query mito_genes.fasta -db mito_genomes.fasta -out results.txt      # Zapis wyników do pliku
```

1. W których genomach mitochondrialnych występuje gen *tRNA-Pro*?
2. Czy sekwencja tego genu jest identyczna we wszystkich genomach?
3. Sprawdź jakie parametry może przyjmować program blastp (`blastn –help`).
   * Wykonaj ponowne przeszukiwanie, tym razem wyświetlając wyniki w formie tabeli (format tabularny z komentarzami).
   * Podaj numery kolumn, w których znajdują się E-value i Score.
4. Podaj pozycję startu i końca genu *tRNA-Pro* w sekwencji szympansa.
5. Zmodyfikuj poprzednie polecenie, aby wyświetlić wyniki w formacie tabularnym bez komentarzy.
6. Zmodyfikuj poprzednie polecenie zmieniając wartość parametru `task` z `megablast` na `blastn`.
   * Czy w wyniku otrzymano mniej, czy więcej wyników? 
7. Zmodyfikuj poprzednie polecenie, aby wyświetlić przyrównania, które uzyskały wartość E-value <= `1e-05`.
8. Użyj odpowiedniego polecenie Linuxa, aby posortować otrzymany wynik, aby w obrębie każdego organizmu (genomu) trafienia były uszeregowane zgodnie z ich lokalizacją w genomie.
9. Użyj odpowiedniego polecenia Linuxa, aby odpowiedzieć na pytanie ile trafień znalazł program BLAST w obrębie każdego organizmu.
10. Do polecenia z pkt. 9 dodaj kolejny potok, aby uszeregować wynik ze względu na malejącą liczbę trafień i nazwę organizmu.


### Zad. 4
W pliku [yeast_query.fasta](./data/yeast_query.fasta) znajduje się 10 sekwencji CDS pochodzących z drożdży piekarniczych (*Saccharomyces cerevisiae*), z kolei w pliku [spombe.fasta.tar.gz](./data/spombe.fasta.tar.gz) znajdują się wszystkie sekwencje CDS drożdży *Schizosaccharomyces pombe*.

Skonstruuj polecenie programu BLAST, aby dla każdego z 10 genów w wynikach pojawiał się tylko jedno - najwyżej punktowane - trafienie, a format wyniku ograniczony był do następujących pól: identyfikator sekwencji zapytania i sekwencji z bazy danych, identyczność, punktacja, E-value.


Przykładowy output:

```
YJL200C     SPBP4H10.15.1     64.82   386     1e-95
YPR187W     SPCC1020.04c.1    75.22   172     3e-38
YML075C     SPCC162.09c.1     69.74   474     2e-119   
...
```

Podaj użyte polecenie i wklej do sprawozdania uzyskany wynik.


## Profile sekwencji / PSI-BLAST

### Zad. 5
> Zapoznaj się z budowaniem profili sekwencji: [YouTube](https://youtu.be/419r3r87nAk) [6min10sek].

W oparciu o poniższe przyrównanie sekwencji utwórz w tabeli profil, który będzie przedstawiał, ile razy dany aminokwas występuje w danej pozycji (kolumnie) dopasowania.

```
VDFWAE
VDFWAP
VDFWAE
VDFWAE
VDFWAP
VDFSAT
VDFSAT
VDFSAT
VDFSAT
VDFSAT
VDFSAT
VDFSAV
VDFSAE
LDFYAT
LDFYAT
VDFTAS
ADFYAD
```

<table>
  <tr>
    <th>pozycja</th>
    <th>A</th>
    <th>C</th>
    <th>D</th>
    <th>E</th>
    <th>F</th>
    <th>G</th>
    <th>H</th>
    <th>I</th>
    <th>K</th>
    <th>L</th>
    <th>M</th>
    <th>N</th>
    <th>P</th>
    <th>R</th>
    <th>S</th>
    <th>T</th> 
    <th>Q</th>
    <th>Y</th>
    <th>V</th>
    <th>W</th>   
  </tr>

  <tr>
    <td>1</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>2</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>3</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>4</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>5</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>6</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>

Odpowiedz na pytania:

1. Jaka będzie wartość punktacji dla peptydu `ACGWAP`?
2. Wygeneruj sekwencję sześciu aminokwasów, która będzie najbardziej podobna do sekwencji profilu. Podaj również wartość jej punktacji.


### Zad. 6
> **Zapoznaj się z algorytmem PSI-BLAST [YouTube](https://youtu.be/T3kHEieyylk) [6min30sek].**

Poniżej znajduje się sekwencja białkowa, którą chcesz scharakteryzować strukturalnie i funkcjonalnie przy użyciu internetowego serwisu NCBI BLAST.

```
>Query
MKDTDLSTLLSIIRLTELKESKRNALLSLIFQLSVAYFIALVIVSRFVRYVNYITYNNLV
EFIIVLSLIMLIIVTDIFIKKYISKFSNILLETLNLKINSDNNFRREIINASKNHNDKNK
LYDLINKTFEKDNIEIKQLGLFIISSVINNFAYIILLSIGFILLNEVYSNLFSSRYTTIS
IFTLIVSYMLFIRNKIISSEEEEQIEYEKVATSYISSLINRILNTKFTENTTTIGQDKQL
YDSFKTPKIQYGAKVPVKLEEIKEVAKNIEHIPSKAYFVLLAESGLRPGELLNVSIENID
LKARIIWINKETQTKRAYFSFFSRKTAEFLEKVYLPAREEFIRANEKNIAKLAAANENQE
IDLEKWKAKLFPYKDDVLRRKIYEAMDRALGKRFELYALRRHFATYMQLKKVPPLAINIL
QGRVGPNEFRILKENYTVFTIEDLRKLYDEAGLVVLE
```

#### 6.1. Standardowe przeszukanie BLAST

Zidentyfikuj sekwencje homologiczne wykorzystując serwis [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi) wybierając program `Protein BLAST`. Ogranicz przeszukiwanie do bazy `PDB (Protein Data Bank)`.

1. Ile istotnych statystycznie wyników zostało znalezionych (E-value < 1)?

#### 6.2. Przeszukanie PSI-BLAST

Wróć do strony BLAST i wykonaj ponownie przeszukiwanie ograniczając wyszukiwanie do bazy danych `nr (non-redundant protein sequences)` oraz wybierając algorytm `PSI–BLAST (Position-Specific Iterated BLAST)`.

2. Ile istotnych statystycznie wyników zostało znalezionych?
   > *Wskazówka*: zaznacz wszystkie istotne statystycznie wyniki poprzez Select: All w sekcji `Sequences producing significant alignments with E-value BETTER than threshold`
3. Czy wśród istotnych statystycznie wyników znajduja się wyniki pochodzące z bazy PDB?
   > *Wskazówka*: szukaj identyfikatora bazy PDB w kolumnie `Accession`. Identyfikator składa się z min. 4 znaków, w których pierwszy jest cyfrą np. `1XYZ_A`

#### 6.3. Tworzenie i zapisanie profilu PSSM

Uruchom drugą iterację programu BLAST poprzez naciśnięcie przycisku `Go` (znajdującego się nad lub pod tabelą z wynikami).

4. Ile istotnych statystycznie wyników zostało znalezionych?
5. Co oznaczają wiersze w tabeli wyróżnione żółtym kolorem?
6. Dlaczego w wynikach drugiego przeszukiwania PSI-BLAST znajduje się więcej istotnie statystycznych wyników?

Naciśnij przycisk `Download` u góry strony z wynikami BLAST. Zapisz profil PSSM na dysk. Nie zamykaj karty przeglądarki z wynikami.

#### 6.4. Przeszukiwanie bazy sekwencji przy użyciu matrycy PSSM
Otwórz stronę BLAST w nowej karcie przeglądarki. Ogranicz wyszukiwanie do bazy danych `PDB` oraz wybierz algorytm `PSI–BLAST`. Rozwiń menu `Algorithm parameters` i wybierz zapisany wcześniej plik z matrycą PSSM w sekcji `Upload PSSM`.
> Pole tekstowe dla sekwencji pozostaw puste, ponieważ wykonujemy przeszukiwanie profilem PSSM.

7. Ile istotnie statystycznie wyników pochodzi z bazy PDB?
8. Podaj identyfikatory PDB i wartości E-value dwóch najlepszych wyników przeszukiwania.
9. Podaj wartości `Query coverage` oraz procent identyczności i podobieństwa dla najlepszego wyniku przeszukiwania.

Przejdź do rekordu odpowiadającemu najlepszemu wynikowi przeszukiwania.

10. Jakie to białko?
11. Z jakiego organizmu pochodzi ten rekord?
12. Jaką metodą eksperymentalną została otrzymana struktura tego białka?

#### 6.5. Ponowna iteracja i utworzenie profilu PSSM
Wróć do karty z wynikami przeszukiwania PSI-BLAST nr 2 i wykonaj kolejne przeszukiwanie (`Run PSI-Blast iteration 3`). Zapisz na dysku profil PSSM.

Wykonaj nowe przeszukiwanie PSI-BLAST w bazie PDB z wykorzystaniem nowo zapisanego profilu PSSM.

13. Ile istotnie statystycznie wyników pochodzi z bazy PDB?
14. Podaj identyfikator PDB i wartość E-value najlepszego wyniku przeszukiwania.
15. Podaj wartości `Query coverage` oraz procent identyczności i podobieństwa dla najlepszego wyniku przeszukiwania.

#### 6.6. Przyrównanie sekwencji zapytania i sekwencj i z bazy danych
Z wyników BLAST pobierz w formacie FASTA sekwencję najbardziej odpowiadającą sekwencji zapytania. Korzystając z narzędzi poznanych na poprzednich zajęciach wykonaj globalne przyrównanie pobranej sekwencji i sekwencji zapytania.

16. Podaj procent identyczności i podobieństwa uzyskanego dopasoewania.
17. Podaj najdłuższy region o nieprzerwanej stuprocentowej identyczności.


## Programowanie dla chętnych

### Zad. 7
Napisz skrypt, który zliczy występowanie każdej reszty (aminokwasu) w każdej kolumnie dopasowania sekwencji z pliku [profile.aln](./data/profile.aln).

### Zad. 8
Zmodyfikuj skrypt, aby zamiast zliczeń przedstawiał częstości reszty w danej kolumnie (suma częstości reszt w danej kolumnie powinna być równa 1).

### Zad. 9
Zmodyfikuj skrypt, aby zamiast częstości danej reszty w danej pozycji obliczał logarytm ilorazu szans. Logarytm ilorazu szans to logarytm ze stosunku częstości występowania danej reszty w danej kolumnie przez ogólną częstość występowania danego aminokwasu.

> Wskazówka: Ponieważ logarytm w zerze nie jest określony, powszechną parktyką jest dodanie niewielkiej stałej wartości liczbowej (np. `0.001`) do wszystkich obliczanych częstości.

```python
# General amino-acid frequencies
AA = {
  'A': 0.082, 'Q': 0.039, 'L': 0.096, 'S': 0.066, 
  'R': 0.055, 'E': 0.067, 'K': 0.058, 'T': 0.053,
  'N': 0.040, 'G': 0.070, 'M': 0.024, 'W': 0.010,
  'D': 0.054, 'H': 0.022, 'F': 0.038, 'Y': 0.029,
  'C': 0.013, 'I': 0.059, 'P': 0.047, 'V': 0.068,
}
```