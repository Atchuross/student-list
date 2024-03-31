
# Student-List

The goal of this project is to containerize 1 web app and 1 API + custom private repository for Docker images.



## Tech Stack

**Client:** HTML, CSS

**Server:** Python, Flask



## 1. Build and Test API

The first step was to build the Docker Image API. To achieve that, I have created a Dockerfile with all the different arguments needed.

![Dockerfile of API](https://raw.githubusercontent.com/Atchuross/student-list/master/image_rapport/Dockerfile.png)

This file image installs all the dependencies needed, then installs requirement.txt and runs the ".py" files.

I can test now if the API is working with curl command :
```shell
  curl -u toto:python -X GET http://<host IP>:<API exposed port>/pozos/api/v1.0/get_student_ages
```

And this is the response of the curl command : 

```shell
{
  "student_ages": {
    "alice": "12",
    "bob": "13"
  }
}
```

The first step is completely working!

## 2. IaC (Infrastructure As Code)

Our API is operational, so now we need to build the IHM. 
The IHM needs to be connected to our API, so we do that in the Docker-compose file.

This allowed me to build an IaC, a just simple files we deploy all our services.

The first step is to create the docker-compose file.

![docker-compose file](https://raw.githubusercontent.com/Atchuross/student-list/master/image_rapport/docker-compose.png)

After this docker files is OK, I can build it wit htis command :
```shell
  docker-compose build
```

And now I can access to the IHM at my serveur IP address : 

![Webapp + API](https://raw.githubusercontent.com/Atchuross/student-list/master/image_rapport/202403311829.gif)
## Authors

- [@atchuross](hhttps://github.com/Atchuross)

