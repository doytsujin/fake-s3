fakes3
=======

Alpine Linux based dockerfile for [deppy/fake-s3](https://registry.hub.docker.com/u/deppy/fake-s3/)

Deploys [fake-s3](https://github.com/jubos/fake-s3) in a Docker container.

To create a deployment:

        docker run --name my_s3 -d deppy/fake-s3

Service exposed on port 4569.  Credentials are ignored.
See [fake-s3](https://github.com/jubos/fake-s3) README for details/limitations.

If you want fake-s3 to be exposed on your Docker host on port 4569, then

        docker run --name my_s3 -p 4569:4569 -d deppy/fake-s3

If you want the container to use a volume, then

        docker run --name my_s3 -v /fakes3_root -d deppy/fake-s3

The fake-s3 root directory will then be added as a volume on the Docker host.  To get the volume

        docker inspect --format "{{range .Mounts}}{{.Source}}{{end}}" my_s3

Based off of [lphoward/fake-s3](https://github.com/lphoward/fake-s3)
