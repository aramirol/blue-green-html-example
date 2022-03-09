# blue-green-html-example

![Docker Pulls](https://img.shields.io/docker/pulls/aramirol/blue-green-deployment?logo=docker&logoColor=white)
![Docker Image Size (latest semver)](https://img.shields.io/docker/image-size/aramirol/blue-green-deployment?logo=docker&logoColor=white)

Simple container with CentOS 7 and Apache server installed. You must pull the image from [blue-green-deployment](https://hub.docker.com/r/aramirol/blue-green-deployment) in Docker Hub. Basically, I have two images with two versions of the same code that change background colour.

## How to

To use this images just create two differents deployments that link with the two differents images.

<img src="https://aramirol.github.io/custom-resources/images/blue.png" width="30%" /> <img src="https://aramirol.github.io/custom-resources/images/green.png" width="30%" />

For example, to deploy the first blue image you can use:

![Blue Deployment](https://img.shields.io/badge/v0.0.1-Blue%20Deployment-blue)
```yml
    spec:
      containers:
      - name: app
        image: aramirol/blue-green-deployment:0.0.1
        ports:
        - containerPort: 80
```

To deploy the second green image you can use:

![Green Deployment](https://img.shields.io/badge/v0.0.2-Green%20Deployment-green)
```
    spec:
      containers:
      - name: app
        image: aramirol/blue-green-deployment:0.0.2
        ports:
        - containerPort: 80
```
