## Dot plot

### Zad. 1
> **Przypomnij sobie technikę porównywania sekwencji dot-plot w oparciu o [naszą prezentację](http://combio.pl/courses/bioseq.amupie/?lecture=6) (slajdy: 39-68) [ok. 10 min].**

Korzystając z techniki dot-plot porównaj sześć par sekwencji DNA w pliku [dotplot.xlsx](http://www.combio.pl/files/dotplot.xlsx). Zinterpretuj każdy z sześciu otrzymanych wykresów dot-plot (a-f) pod kątem: 
* zgodności/niezgodności sekwencji,
* insercji
* sekwencji powtórzonych i palindromowych. 

Wypełniony arkusz dołącz do sprawozdania.


## Przyrównanie sekwencji - podstawowe informacje

### Zad. 2 - Sekwencje DNA
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
   > Długość przyrównania obejmuje wszystkie znaki w przyrównania (w tym przerwy `-`).
2. Na ilu pozycjach przyrównania nukleotydy są:
   * zgodne/dopasowane (*match*)
   * niezgodne/niedopasowane (*mismatch*)?
3. Ile wynosi procent identyczności przyrównanych sekwencji?
   > **Procent identyczności** = liczba identycznych nukleotydów / długość przyrównania * 100
4. Ile wynosi wartość punktacji (*score*) przyrównania sekwencji? Przyjmij poniższy system punktacji:
   * elementy zgodne (*match*): `2`
   * elementy niezgodne (*mismatch*): `-1`
   * przerwa (*gap*): `-2`


### Zad. 3 - Sekwencje białkowe
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


## Programowanie dynamiczne (materiały z ostatniego wykładu)


### Zad. 4 - Przyrównanie globalne
> **Przypomnij sobie jak działa algorytm Needlemana-Wunscha służący do globalnego przyrównania dwóch sekwencji: [YouTube](https://youtu.be/BYdTqq8AGgc) [5min18sek].**

Wykonaj na kartce przyrównanie globalne dwóch sekwencji DNA, `ATG` i `GGAATGG`, przy pomocy **algorytmu Needlemana-Wunscha**. 

Przyjmij system punktacji: 

* dopasowanie/zgodność (*match*): `+3`
* niedopasowanie/niezgodność (*mismatch*): `-1`
* kara za przerwę (*gap penalty*): `-2`

W odpowiedzi podaj uzyskane dopasowania oraz wartość ich punktacji (*score*).


### Zad. 5 - Przyrównanie lokalne
> **Przypomnij sobie jak działasię algorytm Smitha-Watermana służący do lokalnego przyrównania dwóch sekwencji: [YouTube](https://youtu.be/F1YId_z4pc8) [2min18sec]**

Wykonaj przyrównanie lokalne sekwencji z poprzedniego zadania (ten sam system punktacji) przy pomocy **algorytmu Smitha-Watermana**. W odpowiedzi podaj uzyskane dopasowanie oraz wartość jego punktacji.



## Programy needle i water


### Zad. 6 - Przyrównanie lokalne i globalne sekwencji DNA
Poniżej znajduje się sekwencja genomowa genu insuliny ponocnicny trójpręgowej oraz sekwencja kodująca tego genu (*CDS*, *coding sequence*). 

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

Korzystając z internetowej wersji programów **needle** i **water** (<a href="http://www.ebi.ac.uk/Tools/psa/">http://www.ebi.ac.uk/Tools/psa/</a>) wykonaj - w dwóch kartach przeglądarki - przyrównanie powyższych sekwencji. Ustaw typ porównywanych sekwencji (*Enter a pair of*) jako DNA. Umieść pierwszą sekwencję w formacie FASTA w pierwszym oknie i drugą sekwencję w drugim oknie. Wykonaj przyrównanie.

1. Z ilu egzonów składa się badany gen insuliny?
   > Pełnej długości sekwencja CDS została rozłożona na kilka fragmentów znajdujących się w różnych miejscach w sekwencji genomowej. Te fragmenty odpowiadają egzonom genu.
2. Podaj pozycję początku i końca egzonów w sekwencji genomowej.
3. Dlaczego procent identyczności przyrównania w programie needle jest niższy niż w water?


### Zad. 7 - Przyrównanie lokalne i globalne sekwencji aminokwasowych
W bazie UniProt znajdź rekord acylfosfatazy u: człowieka (ID: `P14621`), *Escherichia coli* (ID: `P0AB65`) oraz *Salmonella sp.* (ID: `A0A1F2J9N6`). Wykorzystując program needle wykonaj przyrównanie następujących par sekwencji:

Organizm 1 | Organizm 2
--- | ---
*Escherichia coli* | *Salmonella sp.*
*Escherichia coli* | człowiek

1. Które przyrównanie odznacza się wyższym poziomem podobieństwa sekwencji i ile wynosi?
2. Podaj kilkuaminokwasowy fragment sekwencji najbardziej zachowany w trzech analizowanych sekwencjach.
    * Jaka może być przyczyna zachowania tego fragmentu sekwencji?
    > Wskzówka: Acylfosfataza jest enzymem. Jak nazywa się region, który bezpośrednio wiąże się i oddziałuje z substratem oraz zawiera kluczowe do przebiegu reakcji reszty aminokwasowe, 
3. Jaka macierz substytucji aminokwasowych została użyta w tych przyrównaniach?


## Wpływ parametrów na przyrównanie sekwencji


### Zad. 8 - Wpływ kary za stosowanie przerw
Poniżej znajdują się dwie sekwencje proteazy serynowych. Pierwsza sekwencja jest termostabilną proteazą pochodzącą z *Bacillus lentus*. Druga sekwencja jest peptydazą człowieka (tripeptydylo-peptydaza). Przyrównaj obie sekwencje programem *Water*.

```
>P29600 SUBS_BACLE Subtilisin Savinase - Bacillus lentus
AQSVPWGISRVQAPAAHNRGLTGSGVKVAVLDTGISTHPDLNIRGGASFVPGEPSTQDGN
GHGTHVAGTIAALNNSIGVLGVAPSAELYAVKVLGASGSGSVSSIAQGLEWAGNNGMHVA
NLSLGSPSPSATLEQAVNSATSRGVLVVAASGNSGAGSISYPARYANAMAVGATDQNNNR
ASFSQYGAGLDIVAPGVNVQSTYPGSTYASLNGTSMATPHVAGAAALVKQKNPSWSNVQI
RNHLKNTATSLGSTNLYGSGLVNAEAATR

>P29144 TPP2_HUMAN Tripeptidyl-peptidase 2 
MATAATEEPFPFHGLLPKKETGAASFLCRYPEYDGRGVLIAVLDTGVDPGAPGMQVTTDG
KPKIVDIIDTTGSGDVNTATEVEPKDGEIVGLSGRVLKIPASWTNPSGKYHIGIKNGYDF
YPKALKERIQKERKEKIWDPVHRVALAEACRKQEEFDVANNGSSQANKLIKEELQSQVEL
LNSFEKKYSDPGPVYDCLVWHDGEVWRACIDSNEDGDLSKSTVLRNYKEAQEYGSFGTAE
MLNYSVNIYDDGNLLSIVTSGGAHGTHVASIAAGHFPEEPERNGVAPGAQILSIKIGDTR
LSTMETGTGLIRAMIEVINHKCDLVNYSYGEATHWPNSGRICEVINEAVWKHNIIYVSSA
GNNGPCLSTVGCPGGTTSSVIGVGAYVSPDMMVAEYSLREKLPANQYTWSSRGPSADGAL
GVSISAPGGAIASVPNWTLRGTQLMNGTSMSSPNACGGIALILSGLKANNIDYTVHSVRR
ALENTAVKADNIEVFAQGHGIIQVDKAYDYLVQNTSFANKLGFTVTVGNNRGIYLRDPVQ
VAAPSDHGVGIEPVFPENTENSEKISLQLHLALTSNSSWVQCPSHLELMNQCRHINIRVD
PRGLREGLHYTEVCGYDIASPNAGPLFRVPITAVIAAKVNESSHYDLAFTDVHFKPGQIR
RHFIEVPEGATWAEVTVCSCSSEVSAKFVLHAVQLVKQRAYRSHEFYKFCSLPEKGTLTE
AFPVLGGKAIEFCIARWWASLSDVNIDYTISFHGIVCTAPQLNIHASEGINRFDVQSSLK
YEDLAPCITLKNWVQTLRPVSAKTKPLGSRDVLPNNRQLYEMVLTYNFHQPKSGEVTPSC
PLLCELLYESEFDSQLWIIFDQNKRQMGSGDAYPHQYSLKLEKGDYTIRLQIRHEQISDL
ERLKDLPFIVSHRLSNTLSLDIHENHSFALLGKKKSSNLTLPPKYNQPFFVTSLPDDKIP
KGAGPGCYLAGSLTLSKTELGKKADVIPVHYYLIPPPTKTKNGSKDKEKDSEKEKDLKEE
FTEALRDLKIQWMTKLDSSDIYNELKETYPNYLPLYVARLHQLDAEKERMKRLNEIVDAA
NAVISHIDQTALAVYIAMKTDPRPDAATIKNDMDKQKSTLVDALCRKGCALADHLLHTQA
QDGAISTDAEGKEEEGESPLDSLAETFWETTKWTDLFDNKVLTFAYKHALVNKMYGRGLK
FATKLVEEKPTKENWKNCIQLMKLLGWTHCASFTENWLPIMYPPDYCVF
```

1. Ponownie przyrównaj te sekwencje programem *water*, tym razem zmniejszając karę za otwarcie przerwy = `1`. 
   * W jaki sposób zmniejszenie kar za otwarcie przerw wpłynęło na to dopasowanie?
2. Wykonaj przyrównanie jak w poprzednim punkcie zwiększając kary za stosowanie przerw: otwarcie przerwy = `25`, wydłużenie przerwy = `5`.
   * W jaki sposób zwiększenie kar za stosowanie przerw wpłynęło na to dopasowanie?
3. Jak nazywa się model karania za przerwy przyjmujący dwa parametry: otwarcie i wydłużenie przerwy?
   > Wyróżniamy trzy podstawowe modele kary za przerwę: stały (*Constant*), liniowy (*Linear*) i afiniczny (*Affine*) [[Wikipedia](https://en.wikipedia.org/wiki/Gap_penalty#Types)].
4. Jak nazywa się model karania za przerwy, który używałe/aś w zadaniach 2-5?


### Zad. 9 - Wpływ kary za stosowanie przerwy na początku i końcu sekwencji
Otwórz program *needle* w dwóch kartach przeglądarki internetowej. W jednej karcie wykonaj przyrównanie sekwencji z poprzedniego zadania. W drugiej karcie wykonaj przyrównanie tych samych sekwencji wybierając w ustawieniach (*More Options*) opcję `END GAP PENALTY` jako `True`.

1. Na czym polega różnica między dwoma otrzymanymi przyrównaniami?
2. Które z przyrównań nazwał(a)byś *semi-globalnym*?


### Zad. 10 - Wpływ macierzy substytucji
> **Zapoznaj się z podstawowymi informacjami na temat macierzy substytucji: [YouTube](https://youtu.be/PdyARRNwi7I) [od 50’ do 57’ + od 1h09’ do 1h15’] [Slajdy z wykładu](http://combio.pl/courses/bioseq.amupie/?lecture=7).**

Z bazy UniProt wyszukaj sekwencje aminokwasowe globin `CTT-Z` i `CTT-VIIA` z *Chironomus thummi thummi*. Użyj programu **needle** i wykonaj przyrównanie sekwencji stosują macierze substytucji: `EBLOSUM30` ([macierz](ftp://ftp.ncbi.nlm.nih.gov/blast/matrices/BLOSUM30)), `EBLOSUM62` ([macierz](ftp://ftp.ncbi.nlm.nih.gov/blast/matrices/BLOSUM62)), `EBLOSUM90` ([macierz](ftp://ftp.ncbi.nlm.nih.gov/blast/matrices/BLOSUM30)). Zapisz wynik każdego dopasowania. 

Odpowiedz na pytania:

1. Dlaczego procent podobieństwa sekwencji jest niższy przy użyciu macierzy przeznaczonych dla blisko spokrewnionych sekwencji?
2. Dlaczego w przyrównaniach wykonanych przy użyciu macierzy `EBLOSUM90` występuje więcej insercji/delecji mimo, że kara za przerwę nie ulega zmianie a obie sekwencje mają zbliżoną długości (`161` i `163` aminokwasy)?
3. Które z przyrównań - Twoim zdaniem - tłumaczy w najbardziej prawdopodobny sposób zmiany, jakie wystąpiły w obu sekwencjach?