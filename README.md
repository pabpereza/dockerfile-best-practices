# Curated Dockerfiles examples
This repository contains examples of Dockerfiles using the docker multi stage build feature. This approach allows to build a Docker image with a minimal footprint, by copying only the necessary files from the build stage to the final image and using non-root user to run the application.


For more information about multi stage builds, please refer to the [official documentation](https://docs.docker.com/develop/develop-images/multistage-build/).


## Examples by language or technology
* [Java](java/)
* [Python](python/)
* [Node](node/) WIP!!


# How to use these examples
Each example contains a Dockerfile and Dockerfile.old. The .old file contains simple Dockerfile without multi stage builds and the Dockerfile contains the multi stage build version. 

To build the image, you can use the following command:
``` bash
docker build -t <image_name> .
```

If you want to build the image using the old Dockerfile, you can use the following command:
``` bash
docker build -t <image_name> -f Dockerfile.old .
```

To run the image, you can use the following command:
``` bash
docker run -it <image_name>
```


# How contribute to this repository
If you want to contribute to this repository, please follow these steps:
1. Fork this repository
2. Add your example in a new folder or update an existing example (always grouped by language or technology)
3. Create a pull request with your changes
