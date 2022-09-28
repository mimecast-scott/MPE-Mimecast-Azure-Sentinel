# Mimecast Azure Sentinel Integration
`DISCLAIMER: This is an unofficial Dockerized version of the integration bundle on the Mimecast website`


In order to simplify the requirements to collect Mimecast logs and share with Azure Sentinel, I have created a docker container. This Dockerfile for this covers the steps in the [Mimecast KB here](https://community.mimecast.com/s/article/Azure-Sentinel) up to the section of `Configuring the Azure Sentinel Workspace`

Give it a go

`docker run -p 5000:5000 -it smck83/mimecast-sentinel`

Then access http://localhost:5000 or http://<ip-address>:5000

