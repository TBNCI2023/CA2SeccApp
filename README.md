Branch master

![dockerLogo](https://user-images.githubusercontent.com/45858960/227732847-a6d9bdce-3e8c-4e14-bef6-fe3d714787b0.png)
---

# Instructions

The setup instructions for a MySQL and phpMyAdmin environment utilizing Docker containers are provided in this *README.md*. You can find instructions on how set up a Docker network, conducting a MySQL Docker image with a given passport and a name, and running a phpMyAdmin Docker image while mapping a port to the container's port 80 on the previously established network.

## Docker version
Docker version *17.09* and later.

## Check if Docker is installed
By running the command:
```sh
docker --version
```
> If installed go to point 1.

> If not installed go to point 4.



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

---

## If Docker is not Installed

4. How to Install Docker
- Go to the [Docker website](https://www.docker.com/products/docker-desktop)
- Click "Download" button and select the correct operating system.
- Follow the installation instructions.
- Once Docker is installed, open a terminal window and run the following command to check if Docker has been installed successfully.
```sh
docker --version
```


For more information on how to install Docker click [HERE](https://docs.docker.com/get-docker/)
