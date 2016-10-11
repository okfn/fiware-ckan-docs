# Installation and Admin Guide

## Introduction

CKAN can be installed in three different ways:

-   Installing from a Debian package.
-   Installing using a Docker image.
-   Installing from source.

The form of installation (what way to use) depends on how CKAN is going
to be used.

### Installing from a Debian package

Installing from a package works best if:

-   CKAN will be installed on an Ubuntu 14.04, 64-bit server, and
-   there will only be one CKAN website one each server.

For more information about how to install CKAN from a package, please
refer to the [official documentation].

### Installing using a Docker image

Installing using a [Docker] image works best if:

-   CKAN will be deployed to any server that can run Docker, regardless
    of operating system, and
-   the deployment mechanism remains the same when moving from vanilla
    CKAN to a heavily customised deployment.

For more information about how to install CKAN using a Docker image,
please refer to the [Fiware CKAN Docker image][1].

### Installing from source

Installing from source works best if none of the above is applicable,
namely:

-   CKAN needs to be installed on a 32-bit computer, or
-   CKAN is installed on a different version of Ubuntu, not 14.04, or
-   CKAN is installed on another operating system (eg. RedHat, CentOS,
    OS X), or
-   Multiple CKAN websites will be run on the same server, or
-   CKAN is installed for for development purposes

For more information about how to install CKAN from source, please refer
to the [official documentation][2].

## Configuration

CKAN is configured via a configuration file which is by default located
at `/etc/ckan/production.ini`.

The configuration file is loaded with a lot of default configurations
but for a better overview of what each configuration does or additional
configuration options not included by default, please refer to the
[official documentation][3].

## Sanity Check Procedures

After installing CKAN, to make sure everything works the simplest test
is to just visit the website and see if it responds. However it is also
recommended to run the tests to see if all functionality works as
expected.

To run tests one needs to set up a test environment with a test database
and preferably another Solr core (or instance) so that tests can be run
at any point in time without affecting the production environment data.

For tests it is required that development requirements are installed
which include the test suite and other important libraries used.

For more detailed information of how to set up a test environment and
run CKAN tests, please refer to the [official documentation][4]

## Diagnosis Procedures

CKAN uses Python's [standard library logging] which prints to standard
output/standard error. The web server that exposes CKAN is usually used
to direct standard output/standard error to log files. The deployment
documentation for example shows how [that is done with the Apache web
server configuration].

The level of logging per application is configured in the configuration
file (usually located at `/etc/ckan/production.ini`) where the levels
follow the logging level of Python's standard logging and is divided
into Pylons - the underlying web framework (default logging level
*WARNING*), the CKAN application (default logging level *INFO*), and
CKAN extensions (default logging level *DEBUG*).

  [standard library logging]: https://docs.python.org/2/howto/logging.html
  [that is done with the Apache web server configuration]: http://docs.ckan.org/en/latest/maintaining/installing/deployment.html#create-the-apache-config-file
  [official documentation]: http://docs.ckan.org/en/latest/maintaining/installing/install-from-package.html
  [Docker]: https://www.docker.com/
  [1]: https://hub.docker.com/r/fiware/ckan/
  [2]: http://docs.ckan.org/en/latest/maintaining/installing/install-from-source.html
  [3]: http://docs.ckan.org/en/latest/maintaining/configuration.html
  [4]: http://docs.ckan.org/en/latest/contributing/test.html
