1.  Green/Yellow/Red su health statusi klastera u Elastic Search-u. Green znači da su svi shardovi alocirani čvorovima i sustav radi potpuno ispravno. Yellow znači da neke replike nisu dostupne, ali sustav i dalje radi, uz rizik gubitka podataka. Red znači da jedan ili više primarnih shardova nedostaje.

2.  2.1. Da ga možemo razlomiti na tokene i raditi full text pretragu
    2.2. Za sortiranje, agregiranje i točno pretraživanje po naslovu
    2.3. Jer se koriste samo za usporedbu/filtiranje/agregacija, a ne za full-text pretragu, pa ne trebamo razlomljivati na tokene.
    2.4. Zato što opis sadrži dulji tekst i može se pretraživati po riječima.

3.  3.1. Asciifolding zamijenjuje dijakritičke znakove (ć -> c).
    3.2. \_score pokazuje relevantnost rezultata. U ovom slučaju 'roman' se pojavljuje jednom u svakom opisu i scores su vrlo slični.

4.  4.1. "na", "drini", "cuprija"
    4.2. lowercase pretvara sve znakove u lowercase, asciifolding zamnjenjuje dijakritičke znakove
    4.3. Analyzer dijeli text na riječi/tokene, i pomoću toga možemo raditi stvari poput lowercase pretvorbe i asciifoldinga za bolju pretragu i tako pronaći riječi koje nisu identične search term-u.

5.  Elastic Search, za razliku od SQL upita, koristi invertirani indeks i puno brže pronalazi tražene riječi jer ne mora skenirati sve. ES može raditi i stemming, asciifolding, itd., što omogućuje puno bolju pretragu koja pronalazi korijene riječi bez obzira na kapitalizaciju i dijakritičke znakove. Također koristi i \_score, pomoću čega prvo vraća najrelevantnije rezultate. ES je dizajniran za distribuiranu arhitekturu te se lakše skalira.
