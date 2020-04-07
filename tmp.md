## Domeny białkowe

### Zad. 1 - Serwis Pfam (modele HMM)
> **Obejrzyj wprowadzenie do bazy Pfam: [YouTube](https://youtu.be/unExXijjMmI) [8min].**

Wykorzystaj serwis [Pfam](https://pfam.xfam.org) i zidentyfikuj domeny białkowe obecne w poniższej sekwencji: 

```
>sequence
NNRNQDNYVSWSDSEDDDEDEEIEEKEKPETNFPSPFTNILCGIIFVERRYTAVVLNRLI
KEAGKQDPELAYISSNFITGHGIGKNQPRNKQMEAEFRKQEEVLRKFRAHETNLLIATSI
VEEGVDIPKCNLVVRFDLPTEYRSYVQSKGRARAPISNYIMLADTDKIKSFEEDLKTYKA
IEKILRNKCSKSVDTGETDIDPVMDDDDVFPPYVLRPDDGGPRVTINTAIGHINRYCARL
PSDPFTHLAPKCRTRELPDGTFYSTLYLPINSPLRASIVGPPMSCVRLAERVVALICCEK
LHKIGELDDHLMPVGKETVKYEEELDLHDEEETSVPGRPGSTKRRQCYPKAIPECLRDSY
PRPDQPCYLYVIGMVLTTPLPDELNFRRRKLYPPEDTTRCFGILTAKPIPQIPHFPVYTR
SGEVTISIELKKSGFMLSLQMLELITRLHQYIFSHILRLEKPALEFKPTDADSAYCVLPL
NVVNDSSTLDIDFKFMEDIEKSEARIGIPSTKYTKETPFVFKLEDYQDAVIIPRYRNFDQ
PHRFYVADVYTDLTPLSKFPSPEYETFAEYYKTKYNLDLTNLNQPLLDVDHTSSRLNLLT
PRHLNQKGKALPLSSAEKRKAKWESLQNKQILVPELCAIHPIPASLWRKAVCLPSILYRL
HCLLTAEELRAQTASDAGVGVRSLPADFRYPNLDFGWKKSIDSKSFISISNSSSAENDNY
CKHSTIVPENAAHQGANRTSSLENHDQMSVNCRTLLSESPGKLHVEVSADLTAINGLSYN
QNLANGSYDLANRDFCQGNQLNYYKQEIPVQPTTSYSIQNLYSYENQPQPSDECTLLSNK
YLDGNANKSTSDGSPVMAVMPGTTDTIQVLKGRMDSEQSPSIGYSSRTLGPNPGLILQAL
TLSNASDGFNLERLEMLGDSFLKHAITTYLFCTYPDAHEGRLSYMRSKKVSNCNLYRLGK
KKGLPSRMVVSIFDPPVNWLPPGYVVNQDKSNTDKWEKDEMTKDCMLANGKLDEDYEEED
EEEESLMWRAPKEEADYEDDFLEYDQEHIRFIDNMLMGSGAFVKKISLSPFSTTDSAYEW
KMPKKSSLGSMPFSSDFEDFDYSSWDAMCYLDPSKAVEEDDFVVGFWNPSEENCGVDTGK
QSISYDLHTEQCIADKSIADCVEALLGCYLTSCGERAAQLFLCSLGLKVLPVIKRTDREK
ALCPTRENFNSQQKNLSVSCAAASVASSRSSVLKDSEYGCLKIPPRCMFDHPDADKTLNH
LISGFENFEKKINYRFKNKAYLLQAFTHASYHYNTITDCYQRLEFLGDAILDYLITKHLY
EDPRQHSPGVLTDLRSALVNNTIFASLAVKYDYHKYFKAVSPELFHVIDDFVQFQLEKNE
MQGMDSELRRSEEDEEKEEDIEVPKAMGDIFESLAGAIYMDSGMSLETVWQVYYPMMRPL
IEKFSANVPRSPVRELLEMEPETAKFSPAERTYDGKVRVTVEVVGKGKFKGVGRSYRIAK
SAAARRALRSLKANQPQVPNS
```

<img src="images/06-01-pfam1.png" alt="06-01-pfam1">

1. Ile w sumie domen i rodzin domen zostało zidentyfikowanych w analizowanej sekwencji?
2. W jakiej pozycji w sekwencji znajduje się domena `Dicer_dimer`?
   > Serwis Pfam przedstawia dwa typy koordynatów `start` i `end`. Pozycje start i end w kolumnie **Alignment** oznaczają region przyrównania sekwencji zapytania z modelem HMM (*Hidden Markov Model*) reprezentującym domenę. Z kolei, koordynaty **Envelope** wyznaczają region w sekwencji, który został dodatkowo probabilistycznie wyznaczony jako miejsce występowania domeny. Region **Envelope** jest zwykle kilka aminokwasów dłuższy niż region **Alignment** i wyznacza on prawdopodobne miejsce występowania domeny.
3. Podaj wartość `E-value` przyrównania domeny `Dicer_dimer` z modelem HMM.

Rozwiń dopasowanie domeny `Dicer_dimer` z modelem HMM z bazy Pfam (`Show`).

4. Podaj fragment sekwencji domeny o największym prawdopodobieństwie (zgodności) z modelem HMM.


#### Rekord domeny Dicer

Otwórz stronę rekordu domeny `Dicer_dimer`.

5. Podaj numer dostępu tej domeny w bazie Pfam.
6. Jaką funkcję pełni ta domena (krótko)?
7. Ile gatunków posiada tę domenę białkową?

Otwórz zakładkę `Species`.

8. Czy domena występuje u organizmów prokariotycznych?
9. W ilu gatunkach owadów występuje ta domena?

<img src="images/06-01-pfam2.png" alt="06-01-pfam2">

Będąc w zakladce `Species`, kliknij na kartę `Tree`.

10. Ile sekwencji białek człowieka posiada tę domenę?
11. Ile sekwencji białek człowiekowatych (*Hominidae*) posiada tę domenę. 
    * Podaj numery dostępu tych białek.

Otwórz zakładkę `HMM logo`.

12. Ile wynosi długość sekwencji domeny `Dicer_dimer`?
13. Jakie dwa aminokwasy są najbardziej zachowane w pozycji 8 sekwencji domeny?

Przejdź do zakładki `Domain organization`.

14. Podaj najczęściej występujący układ domen w białkach, w którym występuje domena `Dicer_domain`.

Użyj sekwencji zapytania w programie BLAST i przeszukaj bazę `RefSeq`.

15. Podaj numer dostępu i nazwa organizmu, z jakiego pochodzi sekwencja zapytania.
16. Jaką funkcję pełni to białko? 
    > Wskazówka: sekcja `COMMENT` rekordu w formacie GenBank.


### Zad. 2 - Serwis PROSITE (wzorce i profile sekwencyjne)
> **PROSITE** charakteryzuje funkcję białka oraz jego rodziny stosując jeden wzorzec konsensusowy. Wzorce sekwencji konsensusowe pochodzą z konserwatywnych regionów przyrównań sekwencji białkowych i  przedstawiane są w bazie PROSITE za pomocą wyrażeń regularnych. Informacje na temat funkcji tych wzorców pochodzą przede wszystkim z danych literaturowych. W celu przeszukania bazy badaną sekwencją PROSITE stosuje dokładne skojarzenie z wzorcem. Poza wyrażeniami regularnymi, w celu ich dopełnienia, serwis PROSITE tworzy także profile.


Użyj sekwencji z zad. 1 i serwisu [PROSITE](https://prosite.expasy.org/prosite.html) w celu identyfikacji domen białkowych. Umieść sekwencję w polu `Quick Scan mode of ScanProsite`. Naciśnij przycisk `Scan`.

<img src="images/06-02-prosite1.png" alt="06-02-prosite1">

1. Podaj nazwę domeny, której nie zidentyfikowano wcześniej w serwisie Pfam.
   * Jaką funkcję pełni ta domena?
2. Czy serwis PROSITE zidentyfikował jakieś wzorce sekwencyjne w sekwencji zapytania?
3. Podaj numer dostępu domeny typu *Dicer* w bazie PROSITE.
4. Czy lokalizacja domeny *Dicer* w sekwencji jest taka sama, jak w przewidywaniach Pfam?

#### Rekord domeny Dicer

Wejdź w rekord domeny Dicer w bazie PROSITE.

5. Podaj długość profilu domeny Dicer w bazie PROSITE.
6. Czy w logo domeny Dicer aminokwasy `Y` i `F` są najbardziej zachowanymi aminokwasami?
7. Wejdź w `Taxonomic distribution` domeny *Dicer*.
   * Czy domena występuje u organizmów prokariotycznych?


### Zad. 3 - Metaserwis InterPro (integracja wyników)
Użyj sekwencji z zad. 1 i serwisu [InterPro](http://www.ebi.ac.uk/interpro/) w celu identyfikacji domen białkowych.

1. Ile domen białkowych zidentyfikowano?
2. Podaj numer dostępu domeny typu Dicer.
3. Podaj lokalizacaję domeny Dicer w sekwencji.
4. W oparciu o jakie bazy danych domen białkowych, domena Dicer została zidentyfikowana?

#### Rekord domemy Dicer

Otwórz stronę rekordu domeny *Dicer* w bazie InterPro.

5. W ilu sekwencjach białkowych domena Dicer jest dostępna?
   > Ile z tych białek należy do *Eukaryota* i *Prokaryota*?
6. Ile jest różnych układów domen (`Domain architectures`), w których występuje domena Dicer?
7. Wymień szlaki biochemiczne, w które zaangażowana jest domena Dicer.


### Zad. 4 - Informacje o domenach w rekordach UniProt
Użyj programu BLAST na stronie serwisu [UniProt](https://www.uniprot.org/) w celu zidentyfikowania sekwencji białkowej z zadania 1.

1. Podaj numer dostępu oraz nazwę znalezionej sekwencji.

Otwórz rekord znalezionej sekwencji białkowej.

2. Czy w rekordzie UniProt zawarte są informacje o domenach występujących w tym białku?
<br/><br/>


### Zad. 5 - InterPro: hierarchiczne relacje między domenami
Korzystając z serwisu InterPro zidentyfikuj domeny białkowe w poniższej sekwencji:

```
>seq1
MELRVLLCWASLAAALEETLLNTKLETADLKWVTFPQVDGQWEELSGLDEEQHSVRTYEV
CDVQRAPGQAHWLRTGWVPRRGAVHVYATLRFTMLECLSLPRAGRSCKETFTVFYYESDA
DTATALTPAWMENPYIKVDTVAAEHLTRKRPGAEATGKVNVKTLRLGPLSKAGFYLAFQD
QGACMALLSLHLFYKKCAQLTVNLTRFPETVPRELVVPVAGSCVVDAVPAPGPSPSLYCR
EDGQWAEQPVTGCSCAPGFEAAEGNTKCRACAQGTFKPLSGEGSCQPCPANSHSNTIGSA
VCQCRVGYFRARTDPRGAPCTTPPSAPRSVVSRLNGSSLHLEWSAPLESGGREDLTYALR
CRECRPGGSCAPCGGDLTFDPGPRDLVEPWVVVRGLRPDFTYTFEVTALNGVSSLATGPV
PFEPVNVTTDREVPPAVSDIRVTRSSPSSLSLAWAVPRAPSGAVLDYEVKYHEKGAEGPS
SVRFLKTSENRAELRGLKRGASYLVQVRARSEAGYGPFGQEHHSQTQLDESEGWREQLAL
IAGTAVVGVVLVLVVIVVAVLCLRKQSNGREAEYSDKHGQYLIGHGTKVYIDPFTYEDPN
EAVREFAKEIDVSYVKIEEVIGAGEFGEVCRGRLKAPGKKESCVAIKTLKGGYTERQRRE
FLSEASIMGQFEHPNIIRLEGVVTNSMPVMILTEFMENGALDSFLRLNDGQFTVIQLVGM
LRGIASGMRYLAEMSYVHRDLAARNILVNSNLVCKVSDFGLSRFLEENSSDPTYTSSLGG
KIPIRWTAPEAIAFRKFTSASDAWSYGIVMWEVMSFGERPYWDMSNQDVINAIEQDYRLP
PPPDCPTSLHQLMLDCWQKDRNARPRFPQVVSALDKMIRNPASLKIVARENGGASHPLLD
QRQPHYSAFGSVGEWLRAIKMGRYEESFAAAGFGSFELVSQISAEDLLRIGVTLAGHQKK
ILASVQHMKSQAKPGTPGGTGGPAPQY
```

1. Do jakiej rodziny białkowej zostało zaklasyfikowane to białko?
2. Ile domen białkowych zostało zidentyfikowanych w sekwencji zapytania?
3. Podaj lokalizację domeny kinazowej `Protein kinase domain (IPR000719)`.
4. Czy domena kinazowa zawiera miejsce wiązanie ATP i centrum aktywne?

Wejdź do rekordu domeny kinazowej `IPR000719`.

5. Wymień bazy domen, na podstawie których tworzony jest ten rekord w bazie InterPro (`Contributing signatures`).
6. Czy w obrębie domeny kinazowej można wyróżnić bardziej specyficzne domeny kinazowe? (`Domain relationships`)
7. Podaj nazwę nadrodziny, w skład której wchodzi domena kinazowa.
<br/><br/>


### Zad. 6 - InterPro: mutacja w obrębie domeny
Poniżej znajduje się sekwencja białkowa `seq2` odpowiadająca sekwencji `seq1` z poprzedniego zadania, lecz pochodzi od pacjenta chorującego na pewne schorzenie.

```
>seq2
MELRVLLCWASLAAALEETLLNTKLETADLKWVTFPQVDGQWEELSGLDEEQHSVRTYEV
CDVQRAPGQAHWLRTGWVPRRGAVHVYATLRFTMLECLSLPRAGRSCKETFTVFYYESDA
DTATALTPAWMENPYIKVDTVAAEHLTRKRPGAEATGKVNVKTLRLGPLSKAGFYLAFQD
QGACMALLSLHLFYKKCAQLTVNLTRFPETVPRELVVPVAGSCVVDAVPAPGPSPSLYCR
EDGQWAEQPVTGCSCAPGFEAAEGNTKCRACAQGTFKPLSGEGSCQPCPANSHSNTIGSA
VCQCRVGYFRARTDPRGAPCTTPPSAPRSVVSRLNGSSLHLEWSAPLESGGREDLTYALR
CRECRPGGSCAPCGGDLTFDPGPRDLVEPWVVVRGLRPDFTYTFEVTALNGVSSLATGPV
PFEPVNVTTDREVPPAVSDIRVTRSSPSSLSLAWAVPRAPSGAVLDYEVKYHEKGAEGPS
SVRFLKTSENRAELRGLKRGASYLVQVRARSEAGYGPFGQEHHSQTQLDESEGWREQLAL
IAGTAVVGVVLVLVVIVVAVLCLRKQSNGREAEYSDKHGQYLIGHGTKVYIDPFTYEDPN
EAVREFAKEIDVSYVKIEEVIGAGEFGEVCRGRLKAPGKKESCVAISTLKGGYTERQRRE
FLSEASIMGQFEHPNIIRLEGVVTNSMPVMILTEFMENGALDSFLRLNDGQFTVIQLVGM
LRGIASGMRYLAEMSYVHRDLAARNILVNSNLVCKVSDFGLSRFLEENSSDPTYTSSLGG
KIPIRWTAPEAIAFRKFTSASDAWSYGIVMWEVMSFGERPYWDMSNQDVINAIEQDYRLP
PPPDCPTSLHQLMLDCWQKDRNARPRFPQVVSALDKMIRNPASLKIVARENGGASHPLLD
QRQPHYSAFGSVGEWLRAIKMGRYEESFAAAGFGSFELVSQISAEDLLRIGVTLAGHQKK
ILASVQHMKSQAKPGTPGGTGGPAPQY
```

Przeprowadź globalne przyrównanie obu sekwencji. 

1. Jakie zmiany w sekwencji tego białka występują u chorego pacjenta?

Przeanalizuj białko pacjenta przy użyciu serwisu InterPro i porównaj z wynikami dla sekwencji osoby zdrowej. 

2. W obrębie, której domeny doszło do mutacji u pacjenta?


### Zad. 7 - InterPro: wszystkie białka zawierające domenę RRM
Otwórz stronę serwisu [InterPro](https://www.ebi.ac.uk/interpro/). W polu szybkiego wyszukiwania po prawej stronie wyszukaj domenę RRM (*RNA recognition motif domain*).

1. Podaj numer dostępu tej domeny.
2. Podaj liczbę białek zawierających domenę RRM u bakterii.


### Zad. 8 - UniProt: wszystkie białka zawierające domenę RRM
W bazie UniProt wyszukaj wszystkie białka zawierające domenę RRM u bakterii. 

1. Podaj użyte zapytanie do bazy UniProt.
2. Ile białek otrzymano?


## Identyfikacja nowych motywów/domen białkowych


### Zad. 6
W pliku [sequences.fasta](./data/sequences.fasta) znajduje się 6 sekwencji białkowych, które pełnią podobną funkcję. Twoim zadaniem jest znalezienie motywów sekwencji wspólnych dla tych sekwencji.

Użyj serwisu [MEME](http://meme-suite.org) i wybierz `Motif Discvovery` > `MEME`. W formularzu, w sekcji `Select the site distribution` wybierz opcję `Any number of repetitions`. Wklej sekwencje lub załaduj je z pliku i rozpocznij analizę.

1. Ile motywów znaleziono?
2. Które motywy są obecne we wszystkich 6 sekwencjach?
3. Sprawdź w serwisie Pfam, czy zidentyfikowane motywy odpowiadają znanym już domenom białkowym.
4. Jaką funkcję pełnią te motywy?


## Ontologia genów


### Zad. 7
W bazie `Gene` serwisu NCBI wyszukaj gen człowieka o nazwie *CASP6*.

1. Podaj pełną nazwę tego genu.
2. W oparciu o informacje zaware w panelu `General gene information` wymień dwa przykładowe opisy dla każdego z trzech działów ontologicznych:
   * funkcji komórkowej
   * procesu biologicznego
   * komponentu komórkowego
3. O czym informują trzyliterowe kody znajdujące się w kolumnie `Evidence Code`?
4. Na stronie rekordu odszukaj identyfikator bazy UniProt kodowanego przez ten gen białka i przejdź do rekordu UniProt. Czy w rekordzie UniProt również znajdują się informacje na temat ontologii tego genu?


### Zad. 8
> Celem tego zadania jest wyszukanie wszystkich genów człowieka (nie tylko *CASP6*) zaangażowanych w proces zaprogramowanej śmierci komórki (*programmed cell death*, PCD).

W serwisie [Gene Ontology](http://amigo.geneontology.org/amigo/), w polu wyszukiwania (`Quick search`) wpisz frazę `programmed cell death` i z listy autouzupełnień wybierz rekord odpowiadający temu procesowi.

1. Podaj numer dostępu procesu PCD.
2. Jak przebiega proces PCD (jednym zdaniem)?
3. Przejdź do zakładki `Inferred Tree View`. Czy PCD jest tym samym, czym apoptoza?
4. Wymień 3 procesy wchodzące w skład PCD.
5. Podaj nazwę i numer dostępu procesu, który jest nadrzędny dla PCD.

Przejdź do zakładki `Annotations`. 

6. Ile jest genów/białek, które biorą udział w PCD?
7. Skorzystaj z filtrów (`Filter results`) i ogranicz liczbę wyników do ludzkich białek pochodzące z bazy UniProt. 
   - Ile rekordów znaleziono?
8. Ogranicz listę wyników otrzymaną w pkt. 7 do białek, których funkcja PCD została przypisana na podstawie doświadczeń laboratoryjnych.
   - Ile rekordów znaleziono?
9. Z listy wyników wybierz dowolne białko i przejdź do rekordu w bazie UniProt. Jaki jest numer dostępu tego białka?
10. W opraciu o informajce zawarte w rekordzie UniProt odpowiedz, czy białko bierze udział w procesach biologicznych innych niż PCD?


## Metody alignment-free


### Zad. 9 (zadanie domowe)
Przeczytaj [artykuł przeglądowy](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-017-1319-7) na temat metody porównywania sekwencji typu "alignment-free".


### Zad. 10*
Utwórz skrypt, który dla sekwencji FASTA podanych przez użytkownika w pliku obliczy Normalized Compression Distance (NCD) [rys. 2 w artykule] między każdą parą sekwencji w pliku. Jako formę kompresji do obliczania NCD użyj metodę Lempel-Ziv.

Przykład kompresji Lempel-Ziv dla poniższej sekwencji `x`:

```
AABABBBABAABABBBABBABB
```

Rozpoczynamy czytanie sekwencji z lewej strony. Znajdujemy najkrótszą podsekwencję, której nie spotkaliśmy wcześniej. To zawsze będzie pojedyncza litera, w tym przypadku `A`:

```
A|ABABBBABAABABBBABBABB
```

Następnie wybieramy kolejną podsekwencję, której nie widzieliśmy. Ponieważ widzieliśmy już `A`, wybieramy `AB`:

```
A|AB|ABBBABAABABBBABBABB
```

Następną podsekwencją, której nie widzieliśmy jest `ABB`, ponieważ widzieliśmy już `AB`.

```
A|AB|ABB|BABAABABBBABBABB
```

Kontynuując, następną podsekwencją będzie pojedyncza litera `B`. Otrzymujemy:

```
A|AB|ABB|B|ABAABABBBABBABB
```

Dalsza część sekwencji zostanie podzielona w poniższy sposób:

```
A|AB|ABB|B|ABA|ABAB|BB|ABBA|BB
```

Ponieważ nie ma więcej liter w sekwencji wejściowej, podsekwencja `BB` zostaje powtórzona.

Złożoność Lempel-Ziv jest liczbą przedziałów, które wyznaczyliśmy.

```
c(x) = 9
```