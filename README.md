# Cohesion Pipeline


The Topic-Detection field deals mainly with providing names to given divisions of documents and lacks a quality measurement that provides a rating for the division, that represent a human-subjective score.

Given a division cohesion-pipeline will calculate the human-subjective score, and the related topic name to each label in a division.

The POC to this attitude can be found in the [colab-notebook](https://colab.research.google.com/drive/1RreFOEd5LQDaNB7kQcH44bk5gkTpSVeH?usp=sharing), or in the ["Cohesion Pipeline Project- Full report"](https://github.com/Berdugo1994/cohesion-pipeline/blob/main/Cohesion%20Pipeline%20Project%20-%20Full%20Report.pdf)

## Installation

```bash
pip install cohesion-pipeline
```

## Usage Example
The input to the cohesion_score function must be a csv, txt, tsv file with a tab['\t'] seperator and must have 'label' and 'text' columns
```python
import pandas as pd
from cohesion import cohesion_pipeline

data = {"text":
            ["we like to play football",
             "I'm playing football better than neymar and cristano ronaldo",
             'I like Fifa more than I like football, My Fav team is #RealMadrid Hala Madrid',
             'Hamburger or Pizza? what would i choose? I will eat both of them, it so tasty!',
             'banana pancakes with syrup maple, thats my favorite meal'],
        'label':
            [1, 1, 1, 2, 2]}
df = pd.DataFrame(data)
score, topic_names  = cohesion_pipeline.cohesion_df(df)
print("Cohesion Final score is", score)
print("Cohesion Topics are:", topic_names)

```
