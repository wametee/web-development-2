# Server Side Scripting

## Introduction to Active Server Pages (ASP)
Active Server Pages (ASP) is a server-side scripting technology developed by Microsoft. It allows developers to create dynamic and interactive web pages by embedding scripts within HTML. These scripts are processed on the server, and the resulting HTML is sent to the client's browser. This approach enables web applications to interact with databases, handle user input, and generate customized content dynamically.

## ASP Introduction
ASP scripts are typically written in VBScript or JavaScript and execute on the server. The primary purpose of ASP is to generate dynamic content that responds to user actions and inputs. When a browser requests an ASP file, the server processes the embedded scripts and returns the generated HTML to the client.

### Key Features of ASP:
- **Server-side execution**: Scripts are executed on the server, which means the client only receives the final HTML.
- **Language support**: Supports multiple scripting languages, including VBScript, JavaScript, and PerlScript.
- **Database interaction**: Easily integrates with databases using ADO (ActiveX Data Objects) to retrieve and manipulate data.
- **State management**: Supports session and application state management to maintain data across multiple requests.

## Types of ASP

### ASP.NET
ASP.NET is an advanced web application framework developed by Microsoft. It allows developers to build dynamic web applications using a wide range of programming languages, including C# and VB.NET. ASP.NET provides a robust and scalable platform for building enterprise-level web applications with features like:

- **Web Forms**: A component-based programming model for building rich web applications.
- **MVC (Model-View-Controller)**: A pattern for building scalable and maintainable web applications.
- **Web API**: Framework for building HTTP services that can be consumed by various clients.
- **Razor Pages**: Simplified page-based programming model for building web UI.

### Classic ASP
Classic ASP, also known as ASP 3.0, is the original version of ASP. It uses VBScript as its primary scripting language and is primarily used for simple web applications. Classic ASP has been largely replaced by ASP.NET but is still used in some legacy systems. Key features of Classic ASP include:

- **Simplicity**: Easy to learn and use for small-scale web applications.
- **Interoperability**: Can work with various databases and COM components.
- **Compatibility**: Supported by all versions of IIS (Internet Information Services).

### Scripts
ASP scripts can be written in various scripting languages, including VBScript, JavaScript, and PerlScript. These scripts are embedded within HTML and processed on the server before being sent to the client's browser. Examples of common tasks performed by ASP scripts include:

- **Form handling**: Processing user input from web forms.
- **Database queries**: Retrieving and displaying data from a database.
- **Session management**: Tracking user sessions and maintaining state.

## Razor
Razor is a markup syntax used in ASP.NET to create dynamic web pages. It allows developers to write server-side code using C# or VB.NET within HTML. Razor provides a clean and concise way to create web pages with dynamic content. Key features of Razor include:

- **Simplicity**: Combines HTML markup with server-side code in a straightforward manner.
- **IntelliSense**: Supports code completion and syntax highlighting in Visual Studio.
- **Flexibility**: Can be used in both ASP.NET MVC and Razor Pages.

### Example of Razor Syntax

```html
@{
    var message = "Hello, world!";
}
<!DOCTYPE html>
<html>
<head>
    <title>Razor Example</title>
</head>
<body>
    <h1>@message</h1>
</body>
</html>

```
## Layout
In ASP.NET, layouts are used to define the common structure of web pages. A layout typically includes a header, footer, and navigation bar, which are shared across multiple pages. Using layouts helps maintain a consistent look and feel throughout the web application.

## Example of a Layout in ASP.NET MVC

```

<!DOCTYPE html>
<html>
<head>
    <title>@ViewBag.Title - My ASP.NET Application</title>
    <link rel="stylesheet" type="text/css" href="~/Content/Site.css" />
</head>
<body>
    <header>
        <h1>My ASP.NET Application</h1>
    </header>
    <nav>
        <ul>
            <li>@Html.ActionLink("Home", "Index", "Home")</li>
            <li>@Html.ActionLink("About", "About", "Home")</li>
            <li>@Html.ActionLink("Contact", "Contact", "Home")</li>
        </ul>
    </nav>
    <section>
        @RenderBody()
    </section>
    <footer>
        <p>&copy; 2025 - My ASP.NET Application</p>
    </footer>
</body>
</html>

```

In this example, the layout defines a common structure for the web application, including a header, navigation bar, and footer. The @RenderBody() method is used to insert the content of the specific view being rendered.


## Forms
Forms are an essential part of web applications, allowing users to submit data to the server. In ASP.NET, forms are created using HTML and enhanced with server-side code to handle user input and perform actions such as data validation and database operations.

## Example of a Simple ASP.NET Form

```

<!DOCTYPE html>
<html>
<head>
    <title>Simple ASP.NET Form</title>
</head>
<body>
    <form method="post" action="process.aspx">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" />
        <br />
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" />
        <br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>

```

## Example of Processing the Form Data in ASP.NET (process.aspx)

```C#
<%@ Page Language="C#" %>
<%@ Import Namespace="System" %>

<!DOCTYPE html>
<html>
<head>
    <title>Form Processing</title>
</head>
<body>
    <h1>Form Data</h1>
    <p>Name: <% Response.Write(Request.Form["name"]); %></p>
    <p>Email: <% Response.Write(Request.Form["email"]); %></p>
</body>
</html>

```

In this example, the form data is submitted to the process.aspx page, where it is processed using C# code. The Request.Form collection is used to retrieve the form data and display it on the page.

## Conclusion
Server-side scripting with ASP provides a powerful way to create dynamic and interactive web applications. By using ASP.NET, developers can build robust and scalable web applications with a wide range of features and capabilities. Understanding the basics of ASP, Razor, layouts, and forms is essential for any web developer working with Microsoft technologies.
