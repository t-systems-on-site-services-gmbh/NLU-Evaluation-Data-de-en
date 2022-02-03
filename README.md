# NLU Evaluation Data - German and English - Similarity
This repository contains two dataset:

1. `NLU-Data-Home-Domain-Annotated-All-de-en.csv`: This dataset contains a labeled multi-domain (21 domains) German and English dataset with 25K user utterances for human-robot interaction.
2. `nlu_similarity_de.csv`: This dataset contains German sentence pairs from `NLU-Data-Home-Domain-Annotated-All-de-en.csv` with semantic similarity scores.

## `NLU-Data-Home-Domain-Annotated-All-de-en.csv`
This dataset is collected and annotated for evaluating NLU services and platforms.
The detailed paper on this dataset can be found at arXiv.org:
[Benchmarking Natural Language Understanding Services for building Conversational Agents](https://arxiv.org/abs/1903.05566)

The dataset builds on the annotated data of the [xliuhw/NLU-Evaluation-Data](https://github.com/xliuhw/NLU-Evaluation-Data)
repository. We have added an additional column (`answer_de`)
by translating the texts in column `answer` into German.
The translation was made with [DeepL](https://www.deepl.com/translator).

## `nlu_similarity_de.csv`
This dataset contains German sentence pairs with a similarity score.
The similarity score follows the approach in the [STSbenchmark dataset](https://ixa2.si.ehu.eus/stswiki/index.php/STSbenchmark).
These are explained in more detail in paper
[SemEval-2017 Task 1: Semantic Textual Similarity Multilingual and Cross-lingual Focused Evaluation](https://aclanthology.org/S17-2001.pdf).

## Load the Dataset (`NLU-Data-Home-Domain-Annotated-All-de-en.csv`)
The dataset can be loaded with [pandas](https://pandas.pydata.org/):
```python
import pandas as pd
df = pd.read_csv("NLU-Data-Home-Domain-Annotated-All-de-en.csv")
```

## Load the Dataset (`nlu_similarity_de.csv`)
The dataset can be loaded with [pandas](https://pandas.pydata.org/):
```python
import pandas as pd
df = pd.read_csv("nlu_similarity_de.csv")
```

## Dataset Quirks (`NLU-Data-Home-Domain-Annotated-All-de-en.csv`)
The original dataset contains some `NaN` values in the `answer` column.
This means that there are also `NaN` values in the translations (`answer_de` column).
These lines can be filtered as follows:
```python
answer_nan = df[df["answer"].isnull()]
answer_de_nan = df[df["answer_de"].isnull()]
```

## Copyright
Copyright (c) the authors of [xliuhw/NLU-Evaluation-Data](https://github.com/xliuhw/NLU-Evaluation-Data)<br/>
Copyright (c) 2022 Philip May

All data is released under the Creative Commons Attribution 4.0
International License (CC BY 4.0).
You should have received a copy of the license along with this dataset.
If not, see http://creativecommons.org/licenses/by/4.0/.
