# ERS

### Indice dei contenuti

+ **Chi siamo**
+ **Il progetto**
+ **Il problema**
+ **L'idea**



## Chi siamo

Siamo un gruppo di studenti di Smart Robot all'ITIS Delpozzo di Cuneo. Da sempre siamo appassionati di robotica e informatica, con un occhio sempre aperto alla sostenibilità ambientale! 

Ci siamo avvicinati alla robotica l'anno scorso arrivando in finale alla **Nao Challenge**, competizione a cui il nostro istituto partecipa già da alcuni anni. Ispirati dalle ampie possibilità forniteci dalla materia, abbiamo voluto sfidarci nel partecipare alle **Olimpiadi di Robotica**, stimolati dal tema scelto per l'edizione di quest'anno:

>  La competizione è dedicata alla ideazione, progettazione e costruzione di prototipi di robot in grado di svolgere funzioni utili al miglioramento delle condizioni ambientali del nostro pianeta e/o delle condizioni di vita dell'uomo su di esso.



#### I nostri ruoli

+ **Pietro Jomini**	`team leader` `programmer` 
+ **Francesco bruno**	`programmer` `robot manufacturer`
+ **Matteo Badoino**	`robot manufacturer` 
+ **Gianluca Bernardi**	 `external member` `3D designer`
+ **Simone Nardi**	`external member` `designer` `public relation`



L'**ITIS Delpozzo**, durante il 4° anno, fornisce agli studenti di Smart Robot la possibilità di prendere parte ad un percorso di PCTO interna in collaborazione con l'**IIT** di Genova. Il supporto dell'IIT e dell'ITIS ci permette di avere accesso a tecnologie avanzate, in modo da poter sviluppare al massimo le nostre idee e da poter assaggiare tecnologie del mondo "reale".



## Il progetto

Come studenti, ci siamo resi conto che non possiamo cambiare lo _state of art_ della tecnologia e della ricerca. Possiamo solo sperare di far cambiare idea alle persone, allenare ad un uso consapevole della tecnologia moderna.

L'obiettivo del nostro progetto è sensibilizzare alla guida ecologica.

> We host real-word races, were the winner is fast and ecologically sustainable.



Crediamo inoltre che i nomi siano importanti. Per questo abbiamo creato il nostro per contenere, al suo interno, il cuore del nostro progetto:

**E**co **R**ace(s) **S**imulator, **ERS**



## Il problema

#### La categoria

Abbiamo scelto la categoria **Terra** in quanto la più affina ai nostri ambienti, dunque quella in cui pensiamo di poter essere più efficaci nella salvaguardia delle condizioni ambientali del nostro pianeta. Soluzioni applicate alla Terra possono facilmente applicare migliorie anche agli ambienti acquatici e aerei, essendo il suolo il nostro ambiente originale, da cui influiamo come umani sugli altri ecosistemi.



#### Il problema

Le emissioni di CO2 derivanti dalla combustione di combustibili fossili continuano ad aumentare. La CO2 è il principale tra i gas serra, autori dell'effetto serra e, di conseguenza, del riscaldamento globale e della distruzione dell'ecosistema. Buona parte di queste emissioni sono generate dai veicoli a combustione, e il 60% di queste emissioni deriva dalle autovetture.

Nel 1997, il protocollo di Kyoto proponeva l'obiettivo di ridurre l'impatto umano sul riscaldamento globale, riducendo le emissioni di gas serra. Eppure, ci vollero quasi 15 anni per ottenere risultati, e tuttora non è stato raggiunto il "livello che impedirebbe pericolose interferenze antropogeniche con il sistema climatico" sperato in fase di progettazione.

A inizio 2020, sarebbero dovuti entrare in vigore i nuovi limiti UE per le emissioni di CO2 nelle autovetture, di 95 g/km. Sarebbe stato il limite più severo mai imposto, e le grandi case automobilistiche hanno fatto forti pressioni per rimandarne l'applicazione a inizio 2021. Nel 2030, il limite sarà abbassato a 59 g/km, meno della metà della media odierna.

Al momento la quantità di CO2 nell'atmosfera è la più alta mai registrata, superando le 400ppm: negli ultimi 800 000 anni, il limite non era mai salito al di sopra delle 300ppm. Nonostante gli sforzi di superpotenze come l'EU-28, le emissioni continuano ad aumentare, e dal 2017 al 2019 la curva di incremento è salita rispetto al decennio precedente.



## L'idea

Come studenti, ci siamo resi conto che non possiamo cambiare lo _state of art_ della tecnologia e della ricerca. Possiamo solo sperare di far cambiare idea alle persone, allenare ad un uso consapevole della tecnologia moderna: l'obiettivo del nostro progetto è sensibilizzare alla guida ecologica.

Abbiamo intenzione di realizzare un rover terrestre che permetta di partecipare a gare di corsa ecologiche. Per scalare la classifica del nostro gioco, non basta essere veloci: bisogna saper guidare bene. Un controllo costante sulla coppia simulata ci permette di applicare un "fattore ecologico" ai tempi ottenuti dai giocatori sui tracciati.

Il rapporto tra coppia motore e consumi è ottimale in un determinato range di RPM, che noi abbiamo astratto dai dati di alcune tra le più comuni autovetture del mondo reale:

```
Power: ~ 63KW
Max engine torque: ~ 200NM
Max  RPM: 3500 -> T: ~ 171NM
Best RPM: 3000 -> T: ~ 200NM
Min  RPM: 2500 -> T: ~ 240NM

_____|_2500__|__3000__|__3500__| RPM
1/10 | 28.80 | 34.56  | 40.32  |
1/7  | 41.14 | 49.37  | 57.60  |
1/5  | 57.60 | 69.12  | 80.64  |
1/3  | 96.00 | 115.20 | 134.41 |
GR                               Speed
```



#### Il rover

![](./imgs/rover.png)

**RPi**: Cuore del progetto, gestisce il web-server e l'integrazione con i sensori e l'elettronica, oltre alla logica di gioco.

[**Web**](https://ers-eco-race-simulator.github.io/Docs/#/web/web?id=web): Il Web inteso come reti di dispositivi ci permette di creare interfacce moderne e affidabili. Utilizziamo il Web per creare una pagina di controllo dove visualizzare le informazione fornite dal rover e tramite il quale comandarlo. Abbiamo lavorato con tecnologie web comuni come html, css, ecmascript e ci siamo avvicinati al back-end con Python, principalmente con il framework [Flask](https://www.palletsprojects.com/p/flask/).

**Arduino**: Arduino ci piace in quanto progetto open source, per la sua semplicità e per le opportunità che offre a "non-elettrotecnici" di approcciare l'elettronica. Utilizziamo Arduino per controllare:

+ Servo, per lo sterzo posteriore
+ LN298, per controllare il motore della trazione anteriore

Abbiamo inoltre dovuto sviluppare un [minimale protocollo](https://ers-eco-race-simulator.github.io/Docs/#/arduino/py2arduino) per la comunicazione asincrona tra RPi e Arduino.

**Sensori**: Diversi sensori sono indispensabili per il corretto funzionamento di ogni robot:

+ **Action camera**: per la visualizzazione in tempo reale del tracciato del rover.

+ [**Lidar**](https://ers-eco-race-simulator.github.io/Docs/#/lidar/lidar): è uno strumento di rilevamento che misura la distanza da un bersaglio tramite la riflessione di un raggio laser. Essendo applicato a una torretta rotante, permette di mappare uno spazio di alcuni metri intorno al rover.

  Abbiamo utilizzato il Lidar per creare un modulo di [object avoidance](https://ers-eco-race-simulator.github.io/Docs/#/lidar/objectdetection), in modo da poter preservare la salute del nostro rover.

+ [**mpu6050**](https://ers-eco-race-simulator.github.io/Docs/#/gyro): conoscere le posizione del rover nello spazio e nel tempo è essenziale. A tale riguardo abbiamo usato il classico accelerometro e giroscopio mpu6050.



#### Il futuro di ERS

Abbiamo grandi sogni per il nostro progetto:

+ Corse multiplayer
+ Piattaforma on-line per la gestione in tempo reale delle classifiche
+ Integrazione con le API di OSM per la creazione dinamica dei tracciati
+ Milioni di persone che si specializzano nella guida ecologica!



Per ulteriori informazione sugli sviluppi in tempo reale del progetto ERS, visitate la nostra [Documentazione](https://ers-eco-race-simulator.github.io/Docs/#/tech):

+ Docs: https://ers-eco-race-simulator.github.io/Docs/#/tech
+ GitHub: https://github.com/ERS-Eco-Race-Simulator





























