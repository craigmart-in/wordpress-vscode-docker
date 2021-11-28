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
        - `devcontainer.json`

## Running the project
- Open the command pallet by pressing: `ctrl` + `shift` + `P`
- Select `Remote-Containers: Reopen in container...`

## Importing existing Wordpress site
- Perform the setup steps
- Download wp-content from existing Wordpress site
- Copy wp-content to ./.data/wp-content/
- If theme under development is in the wp-content folder then move that folder to the src folder
    - This will be symlinked to wp-content/themes in the `devcontainer.json`
- Update `launch.json` and `devcontainer.json` to match new theme folder name
- Create sql backup of existing wordpress site
- Update URLs to match docker
- Copy sql file to ./.data/initdb.d
- Uncomment the mount line in `docker-compose.yml` in the MariaDB section
- Run the project as described in the previous section.

## Debugging
- Select the `Run and Debug` tab on the left menu or press `ctrl` + `shift` + `D`
- Press the play icon for `Listen for Xdebug`
- Place breakpoints in either the `.wordpress` folder or your `theme` folder.
- Navigate to your site in any browser.

## Tips
- If running on windows, this performs faster when all of the files are in WSL2.

## References
- https://github.com/microsoft/vscode-dev-containers/tree/v0.140.1/containers/php
- https://code.visualstudio.com/remote/advancedcontainers/overview