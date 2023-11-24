# Lec-01 
**Datum: 2023-11-22**

<br>

## Introduktion

Tensorflow doc är din bästa vän. 
https://www.tensorflow.org/api_docs/python/tf

## Maskininlärning genom tiderna - Översikt

<details>
<summary>1959: Arthur Samuels inför begreppet Machine Learning</summary>

- Introducerade Arthur Samuel termen Machine Learning.
- Teorier från 1800-talet kan också ses som ML, vilket antyder att ML började tidigare.

</details>
<br>

---

<details>
<summary>60-70-talet: ML tar fart</summary>

- ML började få fart och betraktades som framtiden.

</details>
<br>

---

<details>
<summary>Mitten av 70-talet: AI-vintern</summary>

- AI-vintern inträffade, vilket resulterade i svårigheter att få finansiering för AI-projekt.

</details>
<br>

---

<details>
<summary>80-talet: Lite framsteg inom ML</summary>

- Utvecklingen av ML började visa lite framsteg.

</details>
<br>

---

<details>
<summary>Slutet av 90-talet / tidigt 2000-tal: Specifika lösningar framträder</summary>

- Specifika lösningar för specifika problem började framträda och vinna popularitet.

</details>
<br>

---

<details>
<summary>2010: ImageNet-tävlingen</summary>

- ImageNet-tävlingen ägde rum.

</details>
<br>

---

<details>
<summary>2011: IBM Watson lanseras</summary>

- IBM Watson lanserades.

</details>
<br>

---

<details>
<summary>2012: Deep learning framträder</summary>

- Deep learning började vinna tävlingar inom AI/ML och hypen kring tekniken ökade.

</details>
<br>

---

<details>
<summary>2015: Explosion av AI-projekt hos Google</summary>

- Google gick från att ha några AI-projekt till närmare 3000 projekt, inklusive AI/ML.

</details>
<br>

---

<details>
<summary>2016: AlphaGo besegrar världsmästaren i Go</summary>

- AlphaGo utmanade och besegrade världsmästaren i Go.

</details>
<br>

---

<details>
<summary>2020: Tesla släpper självkörande mjukvarubeta</summary>

- Tesla släppte sin "beta" av sin mjukvara för helt självkörande bilar.

</details>
<br>

---

<details>
<summary>2022: OpenAI släpper ChatGPT</summary>

- OpenAI släppte ChatGPT.

</details>
<br>

---

<details>
<summary>2023: Ökande användning av generativ AI</summary>

- Användandet av generativ AI ökar exponentiellt.

</details>
<br>

## Deep learning

Deep learning är en gren inom maskininlärning som använder neurala nätverk bestående av flera gömda lager för att utföra olika typer av uppgifter. Ett djupt neural nätverk (DNN) består av flera lager av neuroner som bearbetar och transformerar data genom dessa lager för att lösa komplexa problem.

Djupa neurala nätverk (DNNs) utmärker sig genom sin förmåga att hantera och lära av stora mängder data. Genom att lära sig representationer av data i flera abstrakta nivåer kan dessa nätverk identifiera mönster och funktioner som kan vara svåra att upptäcka med traditionella metoder.

Ett tydligt exempel på djupinlärning är dess användning för klassificering av bilder. Genom att träna djupa neurala nätverk på ett stort antal bilder kan de identifiera mönster och kännetecken som gör det möjligt att skilja olika objekt eller klasser från varandra med hög noggrannhet. Detta har visat sig vara särskilt framgångsrikt inom områden som bildigenkänning och objektidentifiering.

Deep learning har blivit en kraftfull metod inom AI och maskininlärning, och dess förmåga att hantera stora datamängder och lösa komplexa problem har lett till innovativa tillämpningar inom olika branscher.

Bra video: https://www.youtube.com/watch?app=desktop&v=q6kJ71tEYqM

## Neurala nätverk

Ett enkelt fully connected neural network består av tre typer av lager, där varje lager i sin tur består av en perceptron.

Funktionen för en perceptron är:

$$
f(z) = \begin{cases} 
      1 & \text{om } z > \text{tröskelvärde} \\
      0 & \text{annars} 
   \end{cases}
$$

där $z = \sum_{i=1}^{n} w_i \cdot x_i + b $ är summan av viktade indata plus bias.

### Perceptron:

Varje perceptron tar in flera inputs och producerar 1 output genom att applicera en tröskelfunktion på summan av viktade indata och bias.

### Inputlager:

Inputlager representerar din inputdata. Till exempel kan inputen bestå av tre dimensioner, såsom x-, y- och z-koordinater. I detta exempel resulterar inputen i två dimensioner i outputen.

### Gömda lager:

De gömda lagren utgör kärnan i ett neural network. När det finns många gömda lager kallas det för "deep neural network". Varje ytterligare lager gör modellen mer komplex.

För ett lager i ett neuralt nätverk är den övergripande matematiska operationen:

$$
A^{[l]} = g^{[l]}(W^{[l]} \cdot A^{[l-1]} + b^{[l]})
$$

där $A^{[l]}$ är aktivationsmatrisen för lager $(l)$,
$(W^{[l]})$ är vikterna, $(b^{[l]})$ är biasen och $(g^{[l]})$ är den valda aktiveringsfunktionen.

### Aktiveringsfunktioner:

Det finns många olika aktiveringsfunktioner att välja mellan, inklusive ReLU (Rectified Linear Activation), sigmoid och tanh. Dessa funktioner har stor påverkan på perceptronens output. Det är också möjligt att använda olika aktiveringsfunktioner på olika ställen i nätverket.

### Inferens av NN (Forward pass):

Under inferensen av neurala nätverk matas en datapunkt in och alla beräkningar utförs genom hela nätverket för att få en output.

För varje datapunkt \(x\) i indata:

- $x$ representerar inputvektorn.
- $y$ representerar målvektorn.
- $\hat{y}$ representerar outputvektorn.
- $L$ representerar antalet lager i neurala nätverket.
- $f^{[l]}$ är aktiveringsfunktionen vid lager $l$.
- $w^{[l]}$ $w^{[l]}_{jk}$ representerar vikterna 

mellan lager $l - 1$ och $l$, där $w^{[l]}_{jk}$ är vikten mellan den $k$-te noden i lager $l - 1$ och den $j$-te noden i lager $l$.

Totala ekvationen för nätverket kan beskrivas som:

$$
g(x) = f^{[L]}(w^{[L]} \cdot f^{[L-1]}(w^{[L-1]} \cdot \ldots \cdot f^{[2]}(w^{[2]} \cdot f^{[1]}(w^{[1]} \cdot x))))
$$

Där $f^{[1]}$ är aktiveringsfunktionen för det första lagret och $f^{[L]}$ är aktiveringsfunktionen för det sista lagret.

för en datapunkt i från tränings datan ${(x_i, y_i)}$, så beräknas output av nätverket enligt.

### Hur lär sig ett nätverk:

Vi försöker approximera en funktion utan att veta exakt vilken funktion det är. Genom att använda input- och outputdata kan vi justera våra nätverksvikter för att minska felet mellan den förutsagda outputen och den verkliga outputen.

### Loss functions:

Loss functions mäter hur mycket nätverkets output skiljer sig från den verkliga outputen. Mean Square Error (MSE) används ofta för regressionsproblem, medan Cross Entropy Loss passar bra för klassificeringsproblem.

För ett nätverk blir lossen $L(\hat{y_i}, y_i) = Loss$.

### Bakåtpropagering (Backpropagation):

Backpropagation är hur vi uppdaterar ett nätverk med avseende på felet, vilket tillåter nätverket att lära sig. Det beräknar gradienten av felet med avseende på vikterna, där felet är skillnaden mellan nätverkets output och den verkliga outputen (ground truth). 

### Minima och Maxima:

I optimering letar vi efter lokala och globala minima och maxima för att hitta de bästa vikterna för vårt nätverk.

### Derivata:

Derivatan representerar lutningen i en given punkt på en funktion.

### Gradient:

Gradienten är en vektor som anger riktningen av största lutning för en funktion.

### Kedjeregeln:

Kedjeregeln används för att beräkna derivatan av sammansatta funktioner, exempelvis $F(x) = f(g(x))$, där $F(x) = f(g(x)) \cdot g(x)$.

### Backpropagation:

För varje träningsdatapunkt där vi har en input $x$ och en ground truth $y$, beräknar vi felet i nätverkets output och använder detta för att justera våra vikter.

### Learning Rate:

Learning rate bestämmer hur stora steg vi tar i optimeringsprocessen - en högre learning rate ger snabbare inlärning, men det kan också leda till att vi hoppar över det globala minimum.

### Hur beräknar vi viktens nya värde?

Gradient descent är en teknik för att uppdatera vikterna genom att förflytta sig i riktningen som minimerar felet.

### Backpropagation vs. Gradient Descent:

Backpropagation används för att beräkna gradienten av felet med avseende på varje vikt, medan gradient descent används för att uppdatera vikterna för att minska felet.

### Att träna ett nätverk - grunderna:

Genom att slumpmässigt initialisera vikterna kan vi börja optimeringsprocessen för att hitta de bästa vikterna för att minimera felet och förbättra nätverkets prestanda.
