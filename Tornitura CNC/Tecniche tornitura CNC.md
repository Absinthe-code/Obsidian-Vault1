### Software

WinNC for Fanuc 30 giorni di prova

Sinutrain siemens 

# Terminologia

Tornio
- Pezzo in rotazione, lavorazione di asportazione di truciolo a pezzo in rotazione e ad utensile fermo
- Bidimensionale
- 2 Assi X e Z
- Torni moderni hanno la capacità di fresare
- Hanno un Autocentrante o Mandrino
- Una torretta calettata su un carro a croce che ne permette i movimenti
- Dalla Contropunta verso l'autocentrante, dal basso verso l'alto e viceversa
## Linguaggio ISO

### Funzioni preparatorie

Molti torni hanno bisogno di un carattere speciale seguito solitamente dal nome del programma
```c
% P001 //per torni vecchi o una parola tipo % Ingranaggio per nuovi 
//Meglio essere dettagliati nel nome del programma
//è buona norma mettere sempre la limitazione dei giri, Se lavori a velocità di taglio costante più ti avvicini al centro più la velocità tende a infinito quindi è bene mettere un massimo per non romprere qualcosa
G92 S2000 //G92 setta il numero massimo di giri, ripetibile nel mezzo del programma
//S2000 è 2000 giri al minuto
G53 X0 Z0 //Muove il carro alle sue origini 
T01 01 //il primo sta per il numero della posizione della torretta, il secondo è il correttore, ne parleremo poi
G94/G95 //Unità di misura dell'avanzamento, G94 è mm/min e G95 è mm/giro
M42 //gamma alta o bassa, è la marcia della macchina, 42 è alta e 41 è bassa, se non specificata userà l'ultima utilizzata
//41 da tutta la coppia possibile, fa le sgrossature, si usa a giri bassi
//42 da meno coppia ma gira più velocemente, tipo uso alluminio e plastica
M4 //Senso di rotazione orario guardando la torretta, guarda il mandrino e regola della mano destra, Antiorario M3
//---SUBITO DOPO NON SOTTO---
G96 S150 //VTcost, velocità di taglio costante a 150m/min
	//V_t = Diametro * pi * n.giri / 1000
	//n = 1000 * V_t / (Diametro * pi) 
G97 S150 //Giri fissi a 150 giri al minuto
//---FINE IMPOSTAZIONE MACCHINA---
	G92 //sposta origine
	G0 X0 Z0 //Movimento rapido ATTENTO PERCHé POTREBBE NON FARE UN MOVIMENTO RETTILINEO
		G0 Z0 //in due volte sarebbe meglio per la sicurezza e non collidere
		   X105
	G01 X Z F0.3 //Interpolazione lineare in movimento di lavoro, linee spezzate
```

1. Nome Programma
2. Limitazione
3. Fuori ingombro
4. Posizione torretta
5. Info avanzamento
6. Gamma
7. Rotazione autocentrante
8. 
