# getMito
Wiki page: https://github.com/shenjean/getMito/wiki

```
Usage: getMito.py [OPTIONS]

From a user-provided list of fish taxonomic names, getMito extracts available mitochondrial information and
FASTA file (optional) at various taxonomic levels. 
The reference database is prepared from the MitoFish database and NCBI (Jul 2020 update).

Options:
  -i, --input_file TEXT           Input query file (e.g. input.txt) [required]
  -o, --output_prefix TEXT        Output prefix (e.g. OUT)  [required]
  -d, --database_file TEXT        Database file (e.g. mitofish.all.Jul2020.tsv) [required]
  -l, --tax_level [1|2|3|4|5|6|7] The taxonomic level of the search (e.g. 7 for speecies search, 6 for genus search)
  --fasta / --no-fasta            Generate FASTA file containing sequences of all matching hits (default=FALSE)
  --help                          Show this message and exit.

Dependencies: Python3 and the conda- and pip-installable click package
```

Download getMito reference database file here: [mitofish.all.Jul2020.tsv](https://drive.google.com/uc?export=download&id=1C1vzqBpC7jsDfgyepbYS2vqDGBYf3rwY) (639,987 records; Jul 2020 update)


Input file example: 
```
Histioteuthis celetaria celetaria
Histioteuthis corona corona
Stomias boa boa
Lampadena urophaos atlantica
```
Screen output example:
```
=== Searching query #1: <aa> ===
Search string:Myctophidae       Taxonomic level:L5      Hits:2746
=== Searching query #2: <Abraliopsis pfefferi> ===
=== Searching query #3: <#> ===
ERROR: Query is too short (<2 characters)! Skipping search...
=== Searching query #4: <Ahliesaurus berryi> ===
Search string:Notosudidae       Taxonomic level:L5      Hits:55
```
Output file example:
```
Query   Accession       Gene definition txid    Superkingdom    Phylum  Class   Order   Family  Genus   Species Sequence
Myctophidae     AB024912        Hygophum benoiti mitochondrial gene for 16S rRNA, partial sequence      89987   Eukaryota       Chordata        Actinopter
i       Myctophiformes  Myctophidae     Hygophum        Hygophum benoiti        TTTAGCAAGTACCCCCTGAGCAAAGAGCCCTTCAGTTCAGCACCCCGAAACTAGACGAGCTACTTCAAGACAGC
CTGTTTAACAAACATGTAGGGCACACCCATATCTGTTGCAAAAGATTGGGAAGATCTTCAAGTAGAGGTGACAAGCCTACCGAGCCTAGTTATAGCTGGTTGTCTGAGAAATGAATATAAGTTCAGCCCCCTGATTTCCCCCATCAAGAGCACC
AATGCCCTCAAAGATCAAACAAAAATCAAGGGAGTTAGCCAGAGGGGGTACAGCCCCTCTGGAAAAGGACACAACCTCAACGGAAGACCAAAGATCAAACCAACTAAGGAACTTTATTTTAGTGGGCCCGGAAGCAGCCACCTAAGAAGAAAGC
GTTACAGCTCCCATATAGCTCCACCCCCTGATCTCGAACCCCTCTCTTCAATCTCCCCTCACTATCAGACCCTCCCACTAGTCCTGGGAAAGATTATGCTAAAATGAGTAATAAGAGGGTGCGCCCCTCTCCACCACACATGTATAAGTCGGAA
CGGACCAACCGCCGATAACTAACGACCCCTGCAGAGAGTAGTGTACTGCCGCACAAATAGCAAGAAAGCCAAACACATAAAATCGTTAACCCAACACAGGTGTGTGCCCCCGGAAAGACTAAAACAAAGGGAAGGAACTCGGCAAACAAAAGCC
TCGCCTGTTTACCAAAAACATCGCCTCTTGCAAAATTCACGAATAAGAGGTCCCGCCTGCCCAGTGACAGTGTTTAACGGCCGCGGTATTTTGACCGTGCAAAGGTAGCACAATAAATTGTCTCTTAATTGGAGAACGGTATGAATGGCATCAC
GAGGGCTTAACTGTCTCCCCTCTAAAGTCAATGAAATTGATCTCCCCGTGCAGAAGCGGGGATACACTCGTAAGACGAGAAGACCCTATGGAGCTTTAGACATAAGCCAGCCCACGTCAAACGCCCCTAATAAAGGAAATGAACAAAATGGCCC
CTGATGGTATGTCTTCGGTTGGGGCGACCACGGAGAAAGACAAAACCTCCACATGGACTGGGGCTACTACGCCCTAAAACACAGACCCACAGGTCAAATAAACAGTACATCTGACCATAAAAGAGCCGGCATAAGCCGATCAATGGACCAAGTT
ACCCTAGGGATAACAGCGCAATCCTCTCAAAGAGACCATATCGACGAGGGGGTTTACGACCTCGATGTTGGATCAGGACATCCTAATGGTGCAGCCGCTATTAAGG
Myctophidae     AB024913        Hygophum proximum mitochondrial gene for 16S rRNA, partial sequence     89988   Eukaryota       Chordata        Actinopter
i       Myctophiformes  Myctophidae     Hygophum        Hygophum proximum       TACCTTTTGCATCATGATTTAGCAAGTACCCCTGAGCAAAGAGTACTTCAGTTCAGCGCCCCGAAACTAGACGA
GCTACTTCAAGACAGCCTTTATTATATATACGTAGGGCACACCCGTCTCTGTTGCAAAAGAGTGGGAAGATCTTCAAGTAGGGGTGACAAGCCTACCGAGCCTAGTTTTAGCTGGTTGTCTGAGAAGTGTATATAAGTTCAGCCTCCTGATTTT
ACCAGTCGAAAGCACCTATGCCCCCAAAGACCAAGTGAATTTCAGGAGAGTTAGTCAAGCGGGGTACAGCCCGCCTGAAAAAGGATACAACCTCTATGGAAGATTAAAGATCATACCAAATAAGGAACTTTACTTTAGTGGGCTTAAAAGCAGC
CACCTACAAAGAAAGCGTTACAGCTCCTGTTTAATTTCACCCGCTAATACCGAACCCCGCCTCTTTAGTCCCCCACACTATCAGACCCTCCCACCCACCCTGGGAGAGATAATGCTAAAATGAGTAATAAGAGGGCGCGCCCCTCTCCAACACA
CATGTTTATGTCGGAACGGACCCACCACCGACAATTAACGACCTCTACAGAGAGCAATGTACCACCGCACAAATAGCAAGAAAATCGAACACCTCATGCTCGTTAACCCAACACAGGTGTGTGACCCTGGAAAGACTAAAATAAAGGGAAGGAA
CTCGGCAAACACAAGCCTCGCCTGTTTACCAAAAACATCGCCTCTTGCAATATTACGAATAAGAGGTCCCGCCTGCCCAGTGACGCTGTTTAACGGCCGCGGTATTTTGACCGTGCAAAGGTAGCGCAATAAATTGTCTCTTAATTGGAGACTA
GTATGAATGGCACCACGAGGGCTTAACTGTCTCCCCTCTAAAGTCAATGAAATTGATCTCCCCGTGCAGAAGCGGGGATACGCTCGTAAGACGAGAAGACCCTTTGGAGCTTTAGACACAAGGGCAGCCCAGGTCAAACACCCCCAAAAGGAAC
TGAACCCCATGAACCACTGCCAATCTGTCTTCGGTTGGGGCGACCACGGAGAAAAACAAAACCTCCACATGGAGTGGGGCCACTCGGCCCTAAAGAACAGACCCACAGGTCTAACCCGCAGAACATCTGACCACAAAGAACCGGCACAAGCCGC
TCAATGGACCAAGTTACCCTAGGGATAACAGCGCAATCCCCTCAAAGAGACCTTATCGACGAGAGGGTTTACGACCTCGATGTTGGATCAGGACATCCTAATGGTGCAGCCGCTATTAAGGGTTCG
```
