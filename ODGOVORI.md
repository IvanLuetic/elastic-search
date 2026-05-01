1.  Green/Yellow/Red su health statusi klastera u Elastic Search-u. Green znači da su svi shardovi alocirani čvorovima i sustav radi potpuno ispravno. Yellow znači da neke replike nisu dostupne, ali sustav i dalje radi, uz rizik gubitka podataka. Red znači da jedan ili više primarnih shardova nedostaje.

2.  2.1. Da ga možemo razlomiti na tokene i raditi full text pretragu
    2.2. Za sortiranje, agregiranje i točno pretraživanje po naslovu
    2.3. Jer se koriste samo za usporedbu/filtiranje/agregacija, a ne za full-text pretragu, pa ne trebamo razlomljivati na tokene.
    2.4. Zato što opis sadrži dulji tekst i može se pretraživati po riječima.
