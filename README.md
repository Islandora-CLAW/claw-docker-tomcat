# Islandora CLAW: Tomcat Docker Image

[![Docker Stars](https://img.shields.io/docker/stars/islandora/claw-tomcat.svg)](https://hub.docker.com/r/islandora/claw-tomcat/)
[![Docker Pulls](https://img.shields.io/docker/pulls/islandora/claw-tomcat.svg)](https://hub.docker.com/r/islandora/claw-tomcat/)
[![Contribution Guidelines](http://img.shields.io/badge/CONTRIBUTING-Guidelines-blue.svg)](./CONTRIBUTING.md)
[![LICENSE](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://packagist.org/packages/islandora/PDX)

## Introduction

Defines the Tomcat Docker image. 

Based on either [OpenJDK Docker Image](https://github.com/Islandora-CLAW/claw-docker-open-jdk) or
[OracleJDK Docker Image](https://github.com/Islandora-CLAW/claw-docker-oracle-jdk).

## Includes

* Tomcat 7
* Java 8 (Oracle or Open JDK)

## Build Arguments

| Variable       | Required | Default |
|----------------|----------|---------|
| TOMCAT_VERSION | no       |  7.0.68 |

**Example:**
```bash
docker build --build-arg "TOMCAT_VERSION=7.0.68" -t islandora/claw-tomcat .
```

## Environment Variables

| Variable              | Required | Default                                                                                              |
|-----------------------|----------|------------------------------------------------------------------------------------------------------|
| TOMCAT_ADMIN_USER     | no       | admin                                                                                                |
| TOMCAT_ADMIN_PASSWORD | yes      |                                                                                                      |
| JAVA_OPTS             | no       |                                                                                                      |
| CATALINA_OPTS         | no       | -server -XX:+CMSClassUnloadingEnabled -Djava.awt.headless=true -Djava.security.egd=file:/dev/urandom |

**Example (foreground, port 8080, auto-remove):**
```bash
docker run --rm -ti -p 8080:8080 -e "TOMCAT_ADMIN_PASSWORD=your_super_secure_password" islandora/claw-tomcat
```

## Commands

For convenience a number of commands are provided in the [commands](/commands)
folder.

| Command    | Arguments               | Defaults    | Notes                                                            |
|------------|-------------------------|-------------|------------------------------------------------------------------|
| build      |                         |             | Build this image with the default settings.                      |
| foreground | [port] [admin password] | 8080 random | Start tomcat in the foreground with the given port and password. |
| background | [port] [admin password] | 8080 random | Start tomcat in the background with the given port and password. |

## Maintainers/Sponsors

* UPEI
* discoverygarden inc.
* LYRASIS
* McMaster University
* University of Limerick
* York University
* University of Manitoba
* Simon Fraser University
* PALS
* American Philosophical Society
* common media inc.

Current maintainers:

* [Nigel Banks](https://github.com/nigelgbanks)
* [Nick Ruest](https://github.com/ruebot)

## Development

If you would like to contribute, please get involved by attending our weekly [Tech Call](https://github.com/Islandora-CLAW/CLAW/wiki). We love to hear from you!

If you would like to contribute code to the project, you need to be covered by an Islandora Foundation [Contributor License Agreement](http://islandora.ca/sites/default/files/islandora_cla.pdf) or [Corporate Contributor Licencse Agreement](http://islandora.ca/sites/default/files/islandora_ccla.pdf). Please see the [Contributors](http://islandora.ca/resources/contributors) pages on Islandora.ca for more information.

## License

[MIT](https://opensource.org/licenses/MIT)
