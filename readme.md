## //***************** NOP Commerce Installation guide in linux ******************//
<br>
<br>


![Docker](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker.jpg)

<br>

### nopCommerce is the best open-source e-commerce shopping cart. nopCommerce is available for free. Today it's the best and most popular ASP.NET ecommerce software. It has been downloaded more than 1.8 million times!
### nopCommerce is a fully customizable shopping cart. It's stable and highly usable. nopCommerce is an open source ecommerce solution that is ASP.NET Core based with a MS SQL 2008 (or higher) backend database. Our easy-to-use shopping cart solution is uniquely suited for merchants that have outgrown existing systems, and may be hosted with your current web host or our hosting partners. It has everything you need to get started in selling physical and digital goods over the internet.

<br>

## **Docker**
 ***

### Docker is a lightweight, open, and secure platform. It is a way to simplify the process of building, shipping, and running applications in a different environment. Docker bundles up all the dependencies of an application and runs it in a container. In a simple word, on the off chance that you need to use MSSQL, you do not need to download, install, and manage a bunch of packages, simply run the container with Docker and use it — as simple as that.
<br>

## **Image**
 ***

### An image is used to build a container, it has necessary files to run something on an operating system, like Windows or Ubuntu, and then it has your application framework along with database files that support that. So, if you’re using ASP.NET, NodeJS, or Python, Images have that typical code.
<br>

## **Container**
 ***

### Images are just the definitions which cannot be run directly. To run the images, we need containers. Containers are the instances that help to run images with a different configuration like port, IP Address, etc.
<br>

## **Docker Compose**
 ***

### Docker Compose is used to run multiple containers under a single instance. It creates a network with different containers, through the network containers can communicate with each other. So, if the application has a dependency on other containers, Docker Compose is the right fit.
 
### As we tend to run a nopCommerce app with an MS SQL server, we'll use Docker Compose.
 
<br>

## **Assumptions**
 ***

### All commands in this post assume that -
    You are running a Linux machine.
    Docker is installed on your system.

<br>

## **Configuration**
 ***

    Open Source/nginx.conf and replace domain name with your domain name and change your host ip.

<br>

## **Grant permission**
 ***


    sudo chmod +x install.sh


<br>

## **Execution**
 ***

    sudo ./install.sh
<br>

## **Check Running Containers**
 ***

### It will list down all the running containers. You should see that both the containers - nopCommerce and SQL Server are running now. 
![docker-ps](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker06.png)

<br>

## **Run nopCommerce store on a browser**
 ***

### Open a browser tab and hit your domain URL. It will open the nopCommerce installation page.
![Browser](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker07.png) 

<br>

## **Pass the DB connection**
 ***

### Pass the database container name and password that has been defined in the yml file.

![db](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker08.png)

<br>

## **Check the container status**
 ***

### Once the installation is done, you should see the connection reset page because our application container has stopped running.

![container](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker09.png)

### Execute the ***docker ps*** command again to see the running containers. You should see only one container of MSSQL is running.

![container-down](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker10.png)

### To get a list of all the containers, execute the command ***docker ps -a***

![start](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker11.png)

<br>

## **Up the web container again**
 ***

### To run the web container again, run the command ***docker container start <container-id>***. You can simply give the first three characters of the container Id.

![up](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker12.png)

### Follow with the command to list the running containers. You should see both the containers are running now.

![running](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker13.png)

<br>

## **Go to the browser window and check the nopCommerce store**
 ***

### Go to your domain and hit Refresh. You'll land up to the nopCommerce Homepage.
![final](https://csharpcorner.azureedge.net/article/how-to-run-nopcommerce-on-linux-using-docker/Images/How%20to%20run%20nopCommerce%20on%20Linux%20using%20Docker14.png)

### Congratulations! 🎉 You’re running your nopCommerce first store on a Linux machine!!

<br>

## **nopCommerce resources:**
 ***


   nopCommerce official site: https://www.nopcommerce.com

   nopCommerce demo store: https://www.nopCommerce.com/demo.aspx

   Feature list: https://www.nopcommerce.com/featurelist.aspx

   Technology & system Requirements: http://docs.nopcommerce.com/pages/viewpage.action?pageId=10256757

   Documentation: http://docs.nopcommerce.com/

   Forums: https://www.nopcommerce.com/boards/Gitter.im 

   chat room: https://gitter.im/nopCommerce-official/Lobby
