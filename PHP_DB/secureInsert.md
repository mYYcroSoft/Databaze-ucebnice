
### Zabezpečení SQL INSERT a UPDATE v PHP

#### Bezpečný INSERT pomocí připravených dotazů

```php
<?php
$sql = "INSERT INTO tabulka (sloupec1, sloupec2) VALUES (:hodnota1, :hodnota2)";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota1' => $hodnota1, 'hodnota2' => $hodnota2]);
?>
```

#### Bezpečný UPDATE pomocí připravených dotazů

```php
<?php
$sql = "UPDATE tabulka SET sloupec1 = :hodnota1 WHERE sloupec2 = :hodnota2";
$stmt = $pdo->prepare($sql);
$stmt->execute(['hodnota1' => $hodnota1, 'hodnota2' => $hodnota2]);
?>
```

### Klíčové body zabezpečení:

- **Připravené dotazy**: Používejte `prepare` a `execute` metody PDO, které automaticky ošetřují vstupy proti SQL injekcím.
- **Vazby parametrů**: Místo přímého vkládání hodnot do SQL dotazu použijte pojmenované parametry (`:param`) a předávejte hodnoty přes pole asociativních klíčů.
