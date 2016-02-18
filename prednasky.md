# Prednáška 01 (18.2.2016)

Webstránka predmetu: http://ics.upjs.sk/~rkb/?cmd=asu1

## Algoritmus

Moznosti zápisov algoritmov

* Programovacím jazykom
* Psudokód
* Slovný zápis
* Obrázkový zápis

### Example

	/**
     * Sedliacke násobenie
     * 
     * @param x nezáporné čísla  
     * @param y všetky prirodzené (dokonca ľub reálne číslo by algoritmus zvládol)
     * @return výsledok po násobení x a y
     */
    public static int run(int x, int y) {
        int vysledok = 0;
        while (x > 0) {
            if (x % 2 == 1) {
                vysledok += y;
            }
            x = (int) Math.ceil(x / 2);
            y *= 2;
        }
        return vysledok;
    }

## Analýza algoritmov

* Korektnosť, správnosť
* Výpočtová zložitosť - čas výpočtu
* Pamäťová zložitosť - veľkosť potrebnej pamäte

### Ohranicenia vypočtovej zložitosti

* **O** - horné ohraničenie - O(n) podmnozina O(n^2)
* **omega** - dolné ohraničenie - omega(n^2) podmnozina omega(n)
* **theta** - testné ohraničenie - theta(n) prienik theta(n^2) = prázdna mnozina

#### Zoradenie podla asymptotickej zlozitosti:

* ln (ln (n))
* ln (n), log (n), log200 (n)
* log^k (n)
* sqrt(n)
* 2^(ln(n)) = n^(1/log2(e))
* n, ln(2^n) = n*ln(2)
* n*log(n)
* n^2
* n^5
* 2^n

Pozn: ln(n) log(n) log200(n) - to vsetko je v rovnakej theta triede!

Pozn2: ln (2^n) = n.ln(2) = theta(n)

Naucit sa L'Hopitala https://en.wikipedia.org/wiki/L%27H%C3%B4pital%27s_rule

### Example

O(n^2):

	Prvy(pole[1..n])
	for i ← 1 to n-2
	  for j ← i to i+2
	    vysl ← vysl+pole[j] 

O(n^2):

	Druhy(pole[1..n])
	for i ← 1 to n
	  for j ← i to n-i
	    vysl ← vysl+pole[j] 

theta(log(n)):

	Treti(pole[1..n])
	i ← 1
	while i ≤ n
	  i ← 2*i
	  vysl ← vysl+pole[j] 

O(n):

	Rek_fcia(n)
	if i = 1
	  return 1
	else
	  return n*Rek_fcia(n-1) 



	Rek_fcia2(n)
	if i = 1
	  return 1
	else
	  return 2*Rek_fcia2(n-1)



	Rek_fcia3(n)
	if i = 1
	  return 1
	else
	  return n*Rek_fcia3(n/2)