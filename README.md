# The influence of Machine Translation systems in the target language: News Translations from English into Spanish

In the github we collect the materials used for our Final Project of the course Machine Translation and Multilingualism.

## Corpora

For this project we have used the News Commentary v16 parallel corpus in its' English-Spanish version. This corpus is available in [Open Corpus](https://opus.nlpl.eu/News-Commentary.php). It is 
a parallel corpus of translated news and it includes a total of 16 languages. This corpus was downloaded in TMX format and aligned into a CSV using XBench.

We translated this corpus using the [facebook/nllb-200-distilled-600M](https://huggingface.co/facebook/nllb-200-distilled-600M) model available in Huggingface.

This way we have obtained a CSV containing on one column the source English version and in two other columns the original Spanish translation and the Machine Translated version of the text. This is available [here](https://github.com/cristinaa23/MT_assignment/tree/main/Translated%20Corpus).

## Extraction of the patterns
We have extracted three different patterns that could potentially change due to the extensive use of MT systems: 1) lexical borrowings, 2) verb+preposition collocations and 3) adverbs ending in -ly that are directly translated as -mente.

### Lexical Borrowings

For the extraction of lexical borrowings we have used the [mBERT Lázaro model available in Huggingface](https://huggingface.co/lirondos/anglicisms-spanish-mbert), which is a model trained to detect lexical anglicisms in Spanish newswire (Álvarez-Mellado et al., 2022).

Since the model tends to give false positives, we cleaned the results manually. We present the script we used to do the first manual extraction along with the final clean annotated CSV [here](https://github.com/cristinaa23/MT_assignment/tree/main/Extraction%20of%20Borrowings).

### Incorrect verb + preposition collocations
For extracting verb-preposition collocations we have using bigrams that followed the VERB-ADP pattern. We provide the corresponding code and results in the folder [VERB-PREP-Bigrams](https://github.com/cristinaa23/MT_assignment/tree/main/VERB-ADV-Bigrams).

### Literal Translation of Adverbs
For extracting adverbs ending in -ly that have been directly translated as adverbs ending in -mente in Spanish we have used our own python scripts. We provide the corresponding code and obtained output in the folder [Extraction-ADV](https://github.com/cristinaa23/MT_assignment/tree/main/Extraction-ADV).

## References
@inproceedings{alvarez-mellado-lignos-2022-detecting,
    title = "Detecting Unassimilated Borrowings in {S}panish: {A}n Annotated Corpus and Approaches to Modeling",
    author = "{\'A}lvarez-Mellado, Elena  and
      Lignos, Constantine",
    booktitle = "Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = may,
    year = "2022",
    address = "Dublin, Ireland",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.acl-long.268",
    pages = "3868--3888",
    abstract = "This work presents a new resource for borrowing identification and analyzes the performance and errors of several models on this task. We introduce a new annotated corpus of Spanish newswire rich in unassimilated lexical borrowings{---}words from one language that are introduced into another without orthographic adaptation{---}and use it to evaluate how several sequence labeling models (CRF, BiLSTM-CRF, and Transformer-based models) perform. The corpus contains 370,000 tokens and is larger, more borrowing-dense, OOV-rich, and topic-varied than previous corpora available for this task. Our results show that a BiLSTM-CRF model fed with subword embeddings along with either Transformer-based embeddings pretrained on codeswitched data or a combination of contextualized word embeddings outperforms results obtained by a multilingual BERT-based model.",
}


@InProceedings{TIEDEMANN12.463,
  author = {Jörg Tiedemann},
  title = {Parallel Data, Tools and Interfaces in OPUS},
  booktitle = {Proceedings of the Eight International Conference on Language Resources and Evaluation (LREC'12)},
  year = {2012},
  month = {may},
  date = {23-25},
  address = {Istanbul, Turkey},
  editor = {Nicoletta Calzolari (Conference Chair) and Khalid Choukri and Thierry Declerck and Mehmet Ugur Dogan and Bente Maegaard and Joseph Mariani and Jan Odijk and Stelios Piperidis},
  publisher = {European Language Resources Association (ELRA)},
  isbn = {978-2-9517408-7-7},
  language = {english}
 }
 
 
 @article{costa2022no,
  title={No language left behind: Scaling human-centered machine translation},
  author={Costa-juss{\`a}, Marta R and Cross, James and {\c{C}}elebi, Onur and Elbayad, Maha and Heafield, Kenneth and Heffernan, Kevin and Kalbassi, Elahe and Lam, Janice and Licht, Daniel and Maillard, Jean and others},
  journal={arXiv preprint arXiv:2207.04672},
  year={2022}
}
