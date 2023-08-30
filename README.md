# Mixpanel Proxy for AWS ECS

This NGINX configuration is based off the [original Mixpanel proxy](https://github.com/mixpanel/tracking-proxy) example, with an additional health check route. This is important when you need to deploy this with a Load Balancer on AWS for a more robust, fault-tolerant and production-ready proxy.

## Installation

You may refer to this [article that I've written here](https://medium.com/p/611649d80453) on Medium. It walks you through the entire infrastructure setup on AWS to get it up and running. However, you first need to build, tag & push this Docker image to your ECR.

### Building Your Docker Image

Assuming you have Docker installed on your system, you can do the following:

1.  Clone the repo
2.  Build the Docker image: `docker build -t mixpanel-proxy:latest .`
3.  Tag the image: `docker tag mixpanel-proxy:latest <aws_account_id.dkr.ecr.region.amazonaws.com>/<ECR_NAME>`
4.  Push it to your ECR: `docker push <aws_account_id.dkr.ecr.region.amazonaws.com>/<ECR_NAME>:latest`

Feel free to deploy it based on your own infrastructure requirements or [refer to this guide](https://medium.com/p/611649d80453).
