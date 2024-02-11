[[Back to Overview](../README.md)]

# EJBCA Compose Setup

EJBCA is an open source **Public-Key Infrastructure (PKI)** and **Certificate Authority (CA)** project that is maintained on [GitHub](https://github.com/Keyfactor/ejbca-ce).

The software is developed and commercially supported by [Keyfactor](https://keyfactor.com). The official **EJBCA Community Edition (CE) Container** is published on [DockerHub Registry](https://hub.docker.com/) under the [Keyfactor publisher](https://hub.docker.com/u/keyfactor).

If you are interested in testing the fully-featured **EJBCA Enterprise Edition** you have to [contact Keyfactor](https://www.keyfactor.com/products/ejbca-enterprise/) to access those images.

> [!NOTE]
> The Container deployment below only provides basic description of commands and configuration options. Further information on Containers, Docker and Compose can be found in chapter [Container Tips](../container/README.md).



## EJBCA-CE (Community Edition)

From a running container environment there are only a few simple steps to setup EJBCA-CE with Podman. Below you find a really **simple setup** without no security in place as well as a **Compose setup** with more control over the environment.



### Simple Setup

**Pull image** from [DockerHub Registry](https://hub.docker.com/r/keyfactor/ejbca-ce):

    > podman pull keyfactor/ejbca-ce


**Simple setup** using `podman run`:

    > podman run -it --rm -p 8080:8080 -p 8443:8443 -h myca -e TLS_SETUP_ENABLED="simple" -n ejbca keyfactor/ejbca-ce


> [!NOTE]
> The parameter `TLS_SETUP_ENBLED="simple"` allows un-authenticated access to the EJBCA admin web console.



### Compose Setup



## Documentation

Official EJBCA documentation can be found in the following locations.



### EJBCA Community

- [EJBCA CE Container Image](https://hub.docker.com/r/keyfactor/ejbca-ce) (DockerHub)
- [EJBCA CE](https://github.com/Keyfactor/ejbca-ce) (GitHub)
- [Start EJBCA Docker container, ephemeral instance](https://www.ejbca.org/case/start-ejbca-docker-container-temporary-instance/) (ejbca.org)
- [Start EJBCA Docker container, production-like settings](https://www.ejbca.org/case/start-ejbca-docker-container-production-like-settings/) (ejbca.org)



### Keyfactor (Public)

- [Quick Start Guide - Start EJBCA Container with Unauthenticated Network Access](https://doc.primekey.com/ejbca/tutorials-and-guides/quick-start-guide-start-ejbca-container-with-unauthenticated-network-access) (docs.primekey.com)
- [Tutorial - Start out with EJBCA Docker container](https://doc.primekey.com/ejbca/tutorials-and-guides/tutorial-start-out-with-ejbca-docker-container) (docs.primekey.com)
