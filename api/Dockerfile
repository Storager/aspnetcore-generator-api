FROM microsoft/aspnetcore:2.0.0

WORKDIR /app

COPY bin/Debug/netcoreapp2.0/publish .

ENTRYPOINT ["dotnet", "/app/api.dll"]