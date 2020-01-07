# Hosts

|                        | Heroku                   | DigitalOcean                      | NodeChef                        | Linode                 |
| ---------------------- | ------------------------ | --------------------------------- | ------------------------------- | ---------------------- |
| **Database**           | Postgres, Redis          | Postgres, MySQL, Redis            | MongoDB, Postgres, MySQL, Redis | Any (requires install) |
| **CDN**                | ❌                       |  ✅                               | ❓                             | ✅                     |
| **Deployment via git** | ✅                       | ❓(via Dokku or Nanobox w/ setup) | ✅ * Maps to branch            | ❌                     |
| **Frameworks**         | LAMP, Ruby, Python, Node | LAMP, LEMP, Ruby, Python, Node    | LAMP, Ruby, Python, Node        | Any (requires install) |

## Heroku

Heroku's big draw is the deploy with git feature. It has a lot of ease of use tools for devs.

__Pros:__
* Easy to use
* Deployment via git

__Cons:__
* Gets expensive real fast
* Need to use seperate service for CDN

### Cost

The free plan is only really good for testing. The Hobby plan is intended for small apps and development and can be a pain to upgrade but can get a server with database for $16/mo. With the professional plan we can have a server with a database for around $75/mo

#### Dynos (Servers)

| Dyno        | Price  | Memory |
| ----------- | ------ | ------ |
| Hobby       | $7/mo  | 0.5 GB |
| Standard 1x | $25/mo | 0.5 GB |
| Standard 2x | $50/mo | 1 GB   |

#### Databases

| Type       | Price   | Rows | Memory | Storage | Connections |
| ----       | ------  | ---- | ------ | ------- | ----------- |
| Hobby      | $9/mo   | 1M   | -      | -       | -           |
| Standard 0 | $50/mo  | -    | 4 GB   | 64 GB   | 120         |
| Standard 1 | $200/mo | -    | 8 GB   | 256 GB  | 400         |

## DigitalOcean

__Pros:__ 
* Affordable
* Many plans to fit needs
* Dedicated CDN server type

__Cons:__ 
* no out-of-box deployment via git

### Promo

Free $100, 60-day credit for new users.

### Cost

Below is a detailed breakdown of thier pricing. You could get a virtual server with a database for as little as $10/mo or $15/mo with a CDN.

#### Shared CPU

| Price   | Memory | vCPU | Transfer | SSD Disk Space |
| -----   | ------ | ---- | -------- | -------------- |
| $5/mo   | 1 GB   | 1    | 1 TB     | 25 GB          |
| $10/mo  | 2 GB   | 1    | 2 TB     | 50 GB          |
| $15/mo  | 3 GB   | 1    | 3 TB     | 60 GB          | 
| $15/mo  | 2 GB   | 2    | 3 TB     | 60 GB          |
| $15/mo  | 1 GB   | 3    | 3 TB     | 60 GB          |
| $20/mo  | 4 GB   | 2    | 4 TB     | 80 GB          |
| $40/mo  | 8 GB   | 2    | 4 TB     | 160 GB         |
| ...     | ...    | ...  | ...      | ...            |
| $960/mo | 192 GB | 32   | 12 TB    | 3,840 GB       |

#### Balanced

| Price   | Memory | vCPU | Transfer | SSD Disk Space |
| -----   | ------ | ---- | -------- | -------------- |
| $60/mo  | 8 GB   | 2    | 4 TB     | 25 GB          |
| $120/mo | 16 GB  | 4    | 5 TB     | 50 GB          |
| ...     | ...    | ...  | ...      | ...            |

#### CPU-Optimized

| Price   | Memory | vCPU | Transfer | SSD Disk Space |
| -----   | ------ | ---- | -------- | -------------- |
| $40/mo  | 4 GB   | 2    | 4 TB     | 25 GB          |
| $80/mo  | 8 GB   | 4    | 5 TB     | 50 GB          |
| ...     | ...    | ...  | ...      | ...            |

#### Memory-Optimized

| Price   | Memory | vCPU | Transfer | SSD Disk Space |
| -----   | ------ | ---- | -------- | -------------- |
| $90/mo  | 16 GB  | 2    | 4 TB     | 50 GB          |
| $110/mo | -      | -    | -        | 150 GB         |
| $140/mo | -      | -    | -        | 300 GB         |
| $180/mo | 32 GB  | 4    | 6 TB     | 100 GB         |
| $220/mo | -      | -    | -        | 300 GB         |
| $280/mo | -      | -    | -        | 600 GB         |
| ...     | ...    | ...  | ...      | ...            |

#### Databases

| Price  | Memory | vCPU | Disk  | Standby Nodes |
| ------ | ------ | ---- | ----- | ------------- |
| $15/mo | 1 GB   | 1    | 10 GB | 0             |
| $30/mo | 2 GB   | 1    | 25 GB | 0             |
| $50/mo | 2 GB   | 1    | 25 GB | 1             |
| $60/mo | 4 GB   | 2    | 38 GB | 0             |
| ...    | ...    | ...  | ...   | ...           |

#### CDN

| Price | Storage | Transfer | Aditional Storage | Additional Transfer |
| ----- | ------- | -------- | ----------------- | ------------------- |
| $5/mo | 250 GB  | 1 TB     | $0.02/GB          | $0.01/GB            |

[More info](https://www.digitalocean.com/pricing/)


## NodeChef

__Pros:__
* Cheapest for small apps
* Out of the box command-line deployment
__Cons:__
* The most expensive for resource hungry apps

### Cost

Can get a server with a database for as low as $9/mo. A server with the equivilent specs as Heroku's base professional tier is $418/mo.

| Price  | Memory  | CPU | DB Memory | DB Storage |
| ------ | ------- | --- | --------- | ---------- |
| $9/mo  | 0.12 GB | 1   | 100MB     | 1 GB       |
| $25/mo | 0.5 GB  | 2   | 100MB     | 1 GB       |
| $19/mo | 0.12 GB | 1   | 200MB     | 2 GB       |
| $38/mo | 0.5 GB  | 2   | 200MB     | 2 GB       |
| ...    | ...     | ... | ...       | ...        |
| $2,245/mo | 4 GB | 8   | 20 GB     | 20 GB      |

[More Info](https://www.nodechef.com/pricing)

## Linode

Basically AWS before there was AWS.

__Pros:__
* Lots of plans
* Inexpensive
* Best value low-tier server 

__Cons:__
* A __lot__ of manual setup would be required unless you use something like Nanobox or docker containers

### Cost

Can get an entry level server for as low as $5/mo. For the same price as Heroku's professional plan, you can get a really beefy server.

### Nanode

Powerful Entry Level VMs

| Price  | Memory | CPU     | Storage | Transfer | Network In | Network Out |
| -----  | ------ | ---     | ------- | -------- | ---------- | ----------- |
| $5/mo  | 1 GB   | 1 core  | 25 GB   | 1 TB     | 40 GB/s    | 1 GB/s      |

### Standard

VMs With Balanced Power and Performance

| Price  | Memory | CPU     | Storage | Transfer | Network In | Network Out |
| -----  | ------ | ---     | ------- | -------- | ---------- | ----------- |
| $10/mo | 2 GB   | 1 core  | 50 GB   | 2 TB     | 40 GB/s    | 2 GB/s      |
| $20/mo | 4 GB   | 2 cores | 80 GB   | 4 TB     | 40 GB/s    | 4 GB/s      |
| $40/mo | 8 GB   | 4 cores | 160 GB  | 5 TB     | 40 GB/s    | 5 GB/s      |
| $80/mo | 16 GB  | 6 cores | 320 GB  | 8 TB     | 40 GB/s    | 6 GB/s      |
| ...    | ...    | ...     | ...     | ...      | ...        | ...         |
| $960/mo | 192 GB | 32 cores | 3840 GB | 20 TB  | 40 GB/s    | 12 GB/s     |

### High Memory

VMs Optimized for Memory Intensive Applications

| Price   | Memory | CPU     | Storage | Transfer | Network In | Network Out |
| -----   | ------ | ---     | ------- | -------- | ---------- | ----------- |
| $60/mo  | 24 GB  | 1 core  | 20 GB   | 5 TB     | 40 GB/s    | 5 GB/s      |
| $120/mo | 48 GB  | 2 cores | 40 GB   | 6 TB     | 40 GB/s    | 6 GB/s      |
| ...     | ...    | ...     | ...     | ...      | ...        | ...         |
| $960/mo | 300 GB | 16 cores | 340 GB | 9 TB     | 40 GB/s    | 9 GB/s      |

### Dedicated CPU

Dedicated VMs Optimized for CPU-Intensive Applications

| Price   | Memory | CPU      | Storage | Transfer | Network In | Network Out |
| -----   | ------ | ---      | ------- | -------- | ---------- | ----------- |
| $30/mo  | 4 GB   | 2 cores  | 80 GB   | 4 TB     | 40 GB/s    | 4 GB/s      |
| $60/mo  | 8 GB   | 4 cores  | 160 GB  | 5 TB     | 40 GB/s    | 5 GB/s      |
| $120/mo | 16 GB  | 8 cores  | 320 GB  | 6 TB     | 40 GB/s    | 6 GB/s      |
| ...     | ...    | ...      | ...     | ...      | ...        | ...         |
| $720/mo | 96 GB  | 48 cores | 1920 GB | 9 TB     | 40 GB/s    | 9 GB/s      |

[More Info](https://www.linode.com/pricing/)


## Other Services

### Back4App

Backend for your app. Allows you to build the front-end of your app without worrying about your backend/database.

### Nanobox

Build special docker containers and choose to deploy them on AWS, DigitalOcean, Linode or others.

### Dokku

Docker container that enables any host that supports docker to act as a Heroku-style host.
