# Block 5: Pseudo-Code

## algorithmisches Denken

* Problem in einzelne Schritte zerlegen
* Schritte ausformulieren
* einzelne Bauteile zusammenstellen

## Pseudo Code

    TEXT =  "text"

    LOOP OVER TEXT

        IF ELEMENT IS VOWEL
    
            PRINT ELEMENT

## Vorteil

* Vorgehen wird klarer
* Konzepte verstehen
* Übertragbar auf andere Programmiersprachen

## Problemstellung

Für die Zahlen zwischen 1 und 100 soll:

* FizzBuzz ausgegeben werden, wenn die Zahl durch 3 und 5 teilbar ist
* Fizz ausgegeben werden, wenn die Zahl durch 3 teilbar ist
* Buzz ausgegeben werden, wenn die Zahl durch 5 teilbar ist

## Pseudo-Code Beispiel

    FOR i from 1 TO 100 DO
        IF i is divisible by 3 AND i is divisible by 5 THEN
            OUTPUT "FizzBuzz"
        ELSE IF i is divisible by 3 THEN
            OUTPUT "Fizz"
        ELSE IF i is divisible by 5 THEN
            OUTPUT "Buzz"
        ELSE
            OUTPUT i

## Pseudo-Code in Python

```Python
for i in range(1,100):
    if i % 3 == 0 and i % 5 == 0:
        print('FizzBuzz')
    elif i % 3 == 0:
        print('Fizz')
    elif i % 5 == 0:
        print('Buzz')
    else:
        print(i)
```