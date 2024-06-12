<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Creating REST APIs with C#</title>
  <style>
    body {
      font-family: sans-serif;
      margin: 20px;
    }
    h1, h2, h3 {
      margin: 10px 0;
    }
    code {
      background-color: #f0f0f0;
      padding: 5px;
      width: 100%;
    }
  </style>
</head>
<body>
  <h1>Creating REST APIs with C#</h1>
  <p>REST APIs (Representational State Transfer APIs) are a popular way to build web services that allow communication between applications. This guide provides a basic introduction to creating REST APIs using C#.</p>

  <h2>Prerequisites</h2>
  <ul>
    <li>Basic understanding of C# programming</li>
    <li>A code editor (e.g., Visual Studio Code, Visual Studio)</li>
    <li>A .NET framework or .NET Core installation</li>
  </ul>

  <h2>Setting Up the Project</h2>
  <p>You can create a REST API using ASP.NET Web API, a popular framework for building web services in C#.</p>
  <ol>
    <li>Open your code editor and create a new project.</li>
    <li>Select the "ASP.NET Web Application" project template.</li>
    <li>Choose the "Web API" project type.</li>
    <li>Give your project a name and click "Create".</li>
  </ol>

  <h2>Creating a Model</h2>
  <p>A model represents the data your API will handle. It defines the structure of your data objects.</p>
  <p>For example, if your API manages a list of products, you could create a `Product` model class with properties like `Id`, `Name`, `Price`, etc.</p>
  <code class="csharp">
  public class Product<br/>
  {<br/>
      public int Id { get; set; }<br/>
      public string Name { get; set; }<br/>
      public decimal Price { get; set; }<br/>
  }
  </code>

  <h2>Creating a Controller</h2>
  <p>Controllers handle incoming requests to the API and define the logic for processing them.</p>
  <p>You can create methods within the controller class to handle different HTTP verbs (GET, POST, PUT, DELETE) for specific API endpoints.</p>
  <code class="csharp">
  public class ProductsController : ApiController<br/>
  {
      private List<Product> products = new List<Product>()<br/>
      {<br/>
          new Product { Id = 1, Name = "Product 1", Price = 10.00m },<br/>
          new Product { Id = 2, Name = "Product 2", Price = 20.00m }<br/>
      };<br/>

      // GET: api/Products<br/>
      public IEnumerable<Product> GetProducts()<br/>
      {<br/>
          return products;<br/>
      }<br/>

      // GET: api/Products/5<br/>
      public Product GetProduct(int id)<br/>
      {<br/>
          var product = products.FirstOrDefault(p => p.Id == id);<br/>
          if (product == null)<br/>
          {<br/>
              return null;<br/>
          }<br/>
          return product;<br/>
      }<br/>
  }<br/>
  </code>
  <p>In this example, the `ProductsController` defines two methods:</p>
  <ul>
    <li>`GetProducts`: This method returns a list of all products using the `GET` verb on the `/api/Products` endpoint.</li>
    <li>`GetProduct`: This method takes an ID as input and returns a specific product using the `GET` verb on the `/api/Products/{id}` endpoint (where `{id}` is replaced with the actual ID).</li>
  </ul>

  <h2>Running the API</h2>
  <p>Once you've defined your models and controllers, you can run the application. Press F5 in your code editor to launch the development server.</p>
  <p>You can then access your API endpoints using tools like Postman or by directly making requests in your web browser (e.g., `http://localhost:5000/api/Products`).</p>
</body></html>
