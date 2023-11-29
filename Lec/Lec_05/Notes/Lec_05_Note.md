# Lec-05
**Datum: 2023-11-29**

# Databehandling 

Data är a och o för deep learning.

Mer data betyder ofta att mer data ger bättre resultat. Men man ska tänka på att om man bara ändrar en sak kommer man få "Diminishing returns".

Men det hjälper väldigt mycket om:

- datan är av hög kvalitet. 
- ...

## Städa data

- Ta bort duplicerade datapunkter. 
- Se till så att all data är formaterad på samma set igenom datasetet. 
- Ta bort oönskade outliers. 
- Hantera saknad data, ska man ta bort datapunkten eller kan man gissa vad för värde som ska vara där. 
- Validera datan för varje kolumn, är förväntad data faktiskt unikt och är datan rimlig (Baseras på domänkunskaper).

# Encoding 

Kategorisk data är svårt att mata in direkt i en ML modell, vissa punkter måste representeras på ett numeriskt sätt.

## Ordinal Encoding

Vi har färgerna grön, lila, gul och röd som vi ksa encodea. är bra om det finns en inneboend ordning annars preseterar den sämre. 

## One-hot Encoding

Vi har en datapunkt äpple, plommon, citron och tomat som vi encodaear igenom att ge dem en vector värde. tex äpple blir [1, 0, 0, 0].

## Dummy Encoding 

Dummy och One-hot encoding är väldigt lika varandra, skillnaden är att den sista klassens värden i vectorn blir till ett alltså tex [0, 0, 0]

# Balansera dataset

Man kan balancera ett dataset igenom att skaffa mer data av den data typen som vi behöver mer av. Men detta kan vara svårt ibland när det inte finns mer data i det området. 

man kan då: 

- Augmentera fram data.
- använda mindre av den data som man har mycket av. 

# Data augmentering

Är när man artificiellt utökar datasetet genom att augmentera data. 

Deta fungerar väldigt bra till vissa typer av data, tex bilder. kan vara svårare för andra typer av data. 

När man gör augmentering tar man tex en bild och ändra olika grejer så som att ändra färg vrida på bilden för att skapa ny bilder som nätverket aldrig har set innan och på så set öka datasetets storlek. 

# Normalisering & standardisering 

Normalisering innebär att vi skalar om en feature så max = 1 och min = 0 eller max = 1 och min = -1.

Standardisering antar man att datan är normalfördelad och man skalar om datan så att medelvärdet = 0 och att standardavvikelsen är 1. 

## Normalisering - varför hjälper det. 

Den stabeliserar gradient descent och gör att modellen konvergerar lättare. (det gör att det går snabbare) Det hjälper till att träna ett neruralt nätverk igenom att hålla alla features på samma skala. 

## Feature engineering 

Man kan inte smälla på normalisering eller one-hot encoding på all data. Utan man måste förstå vad det är för data vi har. 

Beroende på problemet kan: 

- One-hot encoding, göra att det blir väldigt många klasser beronde på problemet och denna mängd kan ledda till problem.

- Normalisering / standardisering, gör ...

Man kan instället försöka representera datan på ett annat set. 

# Regulariseringstekniker

Är för att förska undvika overfitting. 

två vanliga är L1 och L2 regularisering och är en term man lägger på loss-funktionen.

cost function = Loss() + regulariseing term

Kommer att påverka vikterna för modeln under backpopogation. 

## L2 regularisering (Weight decay)

cost function = Loss + lamda / 2m * E||w||^2 

Denna term tvingar vikterna att gå mot 0 men aldrig till 0. 

## L1 regularisering (Lasso)

cost function = loss + lambda/2m Ä E||w||

Denna term kan reducera vikterna till 0, vilket är användbart om man vill komprimisa sin model då det "tar bort" features. 

## L1 vs L2
tabel: L1, L2
L1 penilzes sum of absolute values of weights., L2 penelizes sum of square values of weights.

L1 generates model that is simple and interpretable, L2 is capeble to leran complex tasks...

## Drop out 

Drop ut är en vanilig och effektiv metod för regularisering. under träning kommer drop out att slump mässigt att ta bort olika nevroner och tvingar nätverket att inte använda dem. deta händer under varje epok. man får tänka på att inte göra så den släcker för mycket av nätverkat så att den inte lär sig någonting. (vi tvingar nätverket att hitta olika mönster i datan)

# Hyperparameteroptimering 

Hyperparametrar är parameterar som bestämer över nätverket och dess träningsprocessen på en hög nivå. 

Detta är något som nätverket inte kan lära sig själv utan är något som vi får personligen sätta. (Nätverksparametrar är inte samma sak som hyperparametrar). 

Exemple på hyperparametrar: 

- Learining rate
- Optimeringsalgoritm 
- antal tränings epoker
- batch size
- dataset split ratio
- Antal gömda lager
- Drop-out rate
- ...

## Grid search 

Man anvädner grid search för att testa sig fram till de bästa parametrarna och dess kombinationer. Kan ta väldigt lång tid om man testar många olika kombinationer. 

Vi använder seda dessa kombinationer som vi har kommit fram till i våran riktiga träning. 






