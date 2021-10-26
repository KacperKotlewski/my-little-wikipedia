# Połączenia w bazach danych SQL (join)
---

połączenia relacji w bazach danych możemy tworzyć przy użyciu [[Kwerendy sql|kwerendy]] **join** w różnych konfiguracjach, poniżej znajdziesz przykłady

---
## spis treści:
- [[#natural join]]

---
## natural join
>kiedy mamy 2 relacje w których mamy takie same nazwy atrybutów to zostaną one ze sobą skojarzone i połączone przy takich samych wartościach, wypisane będą tylko te które mają wartości skojarzone


przykład:
relacja: **foods**:

ITEM_ID | ITEM_NAME | ITEM_UNIT | COMPANY_ID 
-|-|-:|-:
 1 		 | Chex Mix     | Pcs       | 16
 6       | Cheez-It     | Pcs       | 15
 2       | BN Biscuit   | Pcs       | 15
 3       | Mighty Munch | Pcs       | 17
 4       | Pot Rice     | Pcs       | 15
 5       | Jaffa Cakes  | Pcs       | 18
 7       | Salt n Shake | Pcs       | Null   
 
relacja: **company**:        
 
 COMPANY_ID | COMPANY_NAME | FIRMA_MIASTO
-|:-:|-:  
18         | Order All     | Boston 
15         | Jack Hill Ltd | London 
16         | Akas Foods    | Delhi 
17         | Foodies.      | London  
19         | sip-n-Bite.   | New York  

w tym wypatku natural join będzie parował po **COMPANY_ID** gdyż w obu relacjach mamy taki atrybut o tej nazwie
```sql
SELECT * FROM foods NATURAL JOIN company;
```

COMPANY_ID|ITEM_ID|ITEM_NAME| ITEM_UNIT|COMPANY_NAME|COMPANY_CITY
-|-|-|-|-|-
16 | 1 | Chex Mix 		| Pcs | Akas Foods 		| Delhi
15 | 6 | Cheez-It 		| Pcs | Jack Hill Ltd 	| London
15 | 2 | BN Biscuit 	| Pcs | Jack Hill Ltd 	| London
17 | 3 | Mighty Munch 	| Pcs | Foodies. 		| London
15 | 4 | Pot Rice 		| Pcs | Jack Hill Ltd 	| London
18 | 5 | Jaffa Cakes 	| Pcs | Order All 		| Boston

___