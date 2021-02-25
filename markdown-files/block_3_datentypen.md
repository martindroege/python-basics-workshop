# Block 3: Datentypen

## Zeichenketten / Strings

```Python
print("Hallo Welt!")
```

## Konkatenieren

```Python
print("Hallo " + "Welt!")

print("Digital History Tagung " + "2021")

print("foo" * 2 + "bar " * 3)
```

## Variablen

```Python
event = "Digital History Tagung"
year = 2021
```

## f-Strings

```Python
print(f"Die {event} findet {year} statt.")

print("Die {} findet {} statt.".format(event, year))
```

## Funktionen und Methoden bei Strings

```Python
len(event)

len("Digital History Tagung")

event.lower()

"Digital History Tagung".upper()
```

## Built-in Functions

* [Übersicht und
  Dokumentation](https://docs.python.org/3/library/functions.html)
* Grundsätzlich: Dokumentationen helfen oft weiter!

## Listen / Lists

```Python
list_1 = [1, 2, 3, 4]

list_2 = ["Banane", "Apfel", "Birne"]

list_3 = [17, "Obst", 23, "Ball"]

list_4 = [[1, 2, 3,], ["a", "b", "c"], ["Hallo", "Welt"]]
```

## Zuordnungen / Dictionaries

```Python
dict_1 = {"Banane": 5, 
          "Apfel": 7, 
          "Birne": 9}

dict_2 = {"Vorname": "Monty", 
          "Nachname": "Python", 
          "Alter": 48}
```

## Mengen / Sets

```Python
menge = {1, 2, 2, 3, 3, 3, 4, 4, 5, 5, 5}

print(menge)

type(menge)
```

## Tuple

```Python
word_freq = ("Wort A", 42)

type(word_freq)
```

## Indexieren von Strings

```Python
"Digital History Tagung"[1]

"Digital History Tagung"[0]

"Digital History Tagung"[8]
```

## Slicing

```Python
"Digital History Tagung"[0:10]

"Digital History Tagung"[3:6]
```

## Indexieren von Listen

```Python
list_2 = ["Banane", "Apfel", "Birne"]

list_2[2]

list_2[0]
```

## Funktionen und Methoden bei Listen

```Python
len(list_2)

list_2.append("Ananas")

list_2.pop()
```

## Zugriff auf Dictionaries

```Python
dict_1 = {"Banane": 5, "Apfel": 7, "Birne": 9}

dict_1["Banane"]

dict_1.keys()

dict_1.values()

sum(dict_1.values())
```

## Logische Ausdrücke

```Python
5 > 3

5 > 7

"Mauer" == "Haus"

"Mauer" != "Haus"
```

## Logische Ausdrücke: and, or

```Python
5 > 3 and "Mauer" != "Haus"

5 > 3 and "Mauer" == "Haus"

5 > 3 or "Mauer" == "Haus"

5 > 7 or "Mauer" == "Haus"
```
