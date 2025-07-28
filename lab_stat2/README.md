# Analisi comparativa tra Stepwise e PCA per l'identificazione delle variabili chiave nella perdita di peso

**Corso:** Laboratorio di R  
**Università:** Università degli Studi di Milano-Bicocca  
**Anno Accademico:** 2023  
**Autori:** Aniello De Palma

## Descrizione del progetto

Il progetto ha come obiettivo l’individuazione delle principali variabili associate a una perdita di peso significativa (≥5%) in un campione di soggetti affetti da obesità. A tal fine, si è condotta un’analisi comparativa tra due approcci statistici di selezione e riduzione dimensionale: la regressione Stepwise e l’Analisi delle Componenti Principali (PCA).

Il dataset analizzato comprende **2.076 soggetti** e **562 variabili**, includendo misurazioni fisiologiche, cliniche e di laboratorio.

## Obiettivi dell’analisi

- Effettuare un’accurata pulizia del dataset, con gestione dei valori mancanti e variabili ridondanti.
- Definire un criterio di classificazione basato sulla perdita di peso significativa (variabile binaria).
- Applicare e confrontare due metodologie di riduzione/selezione delle variabili:
  - **Stepwise selection** basata su regressione logistica e BIC.
  - **PCA** con selezione delle componenti principali tramite elbow method e verifica empirica.
- Valutare la bontà di adattamento e la capacità predittiva dei due modelli.

## Metodologia

### Preprocessing

- Rimozione variabili con oltre il 25% di valori mancanti.
- Imputazione dei missing values.
- Creazione della variabile binaria di outcome (0 = perdita ≤5%, 1 = perdita >5%).

### Stepwise

- Divisione in train/test set.
- Costruzione del modello completo e modello nullo.
- Selezione delle variabili tramite criterio BIC.
- Stima finale di modello logit.

### PCA

- Standardizzazione delle covariate.
- Costruzione di componenti principali.
- Selezione delle PC più rilevanti.
- Individuazione delle variabili dominanti (loading > 0.7).
- Regressione logistica con variabili selezionate e verifica dei risultati.

## Risultati principali

- **Modello Stepwise**: ha selezionato 6 variabili statisticamente significative, tutte direttamente interpretabili e con ottime performance predittive.
- **Modello PCA**: ha selezionato un numero maggiore di variabili, non tutte però risultano significative nell’inferenza.
- Il modello derivante dalla Stepwise mostra una miglior bontà di adattamento e un minor errore di classificazione sia in-sample che out-of-sample.

## Conclusioni

L’analisi ha evidenziato che, in questo contesto, la regressione Stepwise è risultata più efficace e parsimoniosa rispetto all’approccio basato su PCA. Ciò conferma la validità della selezione automatica tradizionale in presenza di una variabile target ben definita, mentre la PCA rimane uno strumento utile ma più orientato alla riduzione informativa non supervisionata.

## File contenuti

- `Lab.Rmd`: script R Markdown con l'intero workflow analitico
- `Slide.pdf`: report completo dell'analisi in formato PDF

## Requisiti software

- R >= 4.0
- Pacchetti R: `tidyverse`, `MASS`, `FactoMineR`, `missForest`, `caret`, `glmnet`

---

Per ulteriori informazioni, contattare gli autori o aprire una issue nel repository.

