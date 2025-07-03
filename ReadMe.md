Mano di Black-Jack Human Code

(Supponiamo ci sia un tavolo da n giocatori (player_1,..,player_n); un mazzo di 52 carte; inoltre supponiamo che si possa solo puntare su se stessi)
(Con sum(x) si intende la somma dei valori delle carte in possesso di x)
(Con $-$(player_i) si intende il denaro posseduto dal player_i)
(Con Puntata(player_i) si intende la puntata fatta nella mano dal player_i)


Per ogni giocatore, sum(giocatore) = 0; 

- Ogni giocatore esegue le sue puntate:
    per i <= n: 
        - player_i punta x soldi:
            - aggiungere x a Puntata(player_i)
            - togliere x da $-$(player_i)
    
- Il banco distribuisce una carta ciascuno, la carta del banco resta coperta:
     per i <= n:
        - rimuovere una carta dal mazzo
        - dare quella carta a player_i
        - aggiungere il valore della carta a sum(player_i)

      - banco rimuove una carta dal mazzo
      - la tiene coperta 
   
- Per i <= n: 
   - Finché sum(player_i) < 21:
     - il banco chiede al giocatore se vuole che venga pescata una carta:

         se si:
           - il banco pesca una carta dal mazzo
           - la dà a player_i
           se la carta è un asso: 
              - player_i sceglie se la carta ha valore 1 o 11;
              - aggiungere il valore scelto della carta a sum(player_i)
           altrimenti:
              - aggiungere il valore della carta a sum(player_i)

   - Passa a player_(i+1)


- Il banco scopre la sua carta
- aggiungere valore carta a sum(banco)

- Finché sum(banco) < 17: 
   - il banco pesca una carta
      se la carta è un asso: 
            - banco sceglie se la carta ha valore 1 o 11;
            - aggiungere il valore scelto della carta a sum(banco)
      altrimenti:
            - aggiungere il valore della carta a sum(banco)

  

- Il banco si ferma e la mano finisce. 

Se sum(banco) > 21:
   - per i <= n:
     se sum(player_i) <= 21:
        - player_i guadagna il doppio della sua puntata:
            - aggiungere 2*Puntata(player_i) a $-$(player_i);
            - settare Puntata(player_i) a 0;

Se sum(banco) <= 21:
   - per i <= n:

     se sum(player_i) <= 21 e sum(player_i) > sum(banco):
        - player_i guadagna il doppio della sua puntata:
            - aggiungere 2*Puntata(player_i) a $-$(player_i);
            - settare Puntata(player_i) a 0;

     altrimenti: 
        - il banco guadagna la puntata del player_i:
            - aggiungere Puntata(player_i) a $-$(banco);
            - settare Puntata(player_i) a 0;
    




       
   