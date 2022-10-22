# Docker image for the build environment
FROM mcr.microsoft.com/dotnet/core/sdk:2.2.207 AS base

# Docker image for the runtime environment
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2.8

WORKDIR /app
    
# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore
    
# Copy everything else and build
COPY . .
RUN dotnet publish -c Release -o out
    



# This command starts up the app
ENTRYPOINT ["dotnet", "Conduit.dll"]
