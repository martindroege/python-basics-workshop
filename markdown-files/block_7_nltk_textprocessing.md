# Block 7: NLTK und Worthäufigkeiten visualisieren

## collections

```python
from collections import Counter

freq = Counter(grundgesetz_words)
```

## most common

```python
print(freq.most_common(25))
```

## NLTK

```python
import nltk
from nltk.tokenize import word_tokenize
nltk.download('punkt')

with open('grundgesetz.txt', 'r', encoding='utf-8') as infile:
    text_raw = infile.read()

text = text_raw.lower()
text = word_tokenize(text)
text = nltk.Text(text)  
```

## concordance

```python
text.concordance("freiheit")
```

## similar

```python
text.similar("freiheit")
```

## dispersion plot

```python
text.dispersion_plot(["artikel", "gesetz", "freiheit"])
```

## Worthäufigkeiten visualisieren

## Importe

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```

## Dataframe erstellen

```python
df = pd.DataFrame(freq.items(), 
                  columns=['word', 'count'])
                  
df = df.sort_values(by='count', 
                  ascending=False)

df_top_25 = df.head(25)
```

## Dataframe plotten

```python
fig, ax = plt.subplots(figsize=(12,8))

sns.barplot(x='word', 
            y='count', 
            data=df_top_25, 
            ax=ax)

ax.set_xticklabels(labels=df_top_25.loc[:, 'word'], 
                   rotation=45, 
                   ha='right')
```
