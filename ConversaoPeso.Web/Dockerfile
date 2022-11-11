FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-env
WORKDIR /App

COPY . ./

RUN dotnet restore

RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /App
COPY . .
ENTRYPOINT ["dotnet",  "ConversaoPeso.Web.csproj"]
EXPOSE 80