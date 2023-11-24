# Lec-02 
**Datum: 2023-11-23**


# Neurala nätverksarkitekturer

Neurala nätverksarkitektur refererar till strukturen och organisationen av neuronnätverkets olika lager och hur de är sammanlänkade. En vanlig representation av ett neuralt nätverk består av flera lager:

1. **Input Layer:** Tar emot data för bearbetning.
2. **Hidden Layers:** Mellanliggande lager som utför komplexa beräkningar genom en kombination av linjära och icke-linjära operationer.
3. **Output Layer:** Ger resultatet av nätverkets bearbetning.

## Nätverksbreddens påverkan

Bredden av ett nätverk refererar till antalet neuroner i varje lager. Input-lagret har antal inputdimensioner och output-lagret har antal outputdimensioner. Ju fler neuroner eller lager, desto större förmåga att lösa komplexa problem. Emellertid medför ökad bredd även ökad beräkningsbörda och risk för överanpassning (overfitting) på träningsdata.

En enkel representation av ett neuralt nätverk med ett hidden layer kan definieras som:

$$
\begin{align*}
\text{Input: } x & \\
\text{Hidden Layer: } h &= f(W_1x + b_1) \\
\text{Output: } y &= g(W_2h + b_2)
\end{align*}
$$

Här representerar \(x\) inputdata, \(h\) är resultatet av hidden layer-beräkningar, \(y\) är den resulterande outputen, \(W\) är vikterna, \(b\) är bias och \(f\) och \(g\) är aktiveringsfunktioner för respektive lager.

## Val av Arkitektur

Förutom input och output är val av nätverksarkitektur ofta en iterativ process som involverar tester och utvärderingar av olika konfigurationer. Det finns ingen universell regel för att välja rätt arkitektur; det beror på det specifika problemet och tillgänglig data.

### Aktiveringsfunktioner

Aktiveringsfunktioner spelar en central roll i ett neuralt nätverk och introducerar icke-linjäritet, vilket möjliggör nätverkets förmåga att approximera komplexa funktioner. Några vanliga aktiveringsfunktioner inkluderar:

- **ReLu (Rectified Linear Unit):** $f(x) = \max(0, x)$
- **Sigmoid:** $f(x) = \frac{1}{1 + e^{-x}}$
- **Softmax:** $f(x_i) = \frac{e^{x_i}}{\sum_{j=1}^{K} e^{x_j}}$ (där \(K\) är antalet klasser)

### Loss Functions

Loss functions mäter hur bra modellen presterar på träningsdata jämfört med de verkliga värdena. För regression används ofta Mean Square Error (MSE):

$$
\text{MSE} = \frac{1}{n}\sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

Där \(n\) är antalet exempel, \(y_i\) är verkligt värde och \(\hat{y}_i\) är förutsagt värde.

För klassificering kan Cross-Entropy Loss användas:

$$
\text{Cross-Entropy} = -\sum_{i=1}^{n} y_i \cdot \log(\hat{y}_i)
$$

Där \(y_i\) är sannolikheten för rätt klass och \(\hat{y}_i\) är modellens förutsagda sannolikhet.

## Träning och Inferens

Träning av nätverk innebär att justera vikterna och biasen för att minimera förlustfunktionen. Under inferensfasen används det tränade nätverket för att göra förutsägelser på nya, tidigare osedda data.

En förenklad förklaring av träning kan representeras som en optimeringsprocess där man försöker hitta de optimala vikterna genom att minimera förlustfunktionen:

$$
\underset{W, b}{\text{min}} \: \text{Loss}(W, b)
$$

Här är \(W\) vikterna och \(b\) är biasen som justeras för att minimera förlusten.

### Vikter

Vikterna i nätverket representerar styrkan av kopplingarna mellan neuronerna. Vid nätverkets start initialiseras dessa oftast slumpmässigt för att undvika att fastna i lokala minima under träning.

Denna beskrivning är en förenklad översikt över neurala nätverksarkitekturer och deras funktion. Det finns många varianter och komplexiteter inom området som involverar flera avancerade tekniker för att förbättra prestanda och hantera olika typer av problem.
