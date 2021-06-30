## Ireland Release Docker Compose Files
This branch contains the docker compose files that pull and run the `EdgeX Ireland` release images.

These compose files are auto generated from the multiple files contained in the `compose-builder` folder. See [README](https://github.com/edgexfoundry/edgex-compose/tree/ireland/compose-builder#readme) there for details.

### Compose Files

This folder contains the following compose files:

#### Generated Compose files

> **NOTES: **
>
> - *DO NOT EDIT the files directly for permanent changes. Make all permanent changes to the source compose files in the `compose-builder` folder and then regenerate these files*
> - Use `make build` from `Compose Builder` to regenerate all the following compose files.
> - See each description for the convenience `make` commands that are provided to work with each of these compose files.

- **docker-compose.yml**
    Contains all the services required to run in secure configuration. Includes the Device Virtual & Device REST device services.
    **Make Commands** 
    
     - Use `make run <service(s)>` and `make down` to start and stop the services using this compose file.
    
     - Use `make pull <service(s)>` to pull all or some images for the services in this compose file.
    
     - Use `make get-token` to generate a Kong access token for remote access of the services running from this compose file.
    
- **docker-compose-arm64.yml**
    Contains all the services required to run in secure configuration on `ARM64` system.  Includes the Device Virtual & Device REST device services.
    **Make Commands** 
    
     - Use `make run arm64` and `make down` to start and stop the services using this compose file.
     - Use `make pull arm64 <service(s)>` to pull all or some images for the services in this compose file.
     - Use `make get-token arm64` to generate a Kong access token for remote access of the services running from this compose file.
    
- **docker-compose-no-secty.yml**
    Contains just the services needed to run in non-secure configuration.  Includes the Device Virtual & Device REST device services.
    **Make Commands**

    - Use `make run no-secty` and `make down` to start and stop the services using this compose file.
    - Use `make pull no-secty <service(s)>` to pull all or some images for the services in this compose file.
    
- **docker-compose-no-secty-arm64.yml**
    Contains just the services needed to run in non-secure configuration on `ARM64` system.  Includes the Device Virtual & Device REST device services.

    **Make Commands**

    - Use `make run no-secty arm64` and `make down` to start and stop the services using this compose file.
    - Use `make pull no-secty arm64 <service(s)>` to pull all or some images for the services in this compose file.


- **docker-compose-no-secty-with-ui.yml**
  Contains just the services needed to run in non-secure configuration with the EdgeX UI.  Includes the Device Virtual & Device REST device services.
  **Make Commands**

  - Use `make run no-secty ui` and `make down` to start and stop the services using this compose file.
  - Use `make pull no-secty ui <service(s)>` to pull all or some images for the services in this compose file.

- **docker-compose-no-secty-with-ui-arm64.yml**
  Contains just the services needed to run in non-secure configuration with the EdgeX UI on `ARM64` system .  Includes the Device Virtual & Device REST device services.

  **Make Commands**

  - Use `make run no-secty ui arm64` and `make down` to start and stop the services using this compose file.
  - Use `make pull no-secty ui arm64 <service(s)>` to pull all or some images for the services in this compose file.

### TAF Compose files

The compose files under the `taf` subfolder are used for the automated TAF tests. These compose files are also generated from `Compose Builder` when the `make build` command is used.

### Additional make commands

- `make clean`

    Runs `down` commands, removes all stopped container and prunes all unused volumes and networks. Use this command when needing to do a fresh restart.
    
- `make get-token`
    For secure mode only. Runs commands via docker to generate a new API Gateway token.

- `make get-consul-acl-token`
  For secure mode only. Runs commands via docker to retrieve a Consul Access token.

### Additional compose files

- **docker-compose-portainer.yml**
    Stand-alone compose file for running Portainer which is a  Docker container management tool. Visit here https://www.portainer.io/ for more details on Portianer.
    Use `make portainer`and `make portainer-down` to start and stop Portainer.
