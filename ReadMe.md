Black-Jack Human Code

(Supponiamo ci sia un tavolo da n giocatori)
(Con sum(x) si intende la somma delle carte in possesso di x)

- Ogni giocatore esegue le sue puntate
- Il banco distribuisce una carta ciascuno, la carta del banco resta coperta
   
- Per i <= n: 
   - Finché sum(player_i) < 21:
     - il banco chiede al giocatore se vuole che venga pescata una carta:
         se si:
          - il banco pesca una carta dal mazzo
          - la dà a player_i
         se no:
          - si passa a player_(i+1)
   
   - Passa a player-(i+1)

- Il banco scopre la sua carta
- Finché sum(banco) <= 17: 
   - il banco pesca una carta
- Il banco si ferma. 

Se sum(banco) > 21:
   - per i <= n:
     se sum(player_i) <= 21:
        - player_i guadagna il doppio della sua puntata

Se sum(banco) <= 21:
   - per i <= n:

     se sum(player_i) <= 21 e sum(player_i) > sum(banco):
        - player_i guadagna il doppio della sua puntata
    




       
   