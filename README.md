# Tecniche di Machine Learning e Deep Learning per la Predizione dei Fattori di Rischio del Tumore Cervicale

## Introduzione
Questo progetto implementa una pipeline completa di Machine Learning e Deep Learning per prevedere la necessità di una biopsia basandosi su fattori di rischio clinici e demografici. Il dataset utilizzato è il "Cervical Cancer (Risk Factors)" proveniente dal repository UCI Machine Learning.

## Descrizione del progetto
L'obiettivo è analizzare i fattori di rischio (fumo, contraccettivi, malattie sessualmente trasmissibili, ecc.) per classificare i pazienti che necessitano di una biopsia. Il progetto affronta sfide comuni nel settore medicale come:
- gestione di dati mancanti;
- dataset fortemente sbilanciato;
- riduzione della dimensionalità per la visualizzazione.

**Dataset**: *Cervical Cancer (Risk Factors)* - UCI Machine Learning Repository (ID: 383)

**Istanze:** 858

**Feature:** 36 (informazioni demografiche, abitudini, anamnesi medica).

### Tecnologie utilizzate
**Linguaggio:** Python

**Analisi Dati:** pandas, numpy

**Visualizzazione:** matplotlib, seaborn

**Machine Learning:** scikit-learn (PCA, Random Forest, SVM, Logistic Regression, Naive Bayes)

**Deep Learning:** TensorFlow & Keras + TensorBoard


### Pipeline dei dati
#### 1. Preprocessing dei dati
- **Pulizia:** sostituzione dei caratteri speciali (?) con NaN.
- **Imputazione:** riempimento dei valori mancanti utilizzando la mediana delle colonne.
- **Feature Selection:** rimozione automatica delle colonne costanti (senza varianza).
- **Standardizzazione:** utilizzo di StandardScaler per normalizzare le feature prima dell'input nei modelli.

#### 2. Analisi Esplorativa (EDA) & PCA
Il codice include un'analisi di correlazione e una Principal Component Analysis (PCA) per ridurre i dati a 2 dimensioni, permettendo la visualizzazione dei cluster dei pazienti (Biopsy vs No Biopsy).

### Modelli Implementati
Il progetto confronta diversi approcci per trovare il miglior compromesso tra precisione e recall.
- **Gaussian Naïve Bayes:** baseline probabilistica.
- **Logistic Regression:** con bilanciamento dei pesi delle classi.
- **Support Vector Machine (SVM):** con kernel RBF.
- **Random Forest:** utilizzato anche per estrarre la Feature Importance.
- **Neural Network (MLP):** rete neurale densa realizzata con Keras.

### Risultati e Performance
Ogni modello viene valutato attraverso:
- matrice di Confusione per visualizzare falsi positivi/negativi;
- report di Classificazione (Precision, Recall, F1-Score);
- curva ROC e punteggio AUC per misurare la capacità discriminante del modello.

Per una spiegazione dettagliata della metodologia utilizzata, dell'analisi statistica e dei risultati ottenuti, consulta l'elaborato completo: **[Elaborato Progettuale - Tecniche di Machine Learning e Deep Learning per la Predizione dei Fattori di Rischio del Tumore Cervicale](./AAAP_elaborato.pdf)**

## Installazione
### 1. Clona la repository
```
git clone https://github.com/danieleiodice/AAAP_progetto.git
cd AAAP_progetto
```

### 2. Installa le dipendenze
```
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow ucimlrepo
```

### 3. Esegui il notebook
```
python main.ipynb
```

### 4. Visualizza i log di addestramento della rete neurale
```
tensorboard --logdir logs/dl_biopsy
```
