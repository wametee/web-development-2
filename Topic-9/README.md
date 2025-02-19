# PHP and MySQL Database Programming

## Overview

PHP is a popular server-side scripting language that is widely used for web development. Combined with MySQL, a powerful relational database management system, PHP allows developers to create dynamic and data-driven web applications. This guide covers the basics of PHP and MySQL database programming, including handling HTTP requests (`POST` and `GET`), establishing database connections, executing queries, and fetching results.

## Handling HTTP Requests

### GET and POST Methods

PHP provides two superglobal arrays, `$_GET` and `$_POST`, to collect data sent via HTTP GET and POST methods, respectively.

- **GET Method**: Data is sent as URL parameters and is visible in the URL. Suitable for data that is not sensitive.
- **POST Method**: Data is sent in the body of the HTTP request and is not visible in the URL. Suitable for sensitive data.

### Example

```php
// Handling GET request
if (isset($_GET['name'])) {
    $name = $_GET['name'];
    echo "Hello, " . htmlspecialchars($name) . "!";
}

// Handling POST request
if ($_SERVER['REQUEST_METHOD'] == 'POST' && isset($_POST['name'])) {
    $name = $_POST['name'];
    echo "Hello, " . htmlspecialchars($name) . "!";
}
```

## Establishing a Database Connection

To interact with a MySQL database, you need to establish a connection using PHP's `mysqli` or `PDO` extensions. In this example, we will use `mysqli`.

### Example

```php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "database_name";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
```

## Executing Queries

Once connected to the database, you can execute SQL queries using the `mysqli_query` function for `SELECT`, `INSERT`, `UPDATE`, and `DELETE` operations.

### Example

#### SELECT Query

```php
$sql = "SELECT id, firstname, lastname FROM MyGuests";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Output data of each row
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["firstname"]. " " . $row["lastname"]. "<br>";
    }
} else {
    echo "0 results";
}
```

#### INSERT Query

```php
$sql = "INSERT INTO MyGuests (firstname, lastname, email)
VALUES ('John', 'Doe', 'john@example.com')";

if ($conn->query($sql) === TRUE) {
    echo "New record created successfully";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
```

## Fetching Results

To fetch results from a `SELECT` query, you can use methods like `fetch_assoc`, `fetch_array`, `fetch_row`, or `fetch_object`.

### Example

```php
$sql = "SELECT id, firstname, lastname FROM MyGuests";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Fetch associative array
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["firstname"]. " " . $row["lastname"]. "<br>";
    }
} else {
    echo "0 results";
}
```

## Closing the Database Connection

Always close the database connection after completing your operations to free up resources.

### Example

```php
$conn->close();
```

## Conclusion

PHP and MySQL together provide a powerful combination for developing dynamic and interactive web applications. Understanding how to handle HTTP requests, establish database connections, execute queries, and fetch results is essential for any web developer working with these technologies.
