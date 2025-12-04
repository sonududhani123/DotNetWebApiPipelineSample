
# .NET 8 Web API CI/CD Sample for Azure DevOps

This repository contains a minimal **ASP.NET Core Web API** with **xUnit tests** and an **Azure DevOps pipeline** (`azure-pipelines.yml`). Use it to practice building, testing, and deploying to Azure Web App.

## Structure
```
src/WebApiSample/            # ASP.NET Core Web API
tests/WebApiSample.Tests/    # xUnit tests
azure-pipelines.yml          # Azure DevOps pipeline
WebApiSample.sln             # Solution file
```

## Steps to Run in Azure DevOps
1. Create a new repo in Azure DevOps and upload this ZIP content.
2. Go to **Pipelines** → **New pipeline** → **Azure Repos Git** → select your repo.
3. Choose **Existing Azure Pipelines YAML file** → pick `azure-pipelines.yml`.
4. Run the pipeline. It will:
   - Restore & build the solution
   - Run unit tests
   - Deploy to Azure Web App (requires service connection and app name)

## Run Locally
```bash
dotnet restore WebApiSample.sln
dotnet build WebApiSample.sln -c Release
dotnet test WebApiSample.sln -c Release
dotnet run --project src/WebApiSample/WebApiSample.csproj
```
