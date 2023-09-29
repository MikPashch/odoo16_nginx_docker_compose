# Odoo16 with Nginx and AWS RDS Integration

This repository provides instructions for deploying Odoo16 with Nginx as a web server within Docker Compose.

If you encounter any issues when connecting Odoo to an external database using Docker Compose, this guide is here to assist you.

This setup is specifically designed for seamless integration with external databases, including AWS RDS, to enhance your database management capabilities.


## Prerequisites

Before you begin, make sure you have the following prerequisites installed on your Linux machine:

1. Docker: You can install Docker using the following commands:

    ```shell
    sudo apt update
    sudo apt install docker-compose
    ```

2. Verify Docker Compose installation:

    ```shell
    docker-compose --version
    ```

## Getting Started

Follow these steps to set up and launch Odoo16 with Nginx using Docker Compose:

1. Create a directory for your Odoo project:

    ```shell
    mkdir odoo
    cd odoo
    ```

2. Create a Docker Compose file:

    ```shell
    nano docker-compose.yml
    ```

3. Copy and paste the contents from the provided `docker-compose.yml` file into this new file.

4. In the `docker-compose.yml` file, don't forget to change the database connection details to match your external database (e.g., AWS RDS). Modify the following environment variables:

   - `DB_PORT_5432_TCP_ADDR=your_db_endpoint`
   - `DB_ENV_POSTGRES_PASSWORD=your_password`

5. Save and exit the text editor.

6. In the `app` folder, create a file called `nginx.conf` and populate it with the configuration information you need for Nginx. You can use the `nginx.conf` file provided in this repository as a reference.

7. Launch the Odoo16 and Nginx containers with Docker Compose:

    ```shell
    sudo docker-compose up -d
    ```

8. To view the running containers, use the following command:

    ```shell
    sudo docker container ls -a
    ```

## Additional Configuration

You may need to customize the configuration files and environment variables further to suit your specific requirements. Be sure to consult the Odoo and Nginx documentation for detailed configuration options.


## Acknowledgments

- [Odoo](https://www.odoo.com/)
- [Nginx](https://www.nginx.com/)
- [Docker](https://www.docker.com/)

Feel free to contribute to this repository or report issues if you encounter any problems during the setup process.
