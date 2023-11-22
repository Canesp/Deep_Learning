# Lec-01 
**2023-11-22**

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

för en datapunkt i från tränings datan ${(xi, yi)}$, så beräknas output av nätverket enligt.

### Hur lär sig ett nätverk 

vi försöker approximera en funktion

vi vet inte vad funktioner är men när vi vet input och output...

### Loss functions

ett sätt att mäta hur "fel" vår output jämnfört med gound truth.

Mean square Error (MSE) är populär för regressionsproblem.

Cross entropy loss är bra för klassificerings problem.

Lossen för ett nätverk blir då L(yhati, yi) = Loss

### bakåtpropagering (back propagation)

backåtpropagering är hur vi updatatera ett nätverk med avseende på på felet (vilket i sin tur tillåter nätverket att lära sig)...

backåtpropagering beräknar gradienten hos vikterna givet ett fel.

felet är skillanden i vårt NNs output och vårt svar, vår ground truth.

Med bakåtpropagering får vi reada på gradienten hos varje enskild vikt. 

vi vill att alla vikters gradient ska hamna i globala minima, -det betyder att felet på varje vikt är så litet det bara kan bli.

### Minima och maxima

lokala maxima och minima 

globala maxima och minima

### derivata 

lutningen i en punkt. 

### Gradient 

graienten är en vektor som..


### Kedjeregeln

the chain rule

for F(x) = f(g(x))

F(x) = f(g(x)) * g(x)




