# Creating REST APIs with C#
  REST APIs (Representational State Transfer APIs) are a popular way to build web services that allow communication between applications. This guide provides a basic introduction to creating REST APIs using C#.

### Prerequisites
  
    Basic understanding of C# programming
    A code editor (e.g., Visual Studio Code, Visual Studio)
    A .NET framework or .NET Core installation
  

### Setting Up the Project
  You can create a REST API using ASP.NET Web API, a popular framework for building web services in C#.
  
    Open your code editor and create a new project.
    Select the "ASP.NET Web Application" project template.
    Choose the "Web API" project type.
    Give your project a name and click "Create".
  

 ### Creating a Model
  A model represents the data your API will handle. It defines the structure of your data objects.
  For example, if your API manages a list of products, you could create a `Product` model class with properties like `Id`, `Name`, `Price`, etc.
    
    public class Product
    {
      public int Id { get; set; }
      public string Name { get; set; }
      public decimal Price { get; set; }
    }


 ### Creating a Controller
  Controllers handle incoming requests to the API and define the logic for processing them.
  You can create methods within the controller class to handle different HTTP verbs (GET, POST, PUT, DELETE) for specific API endpoints. 
  
    public class ProductsController : ApiController
    {
      private List<Product> products = new List<Product>()
      {
          new Product { Id = 1, Name = "Product 1", Price = 10.00m },
          new Product { Id = 2, Name = "Product 2", Price = 20.00m }
      };

      // GET: api/Products
      public IEnumerable<Product> GetProducts()
      {
          return products;
      }

      // GET: api/Products/5
      public Product GetProduct(int id)
      {
          var product = products.FirstOrDefault(p => p.Id == id);
          if (product == null)
          {
              return null;
          }
          return product;
      }
  }

  In this example, the `ProductsController` defines two methods:
  
  `GetProducts`: This method returns a list of all products using the `GET` verb on the `/api/Products` endpoint.
  
  
  `GetProduct`: This method takes an ID as input and returns a specific product using the `GET` verb on the `/api/Products/{id}` endpoint (where `{id}` is replaced with the actual ID).

 ### Running the API
  Once you've defined your models and controllers, you can run the application. Press F5 in your code editor to launch the development server.
  You can then access your API endpoints using tools like Postman or by directly making requests in your web browser (e.g., `http://localhost:5000/api/Products`).
