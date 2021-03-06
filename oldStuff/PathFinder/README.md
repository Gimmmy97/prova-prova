# PathFinder

Labirinto 60x40, 35% possibilità che un quadrato sia un muro, limite fps non aggiunto

## How To:
- scaricare [librerie p5](https://github.com/Gimmmy97/prova-prova/tree/master/challenge/librerie%20p5), sketch.js e index.html
- double click su index.html per aprire il programma nel browser 

### About:
L'algoritmo da un valore ad ogni quadratino che va da 0 per i muri a 1 per il quadrato d'arrivo e valuta ad ogni passo i
4 quadrati attorno a sé (N/S/E/W), preferendo quadrati non ancora visitati. In caso non ci fossero vie d'uscita da un
percorso i quadratini vengono contrassegnati di rosso. Ad ogni passaggio su una strada già battuta il colore si scurisce 
(scala di blu).

L'algoritmo ora preferisce, in caso di parità fra strade possibiliti, avvicinarsi al bersaglio:
se si trova ad esempio 15 caselle ad Est e 9 a Nord del bersaglio e trovandosi una casella bianca ad Ovest ed una bianca a Sud preferirà andare ad Ovest per diminuire il gap maggiore (orizzontale in questo caso).

Il bersaglio viene creato in un punto casuale del labirinto ogni volta che la pagina viene caricata.

#### Valori:
- -0.001 quadrati fuori dai bordi, per non scegliere mai di uscire
- 0 muri (neri)
- 0.1 vicolo cieco (rosso)
- 0.15 - 0.85 strada percorsa da 1 a 15 volte (scala di blu)
- 0.9 quadratini percorribili non visitati (bianchi)
- 1 arrivo (verde)
- (La partenza inizia con un valore di circa 0.85-0.9 ed è viola, in realtà per il momento il colore che assume dipende dalle caselle che si trova attorno e può anche diventare subito un vicolo cieco (rosso))

### Pulsanti (v3.0):
Aggiunti tre pulsanti: Nuovo, Riprova, opzione vicoli ciechi (fine partita)
- Nuovo: viene creato un nuovo labirinto delle stesse dimensioni del precedente azzerando tutti i parametri precedenti
- Riprova: viene riutilizzato lo stesso labirinto e l'algoritmo cerca una strada (al momento percorre la stessa visto che la decisione fra le scelte possibili rimane uguale)
- Vicoli Ciechi (switch): inizia su ON (sfondo verde) e in questo caso se il PathFinder si dovesse trovare fra 4 vicoli ciechi la ricerca si conclude con una sconfitta, tuttavia a volte l'algoritmo può ritrovarsi chiuso in un punto nonostante una strada reale esista (solitamente passando da molto lontano da dove si trova il bersaglio),
se su OFF (sfondo rosso) il PathFinder continua a cercare strade alternative finchè lo switch non viene riportato su ON, senza curarsi della presenza dei vicoli ciechi sul suo cammino

### ToDo:
- resizability in base alle dimensioni dello schermo (per mobile)
- rendere il numero di righe e colonne, le mosse al secondo e la percentuale di muri creati modificabile
e caricare un nuovo labirinto una volta finito
- salvare labirinti
- provare lo stesso labirinto con altri algoritmi (non ancora implementati)
