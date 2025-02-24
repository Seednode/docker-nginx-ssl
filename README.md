## Building the image

To build the image, clone the repository and run the following command, optionally specifying an nginx version to build:

`./build.sh [nginx_version]`

Optionally, you can specify the Docker registry to be used by prepending the `REGISTRY` environment variable:

`REGISTRY=oci.seedno.de/seednode ./build.sh`

If no registry is specified, the images will be built as `local/nginx-ssl:<version>`.

If a registry is specified, the built images will be pushed to it once the build is finished.

If you would like images to also be tagged as `latest`, you can specify `LATEST=yes` as an environment variable:

`LATEST=yes ./build.sh`

These environment variables and arguments can be combined:

`REGISTRY=oci.seedno.de/seednode LATEST=yes ./build.sh 1.27.4`

The resulting images from the above command might look like this:

```
╰─❯ docker images
REPOSITORY                          TAG               IMAGE ID       CREATED          SIZE
oci.seedno.de/seednode/nginx-ssl    1.27.4            15ab73a29593   16 minutes ago   2.64MB
oci.seedno.de/seednode/nginx-ssl    latest            15ab73a29593   16 minutes ago   2.64MB
```
