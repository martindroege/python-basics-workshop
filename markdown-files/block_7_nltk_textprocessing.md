# Block 7: NLTK

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

with open('grundgesetz.txt', 'r', encoding='utf-8') as infile:
    text_raw = infile.read()

text = text_raw.lower()
text = text.split()
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
