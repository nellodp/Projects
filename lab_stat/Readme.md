# Progetto Finale – Analisi e Previsione del PIL del Regno Unito  
### Aniello De Palma

Questo progetto è stato realizzato nell’ambito del corso di **Laboratorio di Statistica** e si propone di analizzare l’andamento del **PIL reale della Gran Bretagna** dal 1998 al 2022, individuando trend, stagionalità, anomalie e predittori economici rilevanti.  
L’analisi è stata svolta in **R Markdown** e pubblicata in formato HTML interattivo.

🔗 **Visualizza il progetto online**:  
[https://nellodp.github.io/Projects/lab_stat/DePalma_Aniello.html](https://nellodp.github.io/Projects/lab_stat/DePalma_Aniello.html)

---

## 🎯 Obiettivo

Analizzare la serie storica del **PIL britannico** per:
- individuare trend, stagionalità e outlier economici
- costruire modelli di regressione con variabili macroeconomiche
- confrontare modelli previsivi e stimare l’evoluzione futura del PIL

---

## 🧮 Dataset e fonti

- Serie storiche trimestrali (1998–2022) non destagionalizzate
- Dati economici ufficiali forniti da **FRED – Federal Reserve Bank of St. Louis**
- Indicatori: PIL reale, esportazioni, importazioni, CPI, popolazione attiva, consumi privati/pubblici, prezzi immobiliari

---

## 📊 Struttura dell’analisi

### 1. Introduzione e contesto
- Cos'è il PIL e perché è centrale nell’analisi macroeconomica
- Eventi chiave nel periodo: **crisi 2008**, **Brexit**, **Covid-19**

### 2. Pulizia della serie del PIL
- Verifica di **missing values**
- Rilevazione e correzione degli **outlier con `tsoutliers()`**
- Creazione di una nuova serie `gdp_noCovid` usando **`tsclean()`** per rimuovere gli effetti pandemici

### 3. Studio della stagionalità
- Analisi tramite **`ggseasonplot()`** e **`ggsubseriesplot()`**
- Confronto tra la serie originale e quella depurata da outlier
- Conferma della presenza di **stagionalità debole e trend forte**

### 4. Autocorrelazione e decomposizione
- Calcolo dell’**ACF**: alta correlazione a ritardi brevi
- Decomposizione STL robusta → il **trend è la componente dominante**

### 5. Regressione lineare con trend e stagionalità
- Modello `gdp ~ trend + season`
- Significatività delle stagioni, test F, analisi dei residui
- Confronto tra modello su serie grezza e serie pulita

### 6. Integrazione di predittori macroeconomici
- Importazioni, esportazioni, CPI, popolazione attiva, consumi, spesa pubblica, prezzi immobiliari
- Costruzione del dataset aggregato con `cbind()` e verifica multicollinearità

### 7. Regressione lineare multipla
- Stima del modello `gdp ~ exp + pce + gce + rpp + trend + season`
- Verifica R², significatività, residui, normalità (`shapiro.test`)
- Scelta del **modello ridotto** con variabili significative
- Confronto tramite AIC, BIC, test F e accuratezza predittiva

### 8. Previsioni

#### 8.1 Modelli di benchmark
- Mean, Naïve, Seasonal Naïve, Drift  
- Valutazione grafica e confronto degli errori sul test set (2019–2022)

#### 8.2 Modello finale di previsione
- Addestramento su 1998–2014, test su 2015–2018
- Previsioni con il **modello ridotto**
- Verifica visiva e confronto delle metriche di accuratezza

---

## 📦 Librerie R utilizzate

- `forecast`, `tidyverse`, `dygraphs`, `GGally`, `quantmod`, `gridExtra`, `readxl`, `rmdformats`

---

## 📈 Risultati chiave

- Il **trend è la componente dominante del PIL** nel lungo periodo
- Gli eventi straordinari come il **Covid-19** introducono forti distorsioni, ma sono gestibili con tecniche robuste
- Le **esportazioni, spesa privata, spesa pubblica e prezzi immobiliari** risultano predittori significativi
- Il **modello ridotto** migliora la predizione rispetto al modello completo
- I **modelli naïve** sono semplici ma meno efficaci nel cogliere il trend

---

## 👤 Autore

**Aniello De Palma**  
Corso di Laurea in Statistica  
Università degli Studi  
Anno Accademico 2024–2025

---

📌 *Progetto svolto a scopo accademico. Per approfondimenti o segnalazioni, contattami via GitHub.*
