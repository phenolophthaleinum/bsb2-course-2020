## Przyrównanie wielu sekwencji (MSA)

> **Zapoznaj się na YouTube z zasadą działania algorytmów służących do przyrównywania wielu sekwencji: [Multiple sequence alignment](https://youtu.be/g0vTcC7kOcA) [50min].**

### Zad. 1
W pliku [ube.fasta](./data/ube.fasta) znajdują się sekwencje białkowe aktywnego enzymu koniugującego ubikwitynę pochodzące z wielu organizmów. Korzystając z programu ClustalOmega (<a href="http://www.ebi.ac.uk/Tools/msa/">http://www.ebi.ac.uk/Tools/msa/</a>) wykonaj ich dopasowanie.
> Obsługa programu Clustal Omega: [YouTube](https://youtu.be/H07g6X-RzRo) [3min].

1. Co oznaczają gwiazdki (`*`), dwukropki (`:`) i kropki (`.`) w otrzymanym dopasowaniu?
   > Przeczytaj: [Wikipedia - Reading Multiple Sequence Alignment Output](https://en.wikipedia.org/wiki/Clustal#Input/Output).
2. Wypisz aminokwasy, które są całkowicie zachowane u wszystkich organizmów.
3. Jaka może być przyczyna zachowania tych aminokwasów we wszystkich sekwencjach?
4. Podaj procent identyczności sekwencji enzymu drożdżowego `UBC6_YEAST` (`P33296)` i sekwencji enzymu królika `UB2R2_RABIT` (`Q29503`)?
   > Wskazówka: `Result Summary` –> `Percent Identity Matrix`

W bazie RefSeq istnieją dwa białka z drożdży o numerach dostępu: `NP_588162` i `NP_011428`, które należą do tej samej rodziny białkowej, ale **nie posiadają** aktywności katalitycznej. Otwórz program ClustalOmega w nowej karcie przeglądarki i wykonaj dopasowanie sekwencji z pliku `ube.fasta` dodając do niego dwie sekwencje z drożdży.

5. Jakie aminokwasy zostały zachowane w tym dopasowaniu?
6. Porównaj wyniki obu przyrównań i podaj aminokwas kluczowy dla aktywności enzymu. Uzasadnij swoją odpowiedź.


### Zad. 2
W pliku [myoglobins.fasta](./data/myoglobins.fasta) znajdują się sekwencje białkowe mioglobiny z 14 gatunków kręgowców. Wykonaj dopasowanie tych sekwencji przy pomocy programów: [ClustalOmega](http://www.ebi.ac.uk/Tools/msa/), <a href="http://tcoffee.crg.cat/apps/tcoffee/do:regular">T-COFFEE</a> i <a href="https://mafft.cbrc.jp/alignment/server/">MAFFT</a>. Umieść wyniki w sprawozdaniu. 

1. Podaj przykładowy fragment sekwencji, dla którego programy zwracają różne dopasowania.
2. Podaj najdłuższy region o nieprzerwanej stuprocentowej identyczności.


## Podstawowe pojęcia z filogenetyki

### Zad. 3

1. Podpisz rysunek (rodzaj drzewa i co jest na nim zaznaczone)
   > Przeczytaj: [Tree terminology](https://www.ncbi.nlm.nih.gov/Class/NAWBIS/Modules/Phylogenetics/phylo7.html).

<p align="center"><img src="./images/tree01.png" width="400"></p>

2. Na czym polega różnica w interpretacji między drzewem nieukorzenionym a ukorzenionym?
   > Przeczytaj: [The difference between rooted and un-rooted phylogenetic tree](https://brainly.in/question/3769990).

### Zad. 4

Przedstawione poniżej drzewo nieukorzenione można przekształcić w 5 drzew ukorzenionych w zależności od miejsca lokalizacji korzenia (miejsca te są zaznaczone cyframi).

<p align="center"><img src="./images/tree-unrooted.png" width="300px"/></p>

Przykład takiego drzewa, w którym korzeń umieszczony jest przy odgałęzieniu 1 przedstawiony jest poniżej:

<p align="center"><img src="./images/tree-rooted.png" width="300px"/></p>

1. Narysuj pozostałe możliwości drzew ukorzenionych (umieszczając korzeń w 2, 3, 4, 5).


#### Przestrzenie drzew

Liczba możliwych drzew dla różnej liczby sekwencji.

```
Liczba sek. (N)   Drzewa nieukorzenione   Drzewa ukorzenione
5                 15                      105
6                 105                     945
7                 945                     10 395
8                 10 395                  135 135
N                 (2N - 5)!!              (2N - 3)!!
```

Na przykład, dla 9 sekwencji (*N* = 9) liczba możliwych drzew nieukorzenionych jest równa:

```
(18 - 5)!! = 13!! = 1 * 3 * 5 * 7 * 9 * 11 * 13 = 135 135
```

2. Ile istnieje drzew nieukorzenionych i ukorzenionych dla 10 sekwencji?


### Zad. 5

Poniższe drzewa są nieukorzenione, a długości ich gałęzi nie odpowiadają odległości ewolucyjnej.

<p align="center"><img src="./images/tree02.png" width="500px"/></p>

Które drzewa są ze sobą równoważne?


### Zad. 6
> Przeczytaj: [Difference Between Monophyletic Paraphyletic and Polyphyletic](https://www.differencebetween.com/difference-between-monophyletic-and-vs-paraphyletic-and-vs-polyphyletic/).

1. Przyporządkuj grupy taksonów (monofiletyczny, polifiletyczny, parafiletyczny) do odpowiedniego drzewa poniżej.

![Tree04](./images/tree03.png)

2. Podaj po jednym przykładzie biologicznym dla każdej z grupy.


### Zad. 7
> **Zapoznaj się na YouTube z tworzeniem drzewa filogentycznego za pomocą metody średnich połączeń (UPGMA): [Oxford Academic](https://youtu.be/09eD4A_HxVQ) [8min50sek]**

Poniższa tabela przedstawia cztery aminokwasy wśród trzech gatunków.

````
Gorilla   Lys - Glu - His - Lys
Horse     Arg - Lys - His - Lys
Zebra     Arg - Lys - His - Lys
````

Które drzewo najodpowiedniej opisuje relację między powyższymi gatunkami.

<p align="center"><img src="./images/tree04.png" width="500px"/></p>


## MEGA
Zainstaluj program MEGA (Molecular Evolutionary Genetic Analysis): [https://www.megasoftware.net](https://www.megasoftware.net).

### Zad. 7 - Pochodzenie niedźwiedzia polarnego i pandy wielkiej.

W pliku [bears.fasta](./data/bears.fasta) znajdują się sekwencje 12s rRNA (niekodujące białka) pochodzące z 7 gatunków niedźwiedzi i 4 gatunków innych kręgowców:

1. American Black bear
2. American Brown bear
3. Asiatic Black bear
4. Spectacled bear
5. Polar bear
6. Giant panda
7. Red panda
8. Dog
9. Racoon
10. Crocodile skink
11. Cow

---


#### 7.1 Dopasowanie sekwencji

* Otwórz program MEGA.
* Otwórz w programie sekwencje znajdujące się w pliku [bears.fasta](./data/bears.fasta).
   * `Align` > `Edit/Build Alignment` > `Retrieve sequences from a file`.
* Zaznacz wszystkie sekwencje (Ctrl+A lub `Edit` > `Select all`) i przeprowadź ich dopasowanie (`Alignment` > `Align by ClustalW`) korzystając z domyślnych ustawień.


1. Jaka jest długość dopasowania?


#### 7.2 Analiza filogenetyczna

* W oknie dopasowania sekwencji wybierz z menu wybierz `Data` > `Phylogenetic Analysis`.
* W głównym oknie programu MEGA wygeneruj drzewo używając algorytmu *Neighbor-Joining (NJ)* 
   * `Analysis` > `Phylogeny` > `Construct Neighbor-Joining tree`.
* W opcjach `Test of Phylogeny` ustaw `None`.
* Naciśnij przycisk `Compute`.


1. Wymień dwie "pary niedźwiedzi", które są ze sobą najbardziej spokrewnione?
2. Które niedźwiedzie są ze sobą bardziej spokrewnione: 
   * American Black - Asia Black Bear 
   * Spectacled Bear - Polar Bear?

Ustaw korzeń drzewa na gałąź `Crocodillian skink (outgroup)`, wyświetl drzewo w pełnej wielkości okna (`Fit tree to screen`) i wyświetl długości gałęzi (`Display of branch lengths`).

3. Czy panda wielka jest bardziej spokrewniona z niedźwiedziami amerykańskimi czy azjatyckimi?
4. Czy Red Panda jest w ogóle niedźwiedziem?
5. Który z niedźwiedzi jest najstarszy?


### Zad. 8
Sekwencje z poprzedniego zadania należą do żyjących gatunków niedźwiedzi. Niedźwiedź jaskiniowy (*Ursus spelaeus*) wymarł ok. 20 tys. lat temu. Wybierz dowolną sekwencję 12s rRNA z pliku [bears.fasta](./data/bears.fasta), użyj jej jako sekwencji zapytania w programie BLAST i zidentyfikuj sekwencję 12s rRNA niedźwiedzia jaskiniowego. Następnie znalezioną sekwencję dołącz do sekwencji pozostałych gatunków w pliku [bears.fasta](./data/bears.fasta) i zbuduj drzewo filogenetyczne.

1. Który niedźwiedź jest najbliższym krewnym wymarłego niedźwiedzia jaskiniowego?
2. Czy dołączenie niedźwiedzia jaskiniowego zmieniło układ pozostałych taksonów na drzewie?


### Zad. 9 (Ocena wiarygodności drzewa: metoda *bootstrap*)
> Bootstrap jest metodą statystyczną, która opiera się na tworzeniu dużej liczby replik z niewielkimi zmianami w danych początkowych. Drzewa skonstruowane ze zbiorów danych z wprowadzonymi losowymi zmianami dają rozkład topologii drzew, który umożliwia statystyczną ocenę każdego pojedynczego kladu z danego drzewa.
> Wykorzystanie metody bootstrap do oceny wiarygności skonstruowanego wcześniej drzewa filogenetycznego obejmuje wygenerowanie wielu dopasowań sekwencji (zazwyczaj między 100 a 1000). Dla każdego z wygenerowanych dopasowań jest wyznaczane drzewo filogenetyczne. W zbiorze takich drzew niektóre drzewa będą miały taką samą topologię, jak drzewo oryginalne. Inne będą się od niego różnić. Każdemu z węzłów w oryginalnym drzewie jest następnie przypisywana tzw. wartość bootstrap równe odsetkowi wygenerowanych drzew, w których obserwowano dokładnie takie samo rozgałęzienie linii ewolucyjnych.
> Nie ma ustalonej reguły, która mówiłaby jak duża musi być wartość bootstrap, aby uznać odpowiedni węzeł drzewa za wiarygodny, a tym samym uznać, że gatunki, których linie ewolucyjne się w nim zbiegają, tworzą klad. W praktyce przyjmuje się, że wartości powyżej 70% takie twierdzenie usprawiedliwiają.

Utwórz drzewo sekwencji niedźwiedzi korzystając z algorytmu Neighbor-Joining i zaznaczając `Test of Phylogeny`: `Bootstrap method` (No. of Boostrap Replications): `1000`.

1. Co oznaczają liczby znajdujące się na węzłach uzyskanego drzewa?
2. Czy na drzewie znajdują się grupy sekwencji o niskim poziomie ufności?
3. Które rozgałęzienia na drzewie są najbardziej wiarygodne.
4. Na czym polega różnica w konstrukcji drzewa `Original Tree` i `Consensus Tree`?
   > `Original tree` jest drzewem zbudowanym na oryginalnym przyrównaniu sekwencji. Natomiast `Bootstrap consensus tree` jest drzewem konsensusowym zbudowanym w oparciu o wszystkie repliki drzew, które zostały wygenerowane podczas testu bootstrap. Drzewo takie jest złożone z kladów, które występowały najczęściej w replikach.

Oblicz dystanse między wszystkimi parami sekwencji niedźwiedzi (`Analysis` > `Distance` > `Compute Pairwise Distance`)

5. Która para sekwencji odznacza się największym/najmniejszym dystansem?

Ponownie oblicz dystans między sekwencjami stosując jako model substytucji: `Kimura 2-parameter model`.

6. Ile wynosi dystans między `Spectacled Bear` a `Polar Bear`.


### Zad. 10 (Algorytmy grupowania)
> **Zapoznaj się z algorytmami tworzenia drzew filogenetycznych: [Choice of Trees](https://www.zoology.ubc.ca/~bio336/Bio336/Lectures/Lecture14/Overheads.html).**

W programie MEGA wykonaj drzewo filogenetyczne sekwencji niedźwiedzi w oparciu o poniższe algorytmy, stosując metodę bootstrap z 100 pseudoreplikacjami.

* największej wiarygodności (Maximum Likelihood Tree)
* minimalnej ewolucji (Minimum-Evolution Tree)

Czy drzewa uzyskane tymi metodami pozwalają wyciągnąć podobne wnioski na temat spokrewnienia niedźwiedzi, co w przypadku drzewa otrzymanego metodą NJ?


### Zad. 11 (Drzewo genów)
W pliku [gw182.fasta](./data/gw182.fasta) znajduje się 17 sekwencji białkowych genu GW182 (TNRC6) pochodzących z bezkręgowców i kręgowców. W programie MEGA utwórz drzewo filogenetyczne tych sekwencji korzystając z algorytmu Neighbor-Joining i metody boostrap (1000 replikacji).

1. Kiedy w toku ewolucji gen TNRC6 uległ duplikacjom?
2. Która z podrodzin genu (TNRC6A, TNRC6B, TNRC6C) zduplikowała pierwsza?
3. Czy na drzewie są duplikacje/delecje genu, które są specyficzne dla danego organizmu.
4. Które pary sekwencji są bliżej spokrewnione: ortologi TNRC6C człowieka i szympansa czy paralogi TNRC6C kury?


### Zad. 12 (Identyfikacja genu RBP3 u kręgowców)
Gen białka wiążącego retinoid (**RBP3**) jest dobrze zachowany u kręgowców. Poniżej znajduje się białko kodowone przez ten gen u człowieka:

```
>gi|4506453|ref|NP_002891.1| retinol-binding protein 3 precursor [Homo sapiens]
MMREWVLLMSVLLCGLAGPTHLFQPSLVLDMAKVLLDNYCFPENLLGMQEAIQQAIKSHEILSISDPQTL
ASVLTAGVQSSLNDPRLVISYEPSTPEPPPQVPALTSLSEEELLAWLQRGLRHEVLEGNVGYLRVDSVPG
QEVLSMMGEFLVAHVWGNLMGTSALVLDLRHCTGGQVSGIPYIISYLHPGNTILHVDTIYNRPSNTTTEI
WTLPQVLGERYGADKDVVVLTSSQTRGVAEDIAHILKQMRRAIVVGERTGGGALDLRKLRIGESDFFFTV
PVSRSLGPLGGGSQTWEGSGVLPCVGTPAEQALEKALAILTLRSALPGVVHCLQEVLKDYYTLVDRVPTL
LQHLASMDFSTVVSEEDLVTKLNAGLQAASEDPRLLVRAIGPTETPSWPAPDAAAEDSPGVAPELPEDEA
IRQALVDSVFQVSVLPGNVGYLRFDSFADASVLGVLAPYVLRQVWEPLQDTEHLIMDLRHNPGGPSSAVP
LLLSYFQGPEAGPVHLFTTYDRRTNITQEHFSHMELPGPRYSTQRGVYLLTSHRTATAAEEFAFLMQSLG
WATLVGEITAGNLLHTRTVPLLDTPEGSLALTVPVLTFIDNHGEAWLGGGVVPDAIVLAEEALDKAQEVL
EFHQSLGALVEGTGHLLEAHYARPEVVGQTSALLRAKLAQGAYRTAVDLESLASQLTADLQEVSGDHRLL
VFHSPGELVVEEAPPPPPAVPSPEELTYLIEALFKTEVLPGQLGYLRFDAMAELETVKAVGPQLVRLVWQ
QLVDTAALVIDLRYNPGSYSTAIPLLCSYFFEAEPRQHLYSVFDRATSKVTEVWTLPQVAGQRYGSHKDL
YILMSHTSGSAAEAFAHTMQDLQRATVIGEPTAGGALSVGIYQVGSSPLYASMPTQMAMSATTGKAWDLA
GVEPDITVPMSEALSIAQDIVALRAKVPTVLQTAGKLVADNYASAELGAKMATKLSGLQSRYSRVTSEVA
LAEILGADLQMLSGDPHLKAAHIPENAKDRIPGIVPMQIPSPEVFEELIKFSFHTNVLEDNIGYLRFDMF
GDGELLTQVSRLLVEHIWKKIMHTDAMIIDMRFNIGGPTSSIPILCSYFFDEGPPVLLDKIYSRPDDSVS
ELWTHAQVVGERYGSKKSMVILTSSVTAGTAEEFTYIMKRLGRALVIGEVTSGGCQPPQTYHVDDTNLYL
TIPTARSVGASDGSSWEGVGVTPHVVVPAEEALARAKEMLQHNQLRVKRSPGLQDHL
```

* Skorzystaj z programu NCBI BLAST w celu wyszukania aminokwasowych sekwencji RBP3 u innych organizmów. 
   * Wybierz bazę danych `RefSeq`.
   * Ogranicz wyszukiwania do kręgowców.
   * W opcjach algorytmu (`Algorithm parameters`) zwiększ maksymalną liczbę wynikowych sekwencji z `100` do `250`.
   * Uruchom program BLAST.
* Do dalszej analizy wybierz po jednym - najwyżej punktowanym - białku: 
   * człowieka,
   * szympansa (*Pan paniscus*),
   * makaka (*Macaca mulatta*),
   * szczura (*Rattus norvegicus*),
   * myszy (*Mus musculus*),
   * krowy (*Bos taurus*),
   * kury (*Gallus gallus*),
   * żaby (*Xenopus laevis*),
   * ryby Trzcinik (*Erpetoichthys calabaricus*).
* Zapisz wybrane sekwencje w formacie FASTA do pliku `vertebrares.fasta`.
* Utwórz drzewo filogenetyczne pobranych sekwencji (Neighbour-Joining, Bootstrap: 1000)

1. Które pary gatunków są bliżej ze sobą spokrewnione na filogramie: 
   * człowek z szympansem
   * mysz ze szczurem?
2. Czy uzyskane drzewo odpowiada aktualnie przyjętej systematyce kręgowców?
3. Zapisz uzyskane drzewo w formacie Newick i wklej jako odpowiedź w sprawozdaniu.