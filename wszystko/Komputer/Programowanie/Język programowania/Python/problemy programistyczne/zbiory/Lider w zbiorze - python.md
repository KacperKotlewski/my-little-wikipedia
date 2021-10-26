O zagadnieniu przeczytasz [[Lider w zbiorze|tutaj]]
---
___
## spis treści
Rozwiązania:
- [[#metoda 1]]  licznika **O(n^2)**
- [[#metoda 2]] słownika liczników	**O(n^2)**
- [[#metoda 3]] skanowania od prawej **O(n)**

[[#przykład implementacji]]

---
## metoda 1 
### (licznika)
[[Lider w zbiorze#metoda 1|czytaj o rozwiązaniu]]

```py
def lider_metoda_1(lista):
	n = len(lista)

	for i in range(n):
		aktualny_kandydat_na_lidera = lista[i]
		licznik = 0
		
		for j in range(i, n):
			if aktualny_kandydat_na_lidera == lista[j]:
				licznik += 1
				
		if licznik > n//2:
			return aktualny_kandydat_na_lidera
			
	return None
```

---

## metoda 2 
### (słownika liczników)
[[Lider w zbiorze#metoda 2|czytaj o rozwiązaniu]]

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

---

## metoda 3
### (skanowania od lewej)
[[Lider w zbiorze#metoda 3|czytaj o rozwiązaniu]]

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


---

## przykład wywołania
```py
lista_z_liderem = [3,6,3,8,3,8,3,2,3,7,3]

print(lider_metoda_1(lista_z_liderem))
print(lider_metoda_2(lista_z_liderem))
print(lider_metoda_3(lista_z_liderem))
```
