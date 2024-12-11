# README

Tutorial: Create a web API with ASP.NET Core in VSCode

### Prerequisites

- Visual Studio Code
- C# for Visual Studio Code (latest version)
- .NET 8.0 SDK

### Create a web project

- Open the integrated terminal.
- Change directories (cd) to the folder that will contain the project folder.
- Run the following commands

```bash
  dotnet new webapi --use-controllers -o TodoApi
  cd TodoApi
  dotnet add package Microsoft.EntityFrameworkCore.InMemory
  code -r ../TodoApi
```

### Test the project

- Trust the HTTPS development certificate by running the following command:

```bash
  dotnet dev-certs https --trust
```

- Select Yes if you agree to trust the development certificate.
- Run the following command to start the app on the https profile:

```bash
  dotnet run --launch-profile https
```

The output shows messages similar to the following, indicating that the app is running and awaiting requests:

```bash
  ...
  info: Microsoft.Hosting.Lifetime[14]
        Now listening on: https://localhost:{port}
  ...
```

- Ctrl+click the HTTPS URL in the output to test the web app in a browser.
- The default browser is launched to https://localhost:<port>/swagger/index.html, where <port> is the randomly chosen port number displayed in the output. There's no endpoint at https://localhost:<port>, so the browser returns HTTP 404 Not Found. Append /swagger to the URL, https://localhost:<port>/swagger.

### Scaffold a controller

- Control-click the TodoAPI project and select Open in Terminal. The terminal opens at the TodoAPI project folder. Run the following commands:

```bash
  dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
  dotnet add package Microsoft.EntityFrameworkCore.Design
  dotnet add package Microsoft.EntityFrameworkCore.SqlServer
  dotnet add package Microsoft.EntityFrameworkCore.Tools
  dotnet tool uninstall -g dotnet-aspnet-codegenerator
  dotnet tool install -g dotnet-aspnet-codegenerator
  dotnet tool update -g dotnet-aspnet-codegenerator
```
