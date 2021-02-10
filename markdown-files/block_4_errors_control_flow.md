# Block 4: error handling und Kontrollstrukturen

## User-Input Skript

```Python
# Eingabe Name
name = input("Wie heißt du? >>>")
# Eingabe Alter
alter = input("Wie alt bist du? >>>")
# Eingabe Wohnort
ort = input("Wo wohnst du? >>>")
jahr = 2021 - int(alter)
# Ausgabe
print(f"""
\nHallo {name}, schön, dass du da bist!\n
Du bist {jahr} geboren.\n
{ort} ist der beste Ort auf dem Planeten.""")
```

## Fehlerbehandlung / error handling

```Python
print("Hallo Welt!"

File "<ipython-input-5-e1aa54892f20>", line 1
    print("Hallo Welt!"
                           ^
SyntaxError: unexpected EOF while parsing
```

## Fehlerbehandlung / error handling

```Python
for x in range(10)

File "<ipython-input-7-a12e79ce3754>", line 1
    for x in range(10)
                      ^
SyntaxError: invalid syntax
```

## Fehlerbehandlung / error handling

```Python
for x in range(10):
print(x)

File "<ipython-input-8-790af6e00d9b>", line 2
    print(x)
        ^
IndentationError: expected an indented block
```

## help() Function

```Python
help(len)
Help on built-in function len in module builtins:

len(obj, /)
    Return the number of items in a container.
```

## Kontrollstrukturen

## For-Schleife

```Python
for x in range(10):
    print(x)
```

## While-Schleife

```Python
x = 10
while x > 0:
    print(x)
    x -= 1
```

## If-Anweisung

```Python
for x in range(1, 11):
    if x % 2 == 0:
        print(f"{x} ist eine gerade Zahl.")
    else:
        print(f"{x} ist eine ungerade Zahl.")
```

## Dateien lesen 1

```Python
f = open("DATEI.txt", "r", encoding="utf-8")
text = f.read()
f.close()
```

## Dateien lesen 2

```Python
with open("DATEI.txt", "r", encoding="utf-8") as f:
    text = f.read()
```

## I/O Parameter

* "r" = read / lesen
* "w" = write / schreiben
* "a" = append / anhängen

## Kommentar

```Python
# Dies ist ein Kommentar
```
