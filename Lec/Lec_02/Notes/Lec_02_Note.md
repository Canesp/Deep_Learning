## Nurala nätverk arkitectur

Arkitecturen för en NN beskriver den över gripande strukturen - vilka beståndsdelar som finns och hur de sitter ihop.

Arkitecturen har stor betydelse för prestandan på Nätverket. 


## Hur påverkar breden ett nätverk

input lagger antal input dimentioner.

output lagger antal output dimentioner. 

desto djypare ett nätverk är alltså mängden hidden layers så destomer komplexa problem kan den lössa.

är de för stora så kommer det ta lång tid att träna. (man får vara försiktig på overfitting).

är det för litet kan nätverket inte göra lika lösa komplexa problem.

lagom är bäst.

## Hur vet jag vilken arkitektur ska jag ha.

för utom input och output vet vi inte. man får testa sig fram till en bra lösning.

det finns inga garantier att nätverket kommer att lära sig.

## Nätverk Input

hur ska inputen se ut för ett nätverk. 
det beror på datan. 

är det tex kordinater altså x, y och z så kommer det vara 3 inputs.

## Nätverk output

Det beror på vad för output vi berhöver föt problemet.

outputen bör också ha en aktiveringsfunktion. Den skilljer sig oftast från aktiveringsfunktioner från resten av nätverket.

man kan ha en linjär om man vill i output noden. (men det beror på vad man vill göra)

Det är vanligt att använda linjär aktiveringsfunktion i output när man kör regression.

Skulle vi vilja göra en binär klassifcering är det oftast man använder sig av sigmoid funktion.

Vid multiklass klassificering är det vanligt att använda softmax. 

## Aktiveringsfunktioner i gömdalager 

Finns väldigt många att välja på men alltid bra att börja med ReLu.

## Loss functions.

loss functions är inte samma sak som aktiveringsfunktionerna.

de hjälper oss bestämma hur bra våran model är.

En vanlig funktion är MSE (Mean square error).

## Träna nätverk

datapunkten kommer in igenom input lagret. 

informationen flödar igenom de gömda lagrena med akitverings funktioner. 

## Vikterna 

det bästa är att initiera vikterna randomly.


## inferens av nätverk

...