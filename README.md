# Wordpress in Docker with Remote Containers and Visual Studio
This repo is a starting point to develop wordpress themes and or plugins.

## Prerequisites
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [VS Code](https://code.visualstudio.com/)
- [Remote - Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers))

## Setup
- Create an `.env` file in the `.devcontainer` folder with the following keys and replace all values.
```
PROJECT_NAME=<Project name>
MARIADB_VER=<MariaDB Version>
MARIADB_ROOT_PASS=<MariaDB Root Password>
DB_NAME=<Database Name>
MARIADB_USER=<MariaDB Username>
MARIADB_PASS=<MariaDB Password>
WORDPRESS_TAG=<Wordpress Tag>
```

- If desired, update the theme folder name.
    - Make sure to update the following settings to match:
        - `launch.json`
        - `docker-compose.yml`

## Running the project
- Open the command pallet by pressing: `ctrl` + `shift` + `P`
- Select `Remote-Containers: Reopen in container...`

## Debugging
- Select the `Run and Debug` tab on the left menu or press `ctrl` + `shift` + `D`
- Press the play icon for `Listen for Xdebug`
- Place breakpoints in either the `.wordpress` folder or your `theme` folder.
- Navigate to your site in any browser.

## References
- https://github.com/microsoft/vscode-dev-containers/tree/v0.140.1/containers/php
- https://code.visualstudio.com/remote/advancedcontainers/overview