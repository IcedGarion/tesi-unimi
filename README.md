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
# TODO
CAP 3 creazione candele, indicatori e strategie. La parte numerica dei dati

CAP 4 multi-armed bandit e tua implementazione / risultati

POI fai girare i veri test online e offline prima di andare avanti a scrivere

didascalie e tabelle: nomi


# IDEE cap 4

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
- Nei test assoluti, calcola un guadagno totale prodotto dalla AI da 2014 a 2020.
