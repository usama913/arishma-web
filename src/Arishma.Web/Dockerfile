FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY src/Arishma.Web/Arishma.Web.csproj src/Arishma.Web/
RUN dotnet restore src/Arishma.Web/Arishma.Web.csproj
COPY . .
RUN dotnet publish src/Arishma.Web/Arishma.Web.csproj -c Release -o /app/wwwroot --no-restore
FROM nginx:alpine
COPY --from=build /app/wwwroot/wwwroot /usr/share/nginx/html
