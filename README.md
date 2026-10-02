# Progetto di Analisi Vendite e Forecasting con Power BI

In questo repository condivido un progetto pratico di Business Intelligence che ho sviluppato interamente da zero per esercitarmi sulle funzionalità avanzate di Power BI Desktop. 

**Nota sul Dataset:** L'intero database utilizzato per questo progetto è stato costruito da me. Ho generato dei *mock data* (dati fittizi) strutturati ad hoc per simulare uno scenario aziendale realistico (vendite, costi, canali, categorie e resi) e avere una base dati su cui testare l'Intelligenza Artificiale e le funzioni predittive di Power BI.

## Obiettivo del Progetto e Competenze
L'obiettivo era creare un report per monitorare le vendite globali, esplorare i centri di costo e capire le cause dei resi, mantenendo un'interfaccia pulita e minimale.
* **Strumenti:** Power BI Desktop
* **Competenze messe in pratica:** Creazione Dataset, Time Series Forecasting, Esplorazione dati con AI (Key Influencers, Decomposition Tree), Data Storytelling e UI/UX (Drill-through, Segnalibri, Tooltip nascosti). *Nessun utilizzo di DAX o codici complessi, focus totale su strumenti nativi e design.*

## Cosa ho implementato nel dettaglio

### 1. Modelli Predittivi e AI (Pagina "AI & Analytics")
* **Forecasting delle vendite (Risoluzione anomalie):** Ho creato una proiezione sui ricavi futuri. Poiché i miei dati fittizi presentavano irregolarità mensili (es. mesi a zero e picchi anomali), ho ristrutturato la linea temporale raggruppando i dati per trimestri (Quarter). Questo ha permesso all'algoritmo di generare una previsione stabile con un intervallo di confidenza (Upper/Lower bound) al 95%.
* **Ricerca delle cause (Key Influencers):** Ho usato l'algoritmo di regressione logistica integrato per analizzare le cause dei resi (*Reso = Sì*). Il modello ha individuato in automatico che un calo della soddisfazione del cliente è il fattore principale che fa impennare la probabilità di reso.
* **Esplorazione dei costi (Decomposition Tree):** Tramite l'Albero di Scomposizione, ho dato all'utente finale la libertà di espandere e analizzare i costi aziendali, scegliendo dinamicamente se incrociarli per canale di vendita, nazione o prodotto.

### 2. Interattività ed Esperienza Utente (Le funzioni dietro agli screenshot)
Poiché gli screenshot qui sotto sono statici, ecco come ho strutturato l'interattività del report per l'utente finale:
* **Tooltip personalizzati (Mappa Pagina 1):** Per non riempire la mappa globale di numeri, ho costruito una pagina nascosta che funge da *Descrizione Comando*. Passando il mouse su una singola nazione nel mappamondo, appare in sovrimpressione una micro-dashboard fluttuante che mostra le Vendite Totali, la Soddisfazione Media e un grafico a barre in pila diviso per Prodotto e Canale.
* **Drill-through (Passaggio a livello di dettaglio):** Dalla Mappa principale, l'utente può fare clic col tasto destro su una specifica città e usare il comando Drill-through. Questo lo "teletrasporta" istantaneamente alla Pagina 3, dove troverà una matrice gerarchica (Categoria > Prodotto > Reso) già filtrata esclusivamente per la città selezionata.
* **Gestione filtri con Segnalibri (Bookmarks):** Sulla pagina del Drill-through ho inserito un pulsante verde di "Reset". Tramite la gestione dei Segnalibri, questo tasto permette di pulire istantaneamente i filtri attivati dalla navigazione, ripristinando la matrice allo stato originale senza dover usare i controlli base di Power BI.
* **Design Minimalista:** Ho valutato l'inserimento di un menu di navigazione laterale (Page Navigator), ma ho optato per rimuoverlo e mantenere la navigazione a schede standard per rispettare la regola del "less is more" e dare più respiro ai grafici.

## Anteprima del Report

**Executive Overview**
<img width="1772" height="737" alt="Screenshot 2026-10-02 155958" src="https://github.com/user-attachments/assets/d788c29a-7310-4ce7-972e-234ef8c702cb" />

**AI & Analytics** *(Key Influencers, Scomposizione e Forecast)*  
<img width="1792" height="737" alt="Screenshot 2026-10-02 155019" src="https://github.com/user-attachments/assets/44c38eb6-7e0f-4e5f-938e-46414f38a002" />

**Dettagli Città** *(Pagina di atterraggio del Drill-through)*
<img width="1682" height="741" alt="Screenshot 2026-10-02 155114" src="https://github.com/user-attachments/assets/4ff3a20b-ae4d-43db-8eeb-fd9cad38d82a" />




