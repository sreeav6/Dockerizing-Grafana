# Dockerizing-Grafana

In this tutorial we will learn how to dockerize grafana. We will also explore how to access it.


Docker File Usage:
    We will use ubuntu latest as base image
    We use Arg inorder to avoid disruption during package installations 
    We will install required packages
    We will download and add Grafana GPG's key to ensure the downloaded packages are verified packages
    We will Adds Grafana's repository to the list of sources and installs Grafana.
    Copy the custom grafana configuration file (grafana.ini) from local into the container at specified path
    Expose port 3000 for the Grafana 
    Finally we will start the grafana server using the custom configuration file (grafana.ini)

Grafana.ini Usage
    http_port = 3000 sets the port on which port Grafana can be accessible.
    Grafana's admin username and password are specified under the security section.
    allow_sign_up = falsedisables the new users to sign up for accounts on their own, only the admin can create new user accounts.

Let Start Building the Docker image
    Make sure you run the docker command in the same directory where Dockerfile is present, else make sure you specify the path while building the image.

        sudo docker build -t grafana:1.0.0 .

Let's verify the iamge is build by below command

        sudo docker images [Here we will see the grafana image]

Let's Run and validate the image

        sudo docker run -p 3000:3000 grafana:1.0.0
        After running the above command we need to access the garfana dashboard.
        localhost:3000
        The username and password are admin which you have given in the grafana.ini file.


