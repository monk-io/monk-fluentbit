# Fluentbit & Monk

This repository contains Monk.io template to deploy Fluentbit either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

## Prerequisites

- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)

### Make sure monkd is running

```bash
foo@bar:~$ monk status
daemon: ready
auth: logged in
not connected to cluster
```

## Clone Repository

```bash
git clone https://github.com/monk-io/fluentbit
```

## Load Template

```bash
cd fluentbit
monk load MANIFEST
```

### Let's take a look at the themes I have installed

```bash
foo@bar:~$ monk list fluentbit
✔ Got the list
Type      Template                  Repository  Version  Tags
runnable  fluentbit/fluentbit  local       -        -

```

## Deploy Stack

```bash
foo@bar:~$ monk run fluentbit/fluentbit
```

## Configuration

The fluentbit configuration file is in app/config.conf.
The fluentbit parser file is in app/parser.conf.

## Stop, remove and clean up workloads and templates

```bash
monk purge -x -a
```
