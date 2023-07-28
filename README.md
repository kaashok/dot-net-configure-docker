# NET 6 Web API on Docker

# Steps:
- Install Docker extension in VS Code
- Press Ctrl+Shift+P to open the Command Palette and search for Docker: Add Docker Files to Workspace
  ![image](https://github.com/kaashok/dot-net-configure-docker/assets/22614984/61692c70-18d3-4ef6-9ca5-b301171af15d)
 - You will be prompted with different options, including:
    - Select Application Platform - choose .NET: ASP.NET Core
    - Select Operating System - choose Linux (this is the operating system of the container, not your machine, so definitely choose Linux)
    - Port - type in which container port your application will use (I prefer 5000)
    - Include optional Docker Compose files - choose Yes
- The extension will create a couple of files and configurations:
    - Dockerfile
    - .dockerignore, which contains files and directories patterns to be excluded from the context
    - docker-compose.yml - a YAML file that defines the services and, with a single command, can spin everything up or tear it all down
    - docker-compose.debug.yml - same as docker-compose.yml, but with debugging configuration
 -  In the Command Palette (Ctrl+Shift+P). Pick which docker-compose file you want to run.
    ![image](https://github.com/kaashok/dot-net-configure-docker/assets/22614984/ac7e8c81-ed57-42ca-9af6-361d6441630f)
- Another way is to right-click on docker-compose.yml or docker-compose.debug.yml and select Compose Up to reproduce the same behavior as the command-line execution.
  ![image](https://github.com/kaashok/dot-net-configure-docker/assets/22614984/4634bc39-2db8-4e14-a23e-f76662ceb2f6)
    
#Reference: https://amelspahic.com/net-6-on-docker-with-debugging

