FROM mcr.microsoft.com/dotnet/core/sdk:2.1 as build

RUN apt-get update; apt-get install git

RUN git clone https://github.com/pvdbleek/ASPNETCoreDockerMicroservices.git

RUN mv /ASPNETCoreDockerMicroservices/Services/Jobs.Api/jobs.api.csproj /ASPNETCoreDockerMicroservices/Services/Jobs.Api/Jobs.Api.csproj; \
    mv /ASPNETCoreDockerMicroservices/Services/Applicants.Api/applicants.api.csproj /ASPNETCoreDockerMicroservices/Services/Applicants.Api/Applicants.Api.csproj

WORKDIR /ASPNETCoreDockerMicroservices/Services/Applicants.Api/

RUN dotnet restore; dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/core/aspnet:2.1 AS final

WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "Applicants.Api.dll"]
