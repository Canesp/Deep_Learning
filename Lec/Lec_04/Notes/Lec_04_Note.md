# Lec-04 
**Datum: 2023-11-27**

## Ordlista träning 

- **Iteration** - En bakåtpropagering med viktuppdatering.

- **Batch** - Under en iteration skickar man inte alltid in all data på en gång, så en batch är den data man använder under den iterationen.

- **Epok** - När man går igenom all data med forward och backward propagation.

## Gradient Descent fortsättning

Gradient descent handlar om att hitta minimin i det globala maxima.

## GD varianter och optimeringsalgoritmer

Det finns smarta varianter av GD samt optimeringsalgoritmer för att hitta minimum snabbare utan att fastna i lokala minima.

### Batch GD

Vi gör vårt hopp när modellen har sett all data.
En iteration = En epok.

Medelvärdet på gradienten för alla träningsexempel. 

Bra om man har en liten datamängd och få features, annars väldigt kostsam.

**Pros and Cons**

| Fördelar         | Nackdelar       |
|------------------|-----------------|
| Mindre varierande hopp mot minimum | Kräver mycket minne för att hålla hela datamängden |
| Stabilt hopp mot minimum | Kan vara långsamt för stora datamängder och många features |

---

### Stochastic Batch GD 

Vi använder stochastic batch gradient descent för att göra mindre justeringar av vikterna genom att beräkna gradienten för en mindre slumpmässig del av träningsdatan vid varje iteration. Detta tillvägagångssätt kombinerar idéerna bakom batch gradient descent och stochastic gradient descent genom att arbeta med små batchar av data istället för hela datasetet.

Processen innebär:

1. **Slumpmässigt välja en delmängd av träningsdata:** 
2. **Beräkna gradienten för den valda delmängden:** 
3. **Uppdatera vikterna baserat på den beräknade gradienten och vald inlärningshastighet:** 

Detta tillvägagångssätt kan ge en balans mellan snabbhet (liknande stochastic gradient descent) och stabilitet (likt batch gradient descent) under träningen av modellen.

**Pros and Cons**

| Fördelar         | Nackdelar       |
|------------------|-----------------|
| Snabbare konvergens på stora dataset | Ostabilt hopp mot minimum |
| Kräver mindre minne än Batch GD | Högre variation i gradient och hopp |

---

### Stochastic Mini-batch GD

Även kallat mini-batch.

Vi gör ett hopp för varje batch av data:
1. **Ta x träningspunkter:**
2. **Kör dem genom nätverket:**
3. **Uppdatera vikter och beräkna gradienter:**
4. **Justera vikter baserat på gradienter och vald inlärningshastighet:**
5. **Upprepa steg 1-4 tills du når önskad noggrannhet eller antal iterationer.**

Detta tillvägagångssätt används för att träna neurala nätverk och består av att segmentera träningsdatan i mindre grupper (minibatchar) för att utföra gradientberäkningar och viktuppdateringar.

**Pros and Cons**

| Fördelar         | Nackdelar       |
|------------------|-----------------|
| Balans mellan stabilitet och hastighet för stora dataset | Mindre variation i gradient och hopp jämfört med Stochastic Batch GD |
| Mindre minneskrävande än Batch GD | Mindre variation i gradient och hopp jämfört med Stochastic Batch GD |

---

## Gradient problem

Får vi för små eller för stora gradienter kan det leda till att nätverket inte uppdateras på ett lämpligt sätt under träningen, vilket kan påverka prestandan hos det neurala nätverket.

### Vanishing gradient problem

Vanishing gradient sker när gradienten sjunker exponentiellt genom nätverkets lager, vilket leder till att vikterna i tidiga lager inte uppdateras tillräckligt under träningen.

Detta fenomen är vanligt förekommande i:

- Ett väldigt djupt nätverk.
- Aktiveringsfunktioner som exp sigmoid och tanh, då dessa kan generera små gradienter som kan leda till vanishing gradient.

För att undvika eller motverka detta fenomen kan vi göra ändringar i nätverket såsom att ändra aktiveringsfunktionen till mer robusta alternativ och även överväga att korta ner nätverkets djup.

---

### Exploding gradient problem

Exploding gradient innebär att gradienten blir väldigt stor när vi rör oss bakåt i nätverket, vilket kan göra att vikterna uppdateras med mycket stora värden.

För att undvika detta kan vi göra följande ändringar i nätverket:

- Använda L2 Regularisering.
- Minska nätverkets djup.
- Minska värdet på learning rate.
- Använda gradient clipping, det vill säga sätta ett mindre maxvärde på gradienten.

### Momentum

Momentum fungerar på ett sätt som liknar fysikens principer om rörelsemängd (tänk på en boll som rullar ner för en backe).

Genom att lägga till en "historieparameter" hjälper Momentum till att accelerera konvergensen och kan undvika att fastna i lokala minima.

| Fördelar                                      | Nackdelar                                  |
|-----------------------------------------------|--------------------------------------------|
| Får nätverket att konvergera snabbare.        | Introducerar en ny parameter.               |
| Kan undvika att fastna i lokala minima.       |                                            |
|                                               |                                            |

### RMSProp

Root Mean Square Propagation har en adaptiv learning rate som anpassar sig efter gradientens storlek. Den minskar stegen för stora gradienter och ökar stegen för små gradienter.

| Fördelar                                      | Nackdelar                                  |
|-----------------------------------------------|--------------------------------------------|
| Konvergerar snabbare.                          | Introducerar en ny parameter.              |
| Kan undvika att fastna i lokala minima.       |                                            |
| Minskar risken för exploding och vanishing gradient. |                                     |

---

### Adam 

Adam står för adaptiv moment estimation och använder sig av adaptiv learning rate. Den kombinerar principer från både Momentum och RMSProp. Det är en väldigt vanligt använd optimeringsalgoritm.

| Fördelar                                      | Nackdelar                                  |
|-----------------------------------------------|--------------------------------------------|
| Hyfsat beräkningseffektiv.                    | Kan överanpassa på små dataset.            |
| Kräver lite minne.                            |                                            |
| Fungerar bra med stora dataset och många parametrar. |                                       |
| Har få nackdelar.                             |                                            |
