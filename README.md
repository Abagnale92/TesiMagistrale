# TesiMagistrale
# Identificazione di attacchi al CAN-bus mediante features temporali e tecniche di Machine-Learning in ambito Automotive
Le automobili sono i mezzi più utilizzati nel mondo, nel corso degli anni sono state apportate diverse modifiche e miglioramenti infatti le auto più moderne dispongono di molti sistemi elettronici che collegati tra loro compongono una vera e propria rete su cui viaggiano i dati.

Il CAN è un protocollo basato su comunicazione seriale che definisce uno standard di comunicazione real-time tra sensori, attuatori, controllori e altri nodi, è implementato come un bus condiviso in cui ogni nodo presente sulla rete è fisicamente collegato alla linea di comunicazione.

L’aggiunta sempre più ingente di computer per la gestione di aspetti anche critici del veicolo ha inevitabilmente portato con sé problemi di sicurezza informatica.

La maggior parte degli attacchi informatici consiste nella contraffazione ed invio indiscriminato di messaggi (frame) all’interno della rete CAN dell’automobile con lo scopo di compromettere in maniera vantaggiosa per l’aggressore il funzionamento del veicolo.
Nel lavoro di tesi, si vogliono identificare gli attacchi che possono essere effettuati sul CAN-bus. Per fare ciò, viene utilizzato un set di dati che include attacchi come: Denial of Service, Fuzzy e Spoofing, ottenuti registrando il traffico CAN attraverso la porta di on-board diagnostics (OBD-II) da un veicolo reale mentre si stava eseguendo un attacco di tipo injection message.

L’obiettivo dunque è quello di riuscire ad estrapolare delle informazioni in modo tale da poter riconoscere degli schemi temporali che delineano gli attacchi, facendo una netta distinzione tra malware e goodware.

Per raggiungere tale obiettivo vengono utilizzate due principali librerie di Python: Pandas per la manipolazione e l’analisi dei dati e Keras per la progettazione di reti neurali profonde.

Viene quindi realizzato un modello di rete neurale ricorrente, la Long Short Term Memory (LSTM) che è adatta allo scopo poiché crea una memoria che permette di passare l’output di un’esecuzione della rete alla esecuzione successiva; avendo in ingresso dei dati sequenziali, la LSTM riesce ad estrarre le informazioni più significative e quindi a ricavarne degli schemi che permettono di riconoscere se un messaggio è malevolo o benevolo.

Gli indici utilizzati per valutare la bontà delle previsioni esposte, sono:
- L’errore quadratico medio che viene utilizzato per quantificare la qualità della stima effettuata;
- La matrice di confusione che consente di capire le prestazioni del classificatore, riuscendo ad individuare in modo immediato se il sistema confonde le classi da predire;
- L’accuratezza che viene utilizzata per quantificare quanto bene funzioni il modello nell’identificare le classi.
Dalla ricerca svolta è emerso che, nella classificazione degli attacchi, i dati più “difficili” da distinguere tra malware e goodware sono risultati gli attacchi Denial of Services mentre, per gli altri tipi di attacchi, l’errore è stata di poca rilevanza data la grossa mole dei campioni forniti.

Dalle analisi effettuate, si è resa nota l’importanza di selezionare con cura le diverse grandezze in input, utilizzando solo quelle che sono strettamente correlate fra loro da un rapporto di causalità rispetto all’output desiderato e la necessità di avere un campione di dati quanto più grande possibile, in modo da poter addestrare efficacemente il modello per sviluppare la capacità di generalizzare e quindi di fornire una previsione affidabile.

La presente tesi ha dimostrato la solidità delle predizioni ottenibili grazie all’utilizzo del Machine Learning, che si è rivelato in grado di fornire un efficace strumento di supporto nel campo della classificazione di attacchi in ambito automotive.
