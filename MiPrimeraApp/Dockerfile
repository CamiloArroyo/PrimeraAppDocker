FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR webPrueba

EXPOSE 80
EXPOSE 5024

#COPY PROJECT FILES
COPY ./*.csproj ./

RUN dotnet restore

#COPY EVERYHING ELSE
COPY . . 
RUN dotnet publish -c Realese -o out


#BUILD IMAGES 
FROM mcr.microsoft.com/dotnet/sdk:8.0 
WORKDIR webPrueba
COPY --from=build /webPrueba/out .
ENTRYPOINT ["dotnet","MiPrimeraApp.dll"]