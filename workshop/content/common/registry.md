As part of the challenge, you will need to use a Container Registry to host the images you build. You can obviously use any of the public container registries (e.g. DockerHub or Quay.io), but we wanted to avoid you needing an account for any of them. 

For this reason, we do provide you with a Container Registry hosted on this platform that will work as long as your challenge lasts (i.e. 24 hours).

The credentials to access this temporary container image registry are:

```
REGISTRY_HOST="{{ registry_host }}"
REGISTRY_USERNAME="{{ registry_username }}"
REGISTRY_PASSWORD="{{ registry_password }}"
```

To login to the registry using `docker`, run:

```
docker login -u {{ registry_username }} -p {{ registry_password }} {{ registry_host }}
```

If you have an existing image you wish to push to the image registry, first
tag it using:

```
docker tag myimage:latest {{ registry_host }}/myimage:latest
```

You can then push the image to the image registry using:

```
docker push {{ registry_host }}/myimage:latest
```

Feel free to use this registry or any one of your choice.