# Web Development 2: Server-Side Scripting

## Introduction
Server-side scripting is a crucial aspect of web development, allowing developers to process requests, manage databases, and dynamically generate content before it is sent to the client. This document covers the fundamentals of server-side scripting using PHP, including syntax, variables, control structures, and PHP basics.

---

## Table of Contents
1. [Syntax](#syntax)
2. [Variables](#variables)
3. [Control Structures](#control-structures)
4. [PHP Basics](#php-basics)

---

## 1. Syntax
PHP scripts are written within `<?php ... ?>` tags and executed on the server before the output is sent to the client.

Example of a basic PHP script:
```php
<?php
  echo "Hello, World!";
?>
```
### Comments in PHP
- **Single-line comments**: `// This is a comment`
- **Multi-line comments**:
  ```php
  /*
   This is a multi-line comment
  */
  ```

PHP code can be embedded within HTML using PHP tags:
```html
<!DOCTYPE html>
<html>
<head>
    <title>PHP in HTML</title>
</head>
<body>
    <h1><?php echo "Welcome to Server-Side Scripting!"; ?></h1>
</body>
</html>
```

---

## 2. Variables
Variables in PHP start with a `$` sign and do not require explicit data types.

Example:
```php
<?php
  $name = "John Doe";
  $age = 30;
  echo "Name: $name, Age: $age";
?>
```
### Variable Scope
- **Local Variables**: Declared inside a function and accessible only within that function.
- **Global Variables**: Declared outside any function and accessible within functions using `global` keyword.
- **Static Variables**: Retain their value across function calls.
  ```php
  function countVisits() {
      static $count = 0;
      $count++;
      echo "Visit Count: $count";
  }
  ```
- **Superglobals**: Predefined variables like `$_GET`, `$_POST`, `$_SESSION`, etc.

### Data Types
PHP supports multiple data types:
- **String**: `$text = "Hello, PHP!";`
- **Integer**: `$num = 42;`
- **Float**: `$pi = 3.14;`
- **Boolean**: `$status = true;`
- **Array**: `$colors = ["Red", "Blue", "Green"];`
- **Object**: Instances of user-defined classes.

---

## 3. Control Structures
Control structures are used to handle decision-making and loops.

### Conditional Statements
```php
<?php
  $num = 10;
  if ($num > 0) {
    echo "Positive Number";
  } elseif ($num < 0) {
    echo "Negative Number";
  } else {
    echo "Zero";
  }
?>
```

### Looping Structures
- **For Loop**:
  ```php
  for ($i = 0; $i < 5; $i++) {
    echo "Iteration $i <br>";
  }
  ```
- **While Loop**:
  ```php
  $count = 0;
  while ($count < 5) {
    echo "Count: $count <br>";
    $count++;
  }
  ```
- **Foreach Loop** (for arrays):
  ```php
  $colors = ["Red", "Blue", "Green"];
  foreach ($colors as $color) {
    echo "Color: $color <br>";
  }
  ```
- **Do-While Loop**:
  ```php
  $i = 1;
  do {
    echo "Number: $i <br>";
    $i++;
  } while ($i <= 5);
  ```

---

## 4. PHP Basics
### Forms Handling
```php
<?php
  if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
    echo "Hello, $name!";
  }
?>
<form method="POST">
  Name: <input type="text" name="name">
  <button type="submit">Submit</button>
</form>
```

### Connecting to MySQL Database
```php
<?php
  $conn = new mysqli("localhost", "root", "", "test_db");
  if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
  }
  echo "Connected successfully";
?>
```

### Functions in PHP
```php
<?php
  function greet($name) {
    return "Hello, " . $name . "!";
  }
  echo greet("Alice");
?>
```

### Include and Require
To modularize code, PHP provides:
- `include "file.php";` (includes a file and continues execution even if the file is missing)
- `require "file.php";` (includes a file but throws an error if the file is missing)

Example:
```php
<?php
  include "header.php";
  echo "Welcome to the main page.";
?>
```

---

## Conclusion
This document has covered the fundamental aspects of server-side scripting using PHP, including syntax, variables, control structures, and form handling.

---

## References
- [PHP Official Documentation](https://www.php.net/manual/en/)
- [MySQL Documentation](https://dev.mysql.com/doc/)