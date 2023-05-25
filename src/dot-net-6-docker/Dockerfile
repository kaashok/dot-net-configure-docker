FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 2527

ENV ASPNETCORE_URLS=http://+:2527

# Creates a non-root user with an explicit UID and adds permission to access the /app folder
# For more info, please refer to https://aka.ms/vscode-docker-dotnet-configure-containers
RUN adduser -u 5678 --disabled-password --gecos "" appuser && chown -R appuser /app
USER appuser

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["src/dot-net-6-docker/dot-net-6-docker.csproj", "src/dot-net-6-docker/"]
RUN dotnet restore "src/dot-net-6-docker/dot-net-6-docker.csproj"
COPY . .
WORKDIR "/src/src/dot-net-6-docker"
RUN dotnet build "dot-net-6-docker.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "dot-net-6-docker.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "dot-net-6-docker.dll"]
