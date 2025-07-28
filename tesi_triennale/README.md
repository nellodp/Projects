# Analisi Statistica delle Abitudini e del Profilo dei Pazienti Diabetici

**Corso di Laurea:** Statistica per i Big Data  
**Università degli Studi di Salerno**  
**Anno Accademico:** 2022/2023  
**Candidato:** Aniello De Palma  
**Relatore:** Prof.ssa Marialuisa Restaino

## Descrizione del lavoro

Il presente elaborato si propone di analizzare le abitudini e le caratteristiche socio-sanitarie dei pazienti affetti da diabete mellito, con l’obiettivo di individuare i principali fattori di rischio associati all’insorgenza della patologia. L’analisi si basa sui dati raccolti dal **Behavioral Risk Factor Surveillance System (BRFSS)**, un'indagine epidemiologica condotta annualmente dal CDC, che per l’anno in esame ha coinvolto un campione di oltre 250.000 individui.

## Obiettivi

- Identificare i fattori socio-demografici e comportamentali correlati al diabete.
- Applicare e confrontare modelli di regressione per variabili dipendenti binarie (*logit*, *probit*, *cloglog*).
- Valutare le performance predittive dei modelli mediante metriche appropriate (AIC, BIC, ROC curve, pseudo-R², Youden Index).
- Discutere le implicazioni dei risultati nell’ambito della prevenzione e gestione della malattia.

## Metodologia

L’analisi prevede una fase iniziale di pulizia e rielaborazione del dataset (data preprocessing), seguita da un’esplorazione statistica descrittiva (EDA). Successivamente sono stati stimati tre modelli di regressione per esaminare la probabilità di insorgenza del diabete in funzione di variabili esplicative quali età, BMI, abitudini alimentari, attività fisica, condizioni cliniche pregresse, ecc.

Le performance dei modelli sono state confrontate sia in termini di bontà di adattamento sia attraverso misure di classificazione su un set di test, con particolare attenzione alla gestione del bilanciamento tra sensibilità e specificità.

## Risultati

- L’età, il BMI, l’ipertensione e il colesterolo elevato sono risultati significativamente associati alla presenza di diabete.
- Il modello **logit** ha mostrato la miglior sensibilità predittiva nel contesto esaminato.
- Il modello **probit** ha ottenuto valori inferiori di AIC e BIC, suggerendo una migliore capacità di adattamento.
- Il modello **cloglog** ha presentato il minor tasso di errore sul test set, confermandosi efficace in presenza di classi sbilanciate.

## Struttura del documento

- **Capitolo 1:** Inquadramento clinico e statistico del diabete mellito  
- **Capitolo 2:** Approfondimento metodologico sui modelli binari  
- **Capitolo 3:** Analisi empirica e risultati  
- **Conclusioni:** Discussione finale, limiti dello studio e prospettive future

## Riferimenti principali

- Centers for Disease Control and Prevention – Behavioral Risk Factor Surveillance System (BRFSS)  
- Tukey, J. W. (1977). *Exploratory Data Analysis*  
- James, G., Witten, D., Hastie, T., Tibshirani, R. (2013). *An Introduction to Statistical Learning*
