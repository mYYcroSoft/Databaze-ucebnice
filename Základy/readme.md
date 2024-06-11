### 1. Základní terminologie
- **Systém řízení báze dat**: Data jsou řízena balíkem programů (SŘDB)
- **Databázoví systém**: Tvoří databáze a systém řízení báze
- **Databáze**: Organizovaná kolekce dat, obvykle uložená a přístupná elektronicky.
- **DBMS (Database Management System)**: Software pro správu a manipulaci s databázemi.
- **Tabulka**: Základní struktura v databázi, skládající se z řádků a sloupců.
- **Záznam**: Jednotlivý řádek v tabulce.
- **Pole**: Jednotlivý sloupec v tabulce.

### 2. Konceptuální modelování

- **ER diagram (Entity-Relationship diagram)**: Grafické znázornění entit a jejich vztahů v databázi.
- **Entita**: Objekt nebo věc, která existuje a je rozpoznatelná, například osoba nebo produkt.
- **Atribut**: Vlastnost nebo charakteristika entity, například jméno nebo cena.
- **Vztah**: Asociace mezi dvěma nebo více entitami, například zákazník kupuje produkt.
- **Kardinálnost**: Určuje počet vztahů mezi entitami, například jeden-na-jeden, jeden-na-mnoho, mnoho-na-mnoho.

### 3. Relační model dat

- **Relační model**: Datový model založený na tabulkách, kde data jsou organizována do relačních tabulek.
- **Primární klíč**: Unikátní identifikátor záznamu v tabulce.
- **Cizí klíč**: Pole v jedné tabulce, které odkazuje na primární klíč v jiné tabulce, což vytváří vztah mezi těmito tabulkami.
- **Normalizace**: Proces organizace dat do tabulek tak, aby se minimalizovala redundance a zlepšila integrita dat.

### 4. DML (Data Manipulation Language)

#### a. SELECT, selekce a projekce, aliasy

- **SELECT**: Používá se pro dotazování dat z databáze.
  - Příklad: `SELECT * FROM Tabulka;`
- **Selekce**: Výběr řádků na základě určitých podmínek.
  - Příklad: `SELECT * FROM Tabulka WHERE podmínka;`
- **Projekce**: Výběr specifických sloupců.
  - Příklad: `SELECT sloupec1, sloupec2 FROM Tabulka;`
- **Alias**: Dočasné přejmenování tabulky nebo sloupce.
  - Příklad: `SELECT sloupec1 AS alias1 FROM Tabulka;`

#### b. INSERT, UPDATE, DELETE

- **INSERT**: Vkládání nových dat do tabulky.
  - Příklad: `INSERT INTO Tabulka (sloupec1, sloupec2) VALUES (hodnota1, hodnota2);`
- **UPDATE**: Aktualizace existujících dat v tabulce.
  - Příklad: `UPDATE Tabulka SET sloupec1 = hodnota1 WHERE podmínka;`
- **DELETE**: Odstranění dat z tabulky.
  - Příklad: `DELETE FROM Tabulka WHERE podmínka;`
