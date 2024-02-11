[[Back to Overview](../README.md)]


# Container Tips

This chapter provides some tips for using **Podman** and **Compose** effectively.


## Install

Podman resources as well as installation instructions can be found here:

- [Podman](https://podman.io/)
- [Podman Desktop](https://podman-desktop.io/)
- [Compose Setup](https://podman-desktop.io/docs/compose/setting-up-compose)


## Run

There are two general ways to run a Container from a given image. The `podman run` commmand together with several options allows you to start an application with a single line but you have to add those parameters every time you want to run a new Container with the same settings.

Therefore, `podman compose up` allows defining the options in a configuration file called `compose.yaml` which can be used to define a certain setup in an easily reproduceable way.

### `podman run`

Running a container with `podman run` is the simplest way to start an application from an image, e.g.

    > podman run -it --rm -p 8080:8080 -p 8443:8443 -h myca -e TLS_SETUP_ENABLED="simple" -n ejbca keyfactor/ejbca-ce

Here are the **most important options** you can use with this command:

Option  | Meaning           | Notes
---     | ---               | ---
-d      | Detached          | Run container in background
-it     | Interactive Tty   | Allow console output
-e      | Environment       | Use variables
-h      | Hostname          | Internal container hostname
--rm    | ReMove            | Clean-up resources when stopping container
-p      | Port              | Published ports
-n      | Name              | Replaces random container name


### `podman compose up`

To use this command you first have to create a `compose.yaml` file which is descibed in a [separate document](./compose-config.md). With this configuration file in place you can simply run your environment with a single default command:

    > podman compose up -d

The **most important option** for this command is:

Option  | Meaning           | Notes
---     | ---               | ---
-d      | Detached          | Run containers in background



## Logs

When a Container is started, console messages are printed directly in the terminal window by default. However, in "detached" mode (option `-d`) console output is not directly visible.

To **identify a container instance** you can use the command:

    > podman ps [-a]

It lists the IDs and names of instances that are currently running. To also see existing but **stopped containers** you have to add the switch `-a`.

To see the **log output** you have to use the following command:

    > podman log <container_names_or_ids>

It supports the following options:

Option      | Meaning           | Notes
---         | ---               | ---
-f          | Follow            | Show output till `CTRL+C`is pressed
--tail [n]  | Tail              | Only show the last [n] lines of the output

To see the **console logs of all containers** started from a Compose file you can use this command:

    > podman compose logs -f


## Stop

There are several options to stop a container.

    > podman stop <container>


## Clean-Up