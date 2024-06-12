# Creating REST APIs with C#
  REST APIs (Representational State Transfer APIs) are a popular way to build web services that allow communication between applications. This guide provides a basic introduction to creating REST APIs using C#.

### Prerequisites
```
  Basic understanding of C# programming
  
  A code editor (e.g., Visual Studio Code, Visual Studio)
  
  A .NET framework or .NET Core installation
```
### Setting Up the Project
  You can create a REST API using ASP.NET Web API, a popular framework for building web services in C#.
  ```
  Open your code editor and create a new project.
    
  Select the "ASP.NET Web Application" project template.
  
  Choose the "Web API" project type.
  
  Give your project a name and click "Create".
  ```


### Creating a Model

  A model represents the data your API will handle. It defines the structure of your data objects. For example, if your API manages a list of products, you could create a `Product` model class with properties like `Id`, `Name`, `Price`, etc.
  ```  
    public class Product
    {
      public int Id { get; set; }
      public string Name { get; set; }
      public decimal Price { get; set; }
    }
  ```
 
