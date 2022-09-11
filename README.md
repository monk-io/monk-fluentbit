# Tensorflow & Monk
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
git clone https://github.com/Burakhan/monk-fluentbit
```

## Load Template
```bash
cd monk-fluentbit
monk load MANIFEST
```


#### Let's take a look at the themes I have installed.
```bash
foo@bar:~$ monk list monk-fluentbit
✔ Got the list
Type      Template                  Repository  Version  Tags
runnable  monk-fluentbit/fluentbit  local       -        -

```

## Deploy Stack
```bash
foo@bar:~$ monk run monk-fluentbit/fluentbit
? Select tag to run [local/monk-fluentbit/fluentbit] on: mnk
✔ Starting the job: local/monk-fluentbit/fluentbit... DONE
✔ Preparing nodes DONE
✔ Checking/pulling images...
✔ [================================================] 100% fluent/fluent-bit:latest mnk-2
✔ Checking/pulling images DONE
✔ Started local/monk-fluentbit/fluentbit

🔩 templates/local/monk-fluentbit/fluentbit
 └─🧊 Peer mnk-2
    └─🔩 templates/local/monk-fluentbit/fluentbit
       └─📦 dd9b3705c227840e6e28362cbc7b8e91-ntbit-fluentbit-monk-fluentbit
          ├─🧩 fluent/fluent-bit:latest
          └─🔌 open tcp 13.48.137.73:24224 (0.0.0.0:24224) -> 24224

💡 You can inspect and manage your above stack with these commands:
        monk logs (-f) local/monk-fluentbit/fluentbit - Inspect logs
        monk shell     local/monk-fluentbit/fluentbit - Connect to the container's shell
        monk do        local/monk-fluentbit/fluentbit/action_name - Run defined action (if exists)
💡 Check monk help for more!
```


## Configuration
The fluentbit configuration file is in app/config.conf.
The fluentbit parser file is in app/parser.conf.


## Stop, remove and clean up workloads and templates

```bash
monk purge -x -a
```