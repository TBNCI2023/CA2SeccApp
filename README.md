Branch master

# Instructions

The setup instructions for a MySQL and phpMyAdmin environment utilizing Docker containers are provided in this *README.md*. You can find instructions on how set up a Docker network, conducting a MySQL Docker image with a given passport and a name, and running a phpMyAdmin Docker image while mapping a port to the container's port 80 on the previously established network.

## Docker version
Docker version *17.09* and later.

## Check if Docker is installed
By running the command:
```sh
docker --version
```
> If installed go to [^1].

> If not installed go to [^4].


## Create a **Docker Network**

1. Run the following command:

```sh
docker network create **[your_network_name]**
```
Replace *"your_network_name"* with the name you decide for you network. It will allow containers to connect.


2. Run the `MySQL Docker image` using the command:

```sh
docker run --name datab --network **[your_network_name]** -e MYSQL_ROOT_PASSWORD=my-sec-password -d mysql:latest
```

This will run the latest version of MySQL and name the container "datab". It will also connect the container to the network you just created and set the root password to "my-sec-password".

3. Run the `phpMyAdmin Docker image` using the command:

```sh
docker run --name phpmyadmin --network **[your_network_name]** -p **[your_port_choice]**:80 -d phpmyadmin/phpmyadmin
```

This will run the latest version of phpMyAdmin and name the container *"phpmyadmin"*. It helps to connect the container to the network created and map a port to port 80 of the container. Replace *"your_port_choice"* and *"your_network_name"*.


## If Docker is not Installed
Follow the next steps if docker need to be installed in your local machine.

4. How to Install Docker
Go to the Docker website: https://www.docker.com/products/docker-desktop
Click on the "Download" button and select your operating system (Windows or Mac).
Follow the installation instructions for your operating system.
Once Docker is installed, open a terminal window (Windows) or a terminal application (Mac).
Run the command "docker --version" to make sure Docker is installed and working properly.
