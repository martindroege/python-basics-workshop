# Block 8: Web Scraping

## Ziel des Web Scraping

* Posts vom Blog der AG Digitale Geschichtswissenschaft bei hypotheses.org
* [https://digigw.hypotheses.org/](https://digigw.hypotheses.org/)

## Zutaten für das Skript

* Webseite aufrufen
* html erfassen
* html parsen
* Text extrahieren
* Text in Datei speichern
* Datei benennen

## Inspektion der Webseite

* Gibt es eine serielle URL?
* Wie ist diese aufgebaut?
* In welchem html-div findet sich Text?

## serielle URL

[https://digigw.hypotheses.org/3653](https://digigw.hypotheses.org/3653)

## Webseiten Inspektor

**STRG + SHIFT + I**

<!-- ## Ansicht Inspektor

<img src="
../images/snapshot_inspector.png" alt="Drawing" style="width:
700px;"/> -->

## Bausteine des Skripts I

* Import der benötigten Module und Bibliotheken
* URL-Root einrichten Variablen benennen
* Startseite bzw. Indexseite anfragen
* html in Variable speichern
* IDs der Blogposts aus html extrahieren
* IDs der Blogposts in Liste speichern
* for-Schleife zur wiederholten Anwendung

## Bausteine des Skripts II

* aus der Liste der IDs URL zusammensetzen und anfragen
* html in Variable speichern
* Text des Posts aus html extrahieren
* Text in Datei speichern
* for-Schleife zur wiederholten Anwendung

## Import der Module

```Python
import requests
import time
from bs4 import BeautifulSoup
```

## URL-Root und Variablen

```Python
url_root = 'https://digigw.hypotheses.org/'
blog_ID_list = []
article_length_list = []
```

## Schleife IDs

```Python
for x in range(1,19):
    url = url_root + 'page/' + str(x)
    response = requests.get(url)
    response = response.text
    soup = BeautifulSoup(response, 'html.parser')
    blog_IDs = soup.find_all('h2',
                             {'class': 'entry-title'})    
    for element in blog_IDs:
        blog_ID = element.find('a')['href']
        blog_ID = blog_ID.split('/')
        blog_ID = blog_ID[3]
        blog_ID_list.append(blog_ID)    
    time.sleep(5)
```

## Schleife Text

```Python
for x in blog_ID_list:    
    try:
        response = requests.get(url_root + str(x))
        response = response.text 
        soup = BeautifulSoup(response, "html.parser")
        article_text = soup.find(
                        attrs={"class": "entry-content"}
                        ).text.strip()
        article_length_list.append(len(article_text))
        with open(r'./data-blog-posts/digigw-blog_' 
                    + str(x) + '.txt', 
                    'w', encoding='utf-8') as infile:
            infile.write(article_text)   
        time.sleep(8)
    except:
        continue
```

## Ausgabe Ergebnisse

```Python
print(blog_ID_list)
print('Gesamtanzahl der Blogbeiträge: ') 
print(str(len(blog_ID_list)))
print('Anzahl der Zeichen des längsten Blogbeitrags: ')
print(str(max(article_length_list)))
print('Anzahl der Zeichen des kürzsten Blogbeitrags: ')
print(str(min(article_length_list)))
print('Anzahl der Zeichen der Blogbeiträge im Durchschnit: ')
print(str(sum(article_length_list) / len(article_length_list)))
```
