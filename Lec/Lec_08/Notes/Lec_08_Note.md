# Lec-08 
**Datum: 2023-12-11**

## Transfer Learning

Transfer learning innebär att man utnyttjar en redan existerande modell som är tränad för att lösa vissa problem, och sedan tränar om denna modell för att lösa ett nytt, liknande problem.

Det finns tillgängliga open source-vikter för olika modeller som vem som helst kan använda för att träna sina egna modeller. Transfer learning används främst inom bild- och textanalys.

## Kända Modeller

### Bilder

- VGG16
- ResNet
- AlexNet
- YOLO

### Text

- BERT
- ERNIE
- ELMO
- GPT
- T5

## Metoder för Transfer Learning

Det finns två huvudsakliga metoder för transfer learning:

### Feature Extraction

Vid feature extraction behåller man de befintliga konvolutionslagren samt input/flatten-lagren, men byter ut klassifieringslagren.

**Fördelar och nackdelar:**

- Fördelar: lämpligt vid mindre dataset, begränsningar i beräkningskraft, likheter mellan dataseten.
- Nackdelar: begränsad kapacitet vid mindre datamängd och beräkningskraft samt krav på likheter mellan de två dataseten.

### Fine-Tuning

Fine-tuning innebär att man väljer vilka lager bakåt i modellen som man vill träna om, där man vanligtvis undviker att ta bort de första lagren. Man justerar oftast en mindre del av modellen beroende på behov.

**Fördelar och nackdelar:**

- Fördelar: passar bra vid större dataset, tillgång till betydande beräkningskraft, kan hantera olikheter mellan dataseten.
- Nackdelar: kräver större mängd data och beräkningskraft, samt behov av att hantera olikheter i dataseten.

Vid användningen av transfer learning refererar man ofta till "source" och "target" som representerar de olika dataseten som används.
