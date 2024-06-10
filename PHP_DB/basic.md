
### Použití databáze v PHP

#### 1. Připojení k databázi

- **PDO (PHP Data Objects)**: Univerzální rozhraní pro práci s databázemi.

##### Připojení pomocí PDO

```php
<?php
$host = '127.0.0.1';
$db = 'nazev_databaze';
$user = 'uzivatel';
$pass = 'heslo';
$charset = 'utf8mb4';

$dsn = "mysql:host=$host;dbname=$db;charset=$charset";
$options = [
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES   => false,
];

try {
    $pdo = new PDO($dsn, $user, $pass, $options);
} catch (\PDOException $e) {
    throw new \PDOException($e->getMessage(), (int)$e->getCode());
}
?>
```

#### 2. Výběr dat z databáze

- **SELECT**: Použití dotazu pro výběr dat.

##### Příklad SELECT dotazu

```php
<?php
$sql = "SELECT * FROM tabulka WHERE sloupec = :hodnota";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota' => $nejakaHodnota]);
$results = $stmt->fetchAll();

foreach ($results as $row) {
    echo $row['sloupec'];
}
?>
```

#### 3. Vkládání dat do databáze

- **INSERT**: Použití dotazu pro vložení dat.

##### Příklad INSERT dotazu

```php
<?php
$sql = "INSERT INTO tabulka (sloupec1, sloupec2) VALUES (:hodnota1, :hodnota2)";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota1' => $hodnota1, 'hodnota2' => $hodnota2]);
?>
```

#### 4. Aktualizace dat v databázi

- **UPDATE**: Použití dotazu pro aktualizaci dat.

##### Příklad UPDATE dotazu

```php
<?php
$sql = "UPDATE tabulka SET sloupec1 = :hodnota1 WHERE sloupec2 = :hodnota2";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota1' => $hodnota1, 'hodnota2' => $hodnota2]);
?>
```

#### 5. Odstraňování dat z databáze

- **DELETE**: Použití dotazu pro odstranění dat.

##### Příklad DELETE dotazu

```php
<?php
$sql = "DELETE FROM tabulka WHERE sloupec = :hodnota";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota' => $hodnota]);
?>
```

#### 6. Bezpečnost

- **Připravené dotazy**: Pomocí `prepare` a `execute` zabráníte SQL injekcím.
- **Výjimky**: Ošetřujte chyby pomocí výjimek (`try-catch` bloky).

##### Příklad zabezpečení

```php
<?php
try {
    $pdo->beginTransaction();
    $sql = "INSERT INTO tabulka (sloupec1, sloupec2) VALUES (:hodnota1, :hodnota2)";
    $stmt = $pdo->prepare($sql);
    $stmt->execute(['hodnota1' => $hodnota1, 'hodnota2' => $hodnota2]);
    $pdo->commit();
} catch (\Exception $e) {
    $pdo->rollBack();
    echo "Failed: " . $e->getMessage();
}
?>
```

Tento zápis ti poskytne základní přehled, jak pracovat s databází v PHP pomocí PDO. Hodně štěstí při práci s databázemi!
