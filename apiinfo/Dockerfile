FROM microsoft/dotnet:2.2-sdk

COPY . /app

# Set the working directory as "app" directory
WORKDIR /app

# Run the following commands in Linux Terminal to restore .NET Core packages
RUN ["dotnet", "restore"]

# Build the application
RUN ["dotnet", "build"]

# Expose a port number from the container to outside world
EXPOSE 5000
EXPOSE 5001

# Determine an entry point of the application.
ENTRYPOINT ["dotnet", "run", "--server.urls", "http://0.0.0.0:5001"]




