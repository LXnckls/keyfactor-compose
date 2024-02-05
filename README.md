# Keyfactor Container Demo Setup

Setting up Keyfactor products and components quickly and easily using Container technology with Docker or Podman Compose.

## Overview

**EJBCA, SignServer and other Keyfactor PKI solutions** can be deployed in many different flavours. For test and demo purposes the easiest way might be the usage of a container environment.

This project provides a **basic eval setups based on Docker/Podman Compose**. Therefore it can easily be deployed in local environments and adjusted according to specific use cases and requirements.


## [EJBCA](./ejbca/ejbca-compose.md)

Keyfactor EJBCA **certificate authority** is based on an open source community project. Therefore, anybody can easily setup the **EJBCA Community Edition** without any restrictions.

However, the **EJBCA Enterprise Edition** provides further modules and functionality not part of the free package.


## [SignServer](./signserver/signserver-compose.md)

Keyfactor SignServer **digital signature solution** is also based on a open source community project.


## [Compose Tips](./compose/compose.md)

Container technology provides an easily reproduceable and customizable deployment for customer and partner demo or evaluation environments. Therefore, this section contains some general basic tips to prepare and manage the compose environment.

> **NOTE** - All container example commands asume `podman`as the underlying container engine. However, most command switched or parameters should also work with `docker`.
