# Fluentbit & Monk
This repository contains Monk.io template to deploy Fluentbit either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

# Prerequisites
- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)

#### Make sure monkd is running.
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


#### Let's take a look at the themes I have installed.
```bash
foo@bar:~$ monk list fluentbit
✔ Got the list
Type      Template                  Repository  Version  Tags
runnable  fluentbit/fluentbit  local       -        -

```

## Deploy Stack
```bash
foo@bar:~$ monk run fluentbit/fluentbit
? Select tag to run [local/fluentbit/fluentbit] on: mnk
✔ Starting the job: local/fluentbit/fluentbit... DONE
✔ Preparing nodes DONE
✔ Checking/pulling images...
✔ [================================================] 100% fluent/fluent-bit:latest mnk-2
✔ Checking/pulling images DONE
✔ Started local/fluentbit/fluentbit

🔩 templates/local/fluentbit/fluentbit
 └─🧊 Peer mnk-2
    └─🔩 templates/local/fluentbit/fluentbit
       └─📦 dd9b3705c227840e6e28362cbc7b8e91-ntbit-fluentbit-fluentbit
          ├─🧩 fluent/fluent-bit:latest
          └─🔌 open tcp 13.48.137.73:24224 (0.0.0.0:24224) -> 24224

💡 You can inspect and manage your above stack with these commands:
        monk logs (-f) local/fluentbit/fluentbit - Inspect logs
        monk shell     local/fluentbit/fluentbit - Connect to the container's shell
        monk do        local/fluentbit/fluentbit/action_name - Run defined action (if exists)
💡 Check monk help for more!
```


## Configuration
The fluentbit configuration file is in app/config.conf.
The fluentbit parser file is in app/parser.conf.


## Stop, remove and clean up workloads and templates

```bash
monk purge -x -a
```