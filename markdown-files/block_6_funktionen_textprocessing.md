# Block 6: Funktionen Textprocessing

## Text-Datei runterladen

```python
import requests

gg_raw_url = "https://raw.githubusercontent.com/levinalex/deutsche_verfassungen/master/grundgesetz/grundgesetz.txt"
response = requests.get(gg_raw_url)
grundgesetz = response.text

grundgesetz[:1000]
```

## Text-Datei speichern

```python
with open('grundgesetz.txt', 'w', encoding='utf-8') as f:
    f.write(grundgesetz)
```

## Kleinschreibung vereinheitlichen

```python
grundgesetz = grundgesetz.lower()
print(grundgesetz[:250])
```

## Zeichensetzung entfernen

```python
import string

def remove_punctuation(text):
    punctuation = string.punctuation
    for marker in punctuation:
        text = text.replace(marker, "")
    return text

grundgesetz = remove_punctuation(grundgesetz)
print(grundgesetz[:250])
```

## Liste erstellen

```python
grundgesetz_words = grundgesetz.split()
```

```python
print("Anzahl aller Worte des Textes: ")
print(len(grundgesetz_words)))
print("=======")
print(grundgesetz_words[:25])
```

## Zählen eines bestimmten Worts

```python
def count_item_in_text(item_to_count, list_to_search):
    number_of_hits = 0
    for item in list_to_search:
        if item == item_to_count:
            number_of_hits += 1
    return number_of_hits

print(count_item_in_text("freiheit", grundgesetz_words))
```

## Alle Wörter zählen mit Hilfe eines Dictionarys

```python
def counter_dict(list_to_search):
    counts = {}
    for word in list_to_search:
        if word in counts:
            counts[word] = counts[word] + 1  
        else:
            counts[word] = 1
    return counts

print(counter_dict(grundgesetz_words))
```

## Worthäufigkeiten sortieren

```python
def freq_sort(list_to_search):
    counts = counter_dict(list_to_search)
    counts = [(counts[key], key) for key in counts]
    counts.sort()
    counts.reverse()
    return counts

print(freq_sort(grundgesetz_words)[:25])
```

## Entfernen von Stoppwörtern

```python
import requests

def remove_stopwords(list_to_search):
    stopword_url = "http://members.unine.ch/jacques.savoy/clef/germanST.txt"
    response = requests.get(stopword_url)
    stopwords = response.text
    stopwords = stopwords.split()
    return [w for w in list_to_search if w not in stopwords]
  
print(remove_stopwords(grundgesetz_words)[:25])
```

## Funktionsaufrufe

```python
grundgesetz = grundgesetz.lower()
grundgesetz = remove_punctuation(grundgesetz)
grundgesetz_words = grundgesetz.split()
grundgesetz_words = remove_stopwords(grundgesetz_words)
print(freq_count(grundgesetz_words)[:25])
```
