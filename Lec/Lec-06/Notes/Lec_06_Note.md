# Lec-05 
**Datum: 2023-12-4**

## CNN (Convolutional Neural Networks)

Convolutional Neural Networks (CNN) är en typ av neurala nätverk där minst ett lager är ett konvolutionslager. CNN är särskilt lämpliga för att hantera spatial data såsom bilder och används ofta inom bildigenkänning.

### Tillämpningar

#### Bildklassificering

- **Helbildsklassificering:** När nätverket klassificerar hela bilden.
- **Områdesklassificering:** Klassificerar en specifik del av en bild. Används ofta inom objektidentifiering för att klassificera flera objekt i en bild eller video.

#### Användningsområden

- **Yolo:** En populär modell för objektidentifiering.
- **Semantisk segmentering:** Klassificerar varje pixel i en bild. Exempelvis, ResNet är en populär modell för segmentering.
- **Instance segmentation:** Klassificerar liknande objekt individuellt.
- **Panoptic segmentation:** En kombination av både semantisk och instanssegmentering.

### Historia

CNN introducerades först 1989 med ConvNet, men dess prestanda var begränsad. Det var inte förrän ImageNet Challenge år 2010 som det fick större uppmärksamhet. ImageNet var en tävling som utmanade deltagare att testa sina algoritmer på stora dataset.

- 2012: AlexNet revolutionerade och dominerade ImageNet Challenge.
- 2014: VGG-16
- 2015: ResNet-50
- 2016: Yolo
- 2018: SE Networks

## Konvolution (Convolution)

En konvolution är en matematisk operation där två signaler kombineras för att skapa en tredje signal. I ett CNN används konvolutionsoperationer för att extrahera särdrag från datan.

### Konvolutionslager (Convolutional Layer)

En konvolutionsoperation utförs genom att applicera en kärna (filter) på inputen för att producera en feature map.

$$ \text{Input} \: (f) * \text{Kärna/Filter} \: (g) = \text{Feature Map} $$

### Kärna/Filter

Kärnan/filter används för att utföra konvolutionsoperationen på inputen. Det kan ha olika storlekar men är vanligtvis kvadratisk.

### Feature Map

En feature map är utdata från ett konvolutionslager och representerar särdragen i datan. Ett filter kan exempelvis användas för att detektera horisontella linjer, vertikala linjer, och så vidare.

### Aktiveringsfunktioner

Aktiveringsfunktioner tillämpas på varje feature map för att introducera icke-linearitet. Några vanliga aktiveringsfunktioner inkluderar:

- ReLU (Rectified Linear Unit)
- Sigmoid
- tanh
- Leaky ReLU
- Maxout
- ELU (Exponential Linear Unit)

### Pooling Layer

Pooling-lager används ofta efter konvolutionslager för att minska dimensionerna av feature maps. Det bidrar till att minska mängden information och fokuserar på viktiga särdrag.

Poolningoperationer (t.ex. max-pooling) agerar som en form av dimensionell nedbrytning av data.

Poolingen kan ses som att man zoomar ut lite från detaljerna i feature-maps och fångar endast det viktigaste.

