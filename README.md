# talk-of-norway

This repository makes available the Talk of Norway (TON) dataset, a collection of Norwegian parliament speeches from 1998 to 2016. Every speech is richly annotated with metadata pulled from different sources, and augmented with sentence, token, lemma, part-of-speech and morphological feature annotations.

This work is inspired by the [Talk of Europe CLARIN campus](http://www.talkofeurope.eu/), and aims primarily at facilitating experimentation at the crossroads between quantitative Political Science and Natural Language Processing. The dataset is currently the core object of study of an interdisciplinary project involving the departments of Political Science and Informatics of the University of Oslo.

## Dataset

The data is split in two main parts, a csv file containing metadata (see [Data.md](Data.md) for a description of the available variables) along with the raw text of the speeches, and a folder containing the linguistic annotations of the speeches. The annotations in this folder are linked to their respective metadata row in the csv file by way of their file name, which is the same as the id variable.

The linguistic annotations their selves loosely follow the [CoNLL format](http://universaldependencies.org/format.html), with newline-separeted tokens and double newline-separated sentences. Every line contains tab-separated token-level annotations, following this pattern:

`index token lemma part-of-speech features`

For instance:

```
1    Ærede                ære                adj      fl|<perf-part>|tr1
2    medrepresentanter    medrepresentant    subst    appell|mask|ub|fl
3    !                    $!                 clb      <<<|<utrop>|<<<
```

## Sources

Linguistic annotations are automatically obtained using [langid.py](https://github.com/saffsd/langid.py) for language idenification and the [Oslo-Bergen tagger](https://github.com/noklesta/The-Oslo-Bergen-Tagger) for morphological analysis.

Metadata was pulled from several sources, utilizing a dump of the [holder-de-ord](https://www.holderdeord.no/portal) database as a starting point and adding further information from the [Storting api](https://data.stortinget.no/), scraping the [Storting web pages](Storting web pages) and integrating data from [Søyland (2016)](???).
See [Data.md](Data.md) for more information on the variables.

## Get the data

You can download the data from [url](url). The recommended way to stay up to date with this repository is to clone this repository and unpack the downloaded archive to its top-level directory.
