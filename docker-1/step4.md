In the last step we just started a container without any customization. Let's have a look at the `docker run` options. At first we'll stop the current running container by using the following command:

`docker stop <CONTAINER ID>`

The `CONTAINER ID` is generated by Docker dynamically so automated management is difficult. To obtain the ID of the running container we have to do some shell "magic":

`docker stop $(docker ps | grep nginx | awk '{print $1}')`{{execute}}`

Looks complicated, eh? Our Nginx container is stopped, so we need to use the `-a` (all) flag to include stopped container in the output:

`docker ps -a`{{execute}}

Note the `Exited` status.

To facilitate the work with containers Docker provides us with the `--name` flag. To start a container with a user-defined name `web`, issue:

`docker run --name web -d nginx`{{execute}}

We check the container's state by the already known command:

`docker ps`{{execute}}

Unlike the previous example the `NAMES` column now contains the user-defined name `web`.

In the `PORTS` column we see, that the Nginx running inside the container exposes a port 80 for HTTP access. In order to access the port from the outside the container, we need to add more options to the `docker run` command. Stop the container again:

`docker stop web`{{execute}}

The Nginx container is stopped, check it by issuing:

`docker ps -a`{{execute}}

Now re-run the container, assign a new name and a port for outside access:

`docker run --name webwithport -d -p 80:80 nginx`{{execute}}

Verify, whether Nginx is accessible from outside:

https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/