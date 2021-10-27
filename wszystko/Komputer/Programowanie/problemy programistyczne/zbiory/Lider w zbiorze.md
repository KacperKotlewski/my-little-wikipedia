# Znajdowanie lidera w zbiorze
---
W zadanaich tego typu chodzi o to by znaleść **liczbe** (lub element) w zbiorze o długości **n**, która się powtarza więcej razy niż połowa z n, czyli występuje więcej niż **n//2** razy, jeżeli nie spełnia warunku występywania więcej razy niż połowa długości listy to lider nie istnieje.

``ilość_wystąpień_liczby > n//2``,
gdzie `>` oznacza `większe od`, a `//` oznacza `dzielenie bez reszty` czyli do liczby całkowitej

można to rozwiązać na 3 (mi znane) sposoby:
- [[#metoda 1]]  licznika **O(n^2)**
- [[#metoda 2]] słownika liczników	**O(n^2)**
- [[#metoda 3]] parowanie i wyznaczanie lidera **O(n)**


---

## metoda 1 
### licznika
 | 
--|--
klasa algorytmu | #algorytm_wyszukiwania, #algorytm_brute_force, #algorytm_zachłanny
struktura danych | lista/tablica
najgorsza możliwa złożoność czasowa | O(n^2)
najlepsza możliwa złożoność czasowa | O(n)
uśrediona złożoność czasowa | O(n^2)
najgorsza możliwa złożoność przestrzenna | O(n)


```
lista <- zawieralistę danych do sprawdzenia przez algorytm
n <- rozmiar listy
połowa_listy <- n podzielone bez reszty przez 2 (int)

lider_metoda_1:

	dla i od 0 do n wykonuj:
		aktualny_kandydat_na_lidera <- lista[i]
		licznik <- 0
		
		dla j od i do n wykonuj:
			jeżeli aktualny_kandydat_na_lidera jest równy lista[j] wykonaj:
				licznik <- licznik + 1
				
		jeżeli licznik jest większy od  wykonaj:
			zwróć jako wynik aktualny_kandydat_na_lidera
			
	zwróć błąd lub wartość pustą jak None czy Null
```
implementacja:
- [[Lider w zbiorze - python#metoda 1|python]]

---

## metoda 2 
### słownika liczników

 | 
--|--
klasa algorytmu | #algorytm_wyszukiwania, #algorytm_brute_force
struktura danych | lista/tablica
najgorsza możliwa złożoność czasowa | O(n^2)
najlepsza możliwa złożoność czasowa | O(n)
uśrediona złożoność czasowa | O(n^2)
najgorsza możliwa złożoność przestrzenna | O(n^2)


```py
def lider_metoda_2(lista):
	n=len(lista)
	slownik_licznikow= dict()
	
	for elem in lista:

		if elem in slownik_licznikow.keys():
			slownik_licznikow[elem]+=1

			if slownik_licznikow[elem] > n//2:
				return elem

		else:
			count_of_nums[elem] = 1

	return None
```
implementacja:
- [[Lider w zbiorze - python#metoda 2|python]]

---

## metoda 3
### parowanie i wyznaczanie lidera

 | 
--|--
klasa algorytmu | #algorytm_wyszukiwania, #algorytm_zachłanny
struktura danych | lista/tablica
najgorsza możliwa złożoność czasowa | O(2n)
najlepsza możliwa złożoność czasowa | O(n)
uśrediona złożoność czasowa | O(n)
najgorsza możliwa złożoność przestrzenna | O(n)


```py
def lider_metoda_1(lista):
	n = len(lista)
	aktualny_kandydat_na_lidera = lista[0]
	do_pary = 1

	for i in range(1, n):
		if do_pary > 0:
		
			if aktualny_kandydat_na_lidera == lista[i]:
				do_pary += 1
			else:
				do_pary -= 1
				
		else:
			do_pary += 1
			aktualny_kandydat_na_lidera = lista[i]
			
	if do_pary == 0:
		return 0
		
		
	else:
		licznik = 0
		lider = aktualny_kandydat_na_lidera
		
		for elem in lista:
			if elem == lider:
				licznik += 1
				
		if licznik > n//2:
			return lider
			
			
	return None

```
implementacja:
- [[Lider w zbiorze - python#metoda 3|python]]


---
