# EJBCA Compose Setup

[[Back to Overview](../README.md)]

The Certificate Authority (CA) solution is provided as an **official Keyfactor container image**.

The **EJBCA Community Edition** is officially published on the [DockerHub Registry](https://hub.docker.com/) under the [Keyfactor publisher](https://hub.docker.com/u/keyfactor).

If you are interested in testing the fully-feature **EJBCA Enterprise Edition** you have to [contact Keyfactor](https://www.keyfactor.com/products/ejbca-enterprise/) to access those images.


## EJBCA-CE (Community Edition)

**Pull image** from DockerHub registry:

    > podman pull keyfactor/ejbca-ce


**Simple `podman run` setup**:

    > podman run -it --rm -p 8080:8080 -p 8443:8443 -h myca -e TLS_SETUP_ENABLED="simple" -e keyfactor/ejbca-ce -n ejbca


> **NOTE** - The parameter `TLS_SETUP_ENBLED="simple"` allows un-authenticated access to the EJBCA admin web console.
