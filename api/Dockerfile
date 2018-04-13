# Build Stage
FROM microsoft/aspnetcore-build:2.0.0 AS build-env
WORKDIR /api
COPY . .
RUN dotnet restore -s http://192.168.33.10:8081/nexus/service/local/nuget/nuget-local/
RUN dotnet publish -o /publish
# Runtime Image Stage
FROM microsoft/aspnetcore:2.0.0
WORKDIR /publish
COPY --from=build-env /publish .
ENTRYPOINT [ "dotnet", "api.dll"]