# Dockerizing Grafana

In this tutorial, we will learn how to dockerize Grafana. We will also explore how to access it.

## Dockerfile Usage
We will use the following steps to create the Dockerfile:

1. Use `ubuntu:latest` as the base image.
2. Use `ARG` to avoid disruptions during package installations.
3. Install the required packages.
4. Download and add Grafana's GPG key to ensure the downloaded packages are verified.
5. Add Grafana's repository to the list of sources and install Grafana.
6. Copy the custom Grafana configuration file (`grafana.ini`) from the local system into the container at the specified path.
7. Expose port `3000` for Grafana.
8. Start the Grafana server using the custom configuration file (`grafana.ini`).

## Grafana.ini Usage

- `http_port = 3000`: Sets the port on which Grafana can be accessed.
- Grafana's admin username and password are specified under the security section.
- `allow_sign_up = false`: Disables new users from signing up for accounts on their own. Only the admin can create new user accounts.

## Building the Docker Image

Make sure you run the Docker command in the same directory where the Dockerfile is present. Otherwise, specify the path while building the image.

```bash
sudo docker build -t grafana:1.0.0 .
```


