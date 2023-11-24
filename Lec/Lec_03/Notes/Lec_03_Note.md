# Lec-03 
**Datum: 2023-11-24**

## Underfitting vs Overfitting

Overfitting uppstår när modellen har anpassat sig för exakt till träningsdatan och därför presterar bättre än den borde.

Underfitting inträffar när modellen inte har lärt sig tillräckligt väl på träningsdatan och misslyckas med att generalisera.

Det optimala är att sträva efter en modell som ligger mittemellan, vilket kallas Rightfitting.

## Dataset-terminologi 

Det råder inte fullständig enighet om terminologin för dataset, så låt oss klargöra hur vi använder det i denna kurs (om inte annat anges):

| Typ          | Procent   |
|--------------|-----------|
| Träning      | 70%       |
| Test         | 15%       |
| Validering   | 15%       |

## Underfitting 

Det innebär att modellen inte har lyckats fånga mönstren i datan och har en otillräcklig inlärning.

## Overfitting 

Modellen har lärt sig träningsdatan för väl och misslyckas med att generalisera till osedda data. Det kan bero på att modellen är för komplex eller att datamängden är för liten.

## Identifiera över- eller underfitting

| Typ          | Träning-error  | Test-error  |
|--------------|----------------|-------------|
| Overfitting  | Låg            | Hög         |
| Underfitting | Hög            | Hög         |
| Rightfitting | Låg            | Låg         |

## Att undvika overfitting 

- Reducera modellens komplexitet genom att förenkla dess arkitektur.
- Förbättra datakvaliteten och öka datamängden genom dataaugmentering, datarening och reduktion av antalet inslagsfunktioner.

## Att undvika underfitting

- Öka modellens komplexitet genom att minska regleringen och utöka dess arkitektur.
- Förbättra datakvaliteten och öka datamängden genom dataaugmentering och andra metoder.

## Bias och Varians avvägning

Detta är ett klassiskt problem inom övervakad inlärning.

Hög bias innebär att modellen inte har lärt sig från datan och underfitar.

Hög varians innebär ofta att modellen har overfitat.

Vi strävar efter en modell med både låg bias och låg varians, vilket innebär att modellen har lärt sig av datan samtidigt som den generaliserar väl till osedda data.

## Regleringstekniker

### Early stopping

Genom att avbryta inlärningen innan modellen har lärt sig träningsdatan utantill, hoppas vi att den kommer att generalisera väl till osedda data.

Detta inträffar när felet för valideringsdatan, som modellen inte har tränats på, slutar minska.
