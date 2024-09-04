Sure! Below is the updated `README.md` file for your project named `DevOps_AspNetCore_Sample`, with the .NET Core version set to 8. The text has been made more human-readable and friendly.

# DevOps ASP.NET Core Sample Project

Welcome to the **DevOps ASP.NET Core Sample Project**! This project serves as a demonstration of how to create a web application using ASP.NET Core 8. In this README, you'll find instructions on how to set up the project, run it locally, and publish it on both Windows and Linux.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Running the Application](#running-the-application)
  - [Changing the Port](#changing-the-port)
- [Publishing the Application](#publishing-the-application)
  - [Publishing on Windows](#publishing-on-windows)
  - [Publishing on Linux](#publishing-on-linux)
- [Running as a Service (Optional)](#running-as-a-service-optional)
- [License](#license)

## Prerequisites

Before you dive in, make sure you have the following installed on your machine:

- [.NET SDK 8.0](https://dotnet.microsoft.com/download) (the latest version)
- A code editor of your choice (e.g., [Visual Studio](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/))


## Getting Started

1. **Clone the Repository**: Start by cloning the project repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/DevOps_AspNetCore_Sample.git
   cd DevOps_AspNetCore_Sample
   ```

2. **Restore Dependencies**: Next, restore the project dependencies:

   ```bash
   dotnet restore
   ```

## Running the Application

To run the application locally, simply use the following command:

```bash
dotnet run
```

Once the application starts, you can access it at `http://localhost:5000` or `https://localhost:5001` by default.

### Changing the Port

If you want to run the application on a different port, you can specify the `--urls` option when starting it. For example, to run the application on port 8080, use:

```bash
dotnet run --urls "http://localhost:8080"
```

Alternatively, you can set the port in the `launchSettings.json` file located in the `Properties` folder of your project. Look for the `applicationUrl` property and modify it like this:

```json
"profiles": {
  "IIS Express": {
    "commandName": "IISExpress",
    "launchBrowser": true,
    "environmentVariables": {
      "ASPNETCORE_ENVIRONMENT": "Development"
    },
    "applicationUrl": "http://localhost:5000;http://localhost:8080"
  },
  "DevOps_AspNetCore_Sample": {
    "commandName": "Project",
    "launchBrowser": true,
    "environmentVariables": {
      "ASPNETCORE_ENVIRONMENT": "Development"
    },
    "applicationUrl": "http://localhost:5000;http://localhost:8080"
  }
}
```

## Publishing the Application

### Publishing on Windows

1. **Open Command Prompt or PowerShell**: Start by opening a command prompt or PowerShell window.
2. **Navigate to the Project Directory**: Change to the directory where your project is located.
3. **Publish the Application**: Use the following command to publish the application:

   ```bash
   dotnet publish -c Release -o ./publish
   ```

   This command will create a published version of your application in the `./publish` directory.

4. **Navigate to the Publish Directory**:

   ```bash
   cd publish
   ```

5. **Run the Application**:

   ```bash
   dotnet DevOps_AspNetCore_Sample.dll
   ```

### Publishing on Linux

1. **Open a Terminal**: Launch a terminal window.
2. **Navigate to the Project Directory**: Change to the directory where your project is located.
3. **Publish the Application**: Use the following command to publish the application:

   ```bash
   dotnet publish -c Release -o ./publish
   ```

   This will create a published version of your application in the `./publish` directory.

4. **Navigate to the Publish Directory**:

   ```bash
   cd publish
   ```

5. **Run the Application**:

   ```bash
   dotnet DevOps_AspNetCore_Sample.dll
   ```

## Running as a Service (Optional)

If you're using Linux, you can run the application as a service using `systemd`. Create a service file (e.g., `devops_aspnetcore_sample.service`) in `/etc/systemd/system/`:

```ini
[Unit]
Description=DevOps ASP.NET Core Sample Application

[Service]
WorkingDirectory=/path/to/your/publish
ExecStart=/usr/bin/dotnet /path/to/your/publish/DevOps_AspNetCore_Sample.dll
Restart=always
RestartSec=10
SyslogIdentifier=devops_aspnetcore_sample
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production

[Install]
WantedBy=multi-user.target
```

After creating the service file, run the following commands to start and enable the service:

```bash
sudo systemctl start devops_aspnetcore_sample.service
sudo systemctl enable devops_aspnetcore_sample.service
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### Key Changes Made:
- Updated the project name to `DevOps_AspNetCore_Sample`.
- Changed the .NET version to 8.0.
- Made the text more conversational and user-friendly.

Feel free to modify any sections further to better fit your project or add any additional information you think is necessary! If you have any further questions or need assistance, let me know!
