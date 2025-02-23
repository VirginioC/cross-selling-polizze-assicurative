# Cross-selling di polizze assicurative

## Descrizione del progetto
Questo progetto, realizzato durante il Master in Data Science di ProfessionAI, si propone di sviluppare col linguaggio **Python** e la libreria **scikit-learn** (ambiente **Google Colab**), un modello di machine learning per identificare i clienti esistenti di una compagnia assicurativa che potrebbero essere interessati a sottoscrivere una polizza aggiuntiva per il loro veicolo. L'obiettivo è ottimizzare le strategie di cross-selling, migliorando l'efficacia delle campagne di marketing e aumentando il tasso di conversione.

### Obiettivi specifici
- Predire la propensione dei clienti con un'assicurazione sanitaria ad acquistare una polizza veicoli.
- Supportare le decisioni strategiche di marketing con analisi basate sui dati.
- Incrementare i ricavi e migliorare la penetrazione di mercato.

## Struttura del progetto
Il progetto è organizzato nelle seguenti fasi:

1. **Analisi esplorativa**:
   - Studio del dataset **`insurance_cross_sell`** (incluso nel repository) contenente 381109 samples con le seguenti features sui clienti: `id`, `Gender`, `Age`, `Driving_License`, `Region_Code`, `Previously_Insured`, `Vehicle_Age`, `Vehicle_Damage`, `Annual_Premium`, `Policy_Sales_Channel`, `Vintage` e `Response`. L'ultima variabile, **`Response`**, rappresenta il target binario (1: cliente interessato, 0: non interessato).
   - Identificazione di un consistente **sbilanciamento delle classi del target**: 87.74% dei clienti appartiene alla classe negativa.
     
2. **Preprocessing dei dati**:
   - Feature encoding delle variabili qualitative tramite label encoding e one-hot encoding.
  
3. **Modellazione**:
   - Sviluppo di modelli di **Regressione Logistica** per la **classificazione binaria** con diverse configurazioni:
     
     - Con/senza feature selection.
     - Con/senza tecniche per bilanciare le classi:
       
       - Parametro `class_weight="balanced"`.
       - `Oversampling` della classe positiva.

4. **Addestramento e valutazione**:
   - Addestramento e valutazione dei modelli tramite **cross-validation** (standardizzazione delle features).
   - Priorità alla massimizzazione della **recall della classe positiva**.
   - Scelta del modello "migliore".
  
## Risultati sintetici
Il modello migliore è il **Modello 3** (features selezionate e bilanciamento delle classi tramite `class_weight="balanced"`), con cui si ottengono le seguenti performance sul test set:

- **Accuracy**: 63.92 %  
- **Recall** (classe positiva): 97.57 %  
- **Precision** (classe positiva): 25.05 %  
- **AUC**: 83 %

Con queste prestazioni si riducono quasi totalmente i falsi negativi grazie ad una **recall molto alta**, permettendo alla compagnia di assicurazioni di identificare la maggior parte dei potenziali clienti interessati alla polizza aggiuntiva, anche se a scapito di una bassa precisione.

## Tecnologie utilizzate
- **Linguaggio**: Python
- **Ambiente di sviluppo**: Google Colab (Jupyter Notebook)
- **Librerie**:
   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scikit-learn`
   - `imblearn`

## Utilizzo  
1. Scarica o clona il repository.
2. Apri il file `cross-selling_polizze_assicurative.ipynb` su Google Colab o altri ambienti compatibili con Jupyter Notebook.
3. Esegui il codice passo-passo per ottenere i risultati.
4. Il dataset utilizzato (`insurance_cross_sell`) è incluso nel repository.

## Autore
[Virginio Cocciaglia](https://github.com/VirginioC)

---
