# Private Docker Registry

A project to help you build a private docker-registry image.

* [http://blog.docker.io/2013/07/how-to-use-your-own-registry/](http://blog.docker.io/2013/07/how-to-use-your-own-registry/)
* [https://github.com/dotcloud/docker-registry/tree/0.5.9](https://github.com/dotcloud/docker-registry/tree/0.5.9)

#### Get the project

```
git clone https://github.com/hopsoft/private-docker-registry.git
cd private-docker-registry
```

#### Add your configuration

An example: https://github.com/dotcloud/docker-registry/blob/0.5.9/config_sample.yml

```
vim assets/config.yml
```

#### Build the image

```
vagrant up
vagrant ssh
sudo docker build -t USERNAME/docker-registry /path/to/private-docker-registry
```

#### Run the registry

```
sudo docker run -d -p 5000:5000 /opt/private-docker-registry/start
```

#### Tag an image

```
sudo docker tag 327db2da537e localhost:5000/example
```

#### Push an image

```
sudo docker push localhost:5000/example
```
