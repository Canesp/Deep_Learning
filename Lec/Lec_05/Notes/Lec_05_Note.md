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
- Se till så att all data är formaterad på samma sätt genom datasetet. 
- Ta bort oönskade outliers. 
- Hantera saknad data, antingen genom att ta bort datapunkten eller genom att fylla i saknade värden baserat på gissningar eller imputationstekniker.
- Validera datan för varje kolumn för att säkerställa att förväntad data är faktiskt unik och rimlig baserat på domänkunskaper.

# Encoding 

Kategorisk data är svårt att mata in direkt i en ML modell, vissa punkter måste representeras på ett numeriskt sätt.

## Ordinal Encoding

Ordinal Encoding används för att koda kategoriska variabler som har en ordning eller rangordning. Det innebär att varje kategori tilldelas en unik numerisk representation. Detta är användbart när det finns en inneboende ordning mellan kategorierna.

## One-hot Encoding

One-hot Encoding används för att koda kategoriska variabler där det inte finns någon ordning mellan kategorierna. Varje kategori representeras som en binär vektor där den aktuella kategorin har värdet 1 och resten av vektorns element är 0. Till exempel representeras äpple som [1, 0, 0, 0] i en vektor av fyra kategorier.

## Dummy Encoding 

Dummy Encoding är liknande One-hot Encoding där den sista kategorin i den kategoriska variabeln representeras som 1 medan övriga kategorier representeras som 0. Till exempel representeras äpple som [0, 0, 0, 1] i en vektor av fyra kategorier.

# Balansera dataset

Att balansera ett dataset handlar om att hantera obalanserade dataklasser. Det kan innebära att skaffa mer data för underrepresenterade klasser eller använda mindre data för överrepresenterade klasser.


# Balansera dataset

Man kan balancera ett dataset igenom att skaffa mer data av den data typen som vi behöver mer av. Men detta kan vara svårt ibland när det inte finns mer data i det området. 

man kan då: 

- Augmentera fram data.
- använda mindre av den data som man har mycket av. 

# Data augmentering

Är när man artificiellt utökar datasetet genom att augmentera data. 

Deta fungerar väldigt bra till vissa typer av data, tex bilder. kan vara svårare för andra typer av data. 

När man gör augmentering tar man tex en bild och ändra olika grejer så som att ändra färg vrida på bilden för att skapa ny bilder som nätverket aldrig har set innan och på så set öka datasetets storlek. 

## Normalisering & standardisering 

Normalisering innebär att skala om en feature så att dess värden ligger mellan 0 och 1 eller mellan -1 och 1.

$$ \text{Normalized value} = \frac{\text{Original value} - \text{Min value}}{\text{Max value} - \text{Min value}} $$

Standardisering antar att datan är normalfördelad och skalar om datan så att dess medelvärde är 0 och standardavvikelsen är 1.

$$ \text{Standardized value} = \frac{\text{Original value} - \text{Mean}}{\text{Standard deviation}} $$

## Feature engineering 

Att använda normalisering och one-hot encoding på all data kan vara olämpligt. För att välja lämplig bearbetningsteknik måste man förstå datans natur och egenskaper. Det kan vara mer effektivt att utföra specifika transformationer eller representationer baserat på det specifika problemet och datan.


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
| L1                                 | L2                                               |
|------------------------------------|---------------------------------------------------|
| Penilzes sum of absolute values of weights. | Penelizes sum of square values of weights.         |
| Generates a simple and interpretable model. | Capable to learn complex tasks.                     |

## Drop out 

Drop ut är en vanlig och effektiv metod för regularisering. under träning kommer drop out att slumpmässigt ta bort olika neuroner och tvingar nätverket att inte använda dem. Detta händer under varje epok. Man måste tänka på att inte göra så att den släcker för mycket av nätverket så att den inte lär sig någonting. (vi tvingar nätverket att hitta olika mönster i datan)

# Hyperparameteroptimering 

Hyperparametrar är parameterar som bestämmer över nätverket och dess träningsprocessen på en hög nivå. 

Detta är något som nätverket inte kan lära sig själv utan är något som vi får personligen sätta. (Nätverksparametrar är inte samma sak som hyperparametrar). 

Exemple på hyperparametrar: 

- Learining rate
- Optimeringsalgoritm 
- Antal tränings epoker
- Batch size
- Dataset split ratio
- Antal gömda lager
- Drop-out rate
- ...

## Grid search 

Man använder grid search för att testa sig fram till de bästa parametrarna och dess kombinationer. Kan ta väldigt lång tid om man testar många olika kombinationer. 

Vi använder sedan dessa kombinationer som vi har kommit fram till i vår riktiga träning.
