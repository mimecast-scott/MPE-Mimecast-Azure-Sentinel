# Mimecast Azure Sentinel Integration
`DISCLAIMER: This is an unofficial Dockerized version of the integration bundle on the Mimecast website`


In order to simplify the requirements to collect Mimecast logs and share with Azure Sentinel, I have created a docker container. This Dockerfile covers the steps in the [Mimecast KB here](https://community.mimecast.com/s/article/Azure-Sentinel) up to the section of `Configuring the Azure Sentinel Workspace`

# Give it a go using Ubuntu 18.04 
NOTE: This OS is end of standard 5 year maintenance windows on  31st May 2023

`docker run -p 5000:5000 -v /my/local/path:/opt/mimecast smck83/mimecast-sentinel:18.04`

Or run detached
`docker run -d -p 5000:5000 -v /my/local/path:/opt/mimecast --restart=always smck83/mimecast-sentinel:18.04`

# Give it a go using Ubuntu 20.04:
NOTE: Using `PPA deadsnakes` to install Python 3.7 which is a dependency of the Mimecast script created for Microsoft Sentinel:

`docker run -p 5000:5000 -v /my/local/path:/opt/mimecast smck83/mimecast-sentinel:20.04`

Or run detached
`docker run -d -p 5000:5000 -v /my/local/path:/opt/mimecast --restart=always smck83/mimecast-sentinel:20.04`

Then access http://localhost:5000 or http://\<ip-address\>:5000

