CAP1
molto piu' lungo, devi spiegare bene tutto quello che serve per andare avanti quindi in dettaglio formule,
strategie (molte di piu'?), buy / hold da battere ecc
TIME SERIES da spiegare e tutte le definizioni di qualsiasi termine

CAP2
stato arte test + sentyment

Sentyment magari allunga? anche se non c'e' piu' molto da dire visto che e' black box...
tot 1+2 = 40 pag


# TODO
didascalie sbagliate, cambia font e numero figura
bold e cose in giro per migliorare leggibilita'
piu immagini
Esempio numerico creazione candele
piu' strategie

- strategie devono battere buy hold mai detto!

ora c'e' nuovo capitolo 3 con cripto; devi cambiare in giro quando dici (di piu' nel capitolo 3) che prima era eleborazione dati ma ora e' il 4


# TODO
spiegare questione stage e aggiunta nuovi moduli da me?

in sentyment o test, devi chiarire perche' si tratta di una decision support ai.
Non e' propriamente decision perche' quelle sono tipo quelle mediche e segono decision tree, qua invece cerca pattern
e fitta quelli, però alla fine ti dice quando comprare e vendere.
E qua puoi citare cos'e' un decision support: https://www.researchgate.net/publication/321600307_Intelligent_Decision_Making_An_AI-Based_Approach

- test for decision ai:
  spiega com'è diverso da quello visto in intro, (articolo golden standard ecc)
  perche' la tua Ai e' diversa? no classificatore
  e come hai deciso di farlo TU
- spiega come hai testato manualmente con max prof e ai genetic
  (cioe, a parte intro bella, come si deve guardare a mano il dato e testarlo 
   con grafici vs max e vs altri)

===============================================================================0
# IDEE

CAP 3 creazione candele, indicatori e strategie. La parte numerica dei dati

CAP 4 multi-armed bandit e tua implementazione / risultati

POI fai girare i veri test online e offline prima di andare avanti a scrivere

didascalie e tabelle: nomi

trade-off fra avere tanti dati (step piccolo) e far fare abbastanza operazioni alla AI
sapendo che poi, step corrisponde a periodo di scambio ai. Dopo test empirici.... 200 lascia fare abbastanza operazioni alle AI (media tempo fra un buy e sell?)

Alla fine confronto fra performance di:
- AI con meta-learner
- AI casuale
- AI piu promettente di tutte

Serve sistema (anche a manina) che switcha le AI secondo quanto deciso da meta-learner, mentre calcola perf / gain per confronto finale con le altre
NO MAX GAIN E GENETIC

CAP 4
XXBT
- AI trigger a confronto (un paio)
- AI trigger generali

ETHEUR
- AI gain (10) a confronto
- Prezzi originali

Spiega come il lavoro e' applicato soltanto a una valuta per volta, o meglio, una soltanto (XXBT), ma i test 
funzionano anche per altre monete (infatti esempio con ETH e POI XXBT)
Ma poi ti concentri solo su XXBT, quindi grafico di ETHEUR poi lo devi rifari in XXBT (autotest)

PERFORMANCE (XXBT)
- PLOT non piu gain ma funzione obiettivo meta-learner (performance) calcolata ogni tot step
- anche valori puntuali di questa funzione vanno bene, esempio media finale di performance per ciascuna AI

Cambia calcolo performance in meta-learner: non calcolare di nuovo da zero ogni step, ma usa il valore cumulativo di tutto il dataset indietro, non solo finestra step!



COSA HAI GIA
autotest fa andare performance delle AI in step di 200, ma poi serve da farlo andare con xbt dataset piu grosso (occhio a allineamento con le ai)
  trade statistics ha funzioni gain e performance
mab sempre il solito, da fare andare con dataset grosso
stats e' servito per tracciare i grafici di prices e triggers, nient altro


Hai un immagine con le performance ma solo in 5 step... e' un esempio e non so se devi metterlo in tesi, meglio aspettare il dataset grosso







NB!!!!!!!!!!!
=============
- non hai mai detto che ci sono ste 12 AI PER OGNI MONETA
- appena inizi con meta-learner: MOTIVAZIONI. Perche' serve un learner invece che scegliere ogni tot
  la AI con statistica migliore? (solo guardando il valore)
  1) Intanto se hai un valore alto ogni tanto non e' detto che sia migliore una AI
     POi ogni quanto cambieresti? C'e' bisogno di cambiare abbastanza spesso perche' una di botto potrebbe peggorare, non si ha garanzie
     e poi con learner puoi adattarti ai nuovi dati, conta di piu' il presente che il passato, e puoi scegliere ogni quanto fare lo scambio
- Ogni quanto fare lo scambio? 
  Parametro che va RICAVATO: Una volta che hai il grafico SCELTE (scrivi csv pandas) calcola la media di quanto passa da un cambio AI all'altro
  (ogni quanto una AI mugliore viene sorpassata) e hai trovato l'intervallo di temop fra una run del learner e l'altra
- Nei test assoluti, calcola un guadagno totale prodotto dalla AI da 2014 a 2020. Poi confronta con le singole AI oppure con SOLO LA MIGLIORE
- Non hai mai parlato di n_eexperiments (20).... Come cambia il risultato? deve essere per forza 10000?
- buy sell -1 1 scambiati ogni tanto


PARAMS
perfetto con performance = profit (tagliato a 50 max)
step = 250, start = 5000, n_exp = 20 / 100 / 1000

1) togli via meta 2014 in entrambi
2) step piu ampio (picchi solo di durata step): analisi per step migliore (quante operazioni riesce a fare in uno step?)


=====
# PROGRAMMI DA FARE GIRARE ANCORA
- 2 o 3 mab che si fermano dove c'e' un picco di un'altra AI (non 0) con alto eps, per vedere se sceglie quella col picco
- ultimo mab in un punto che vuoi tu, ma con altissimo n_experiment (1k o 10k, doveva gia farlo da un po ma non è andato)

- calcolo finale fra performance AI0 e performance META (anche solo un valore numerico e basta)
  magari confronta anche altre AI oltre a ste 2
  performance media delle singole VS finale meta


- non riesce a beccare sto piccooooooo!!! Magari considera solo la storia piu' recente e non ogni volta tutto il dataset? Considera solo l'ultimo anno, tipo?
  Prova picco finale (AI3) o picco 2017 (AI7) usando meno dati.... E eps 0.6?

========
DA SISTEMARE IN GIRO
gain non e' vera formula guadagno, ma ricavo singole operazioni. Devi dirlo

test per sentyment ai: non ci sono test comparativi e qualitativi, solo comparativi.... i qualitativi son da camviare, è solo una misura di performance finale....

performance in realta' hai usato solo profit... cerca in giro se non torna

buy hold non e' veramente "da battere", non e' minimale e non fa schifo... nel lungo periodo su prezzi in salita vince sempre! Sistema INTRO e anche in giro

-----> Sentyment non e' "composta" da 10 AI ma a ogni ciclo ne produce 10 nuove e si sceglie la migliore. Cicli di qialche settimana MAI DETTO!

RANDOM ALGORITHM mai parlato... Sostituito dalle strategie per fare confronto? o ci vuole?

figura 20 -> figura 22

# figure bandit choice allineate

bandit final choice (100 / 1000 esperimenti a 0.1)

# risultati medieeee

# interessante che metalearn sceglie come "seconda" AI verde mentre invece le medie e altro metterebbero come seconda la grigia



Mean performance with period 720
buy hold: 0.0
macd: 0.5733546730655771
rsi: 1.9881815197232546
sentyment: 0.7743340335712756
Mean profit with period 720
buy hold: 0.4184781637772894
macd: -0.4436644813936811
rsi: -0.042681071786188074
sentyment: -0.07103362472806332

MAX PROF
Mean performance with period 100
buy hold: 0.0
macd: 0.6191815184336097
rsi: 2.0131376833638903
sentyment: 0.9684276489818997
max profit: 44.89472911611406
Mean profit with period 100
buy hold: 0.029724063309851535
macd: -0.138792933904424
rsi: -0.03341234226116994
sentyment: -0.02061835434600789
max profit: 0.8391547687364111

