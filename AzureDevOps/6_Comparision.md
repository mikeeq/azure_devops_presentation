# Azure DevOps - Comparision to other CI solutions

Fun fact: Github Actions

## Modern CIs

### GitHub Actions

Link: <https://github.com/pricing>
Docs: <https://help.github.com/en/actions>

Free: Basics for teams and developers
  Unlimited public/private repositories
  Unlimited collaborators
  2,000 Actions minutes/month
  Free for public repositories
  500MB of GitHub Packages storage
  Free for public repositories
  Community Support

Paid:
  Team: 3,000 Actions minutes/month $4 per user/month
  Enterprise: 50,000 Actions minutes/month


### CircleCI

Link: <https://circleci.com/pricing/>
Docs: <https://circleci.com/docs/>

Free
  Features include:
    2,500 free credits/week
    Run 1 job at a time
    Build on Linux and Windows

Paid:
  Starting at $30 per month

SELF-HOSTED: $35/month per user

VM and Docker based agents (Executors)
Different VM sizes

Orbs: ready to use scripts/automation for deploying/building/testing code

### DroneCI

Link: <https://drone.io>

OpenSource: <https://github.com/drone/drone>
Enterprise: <https://drone.io/enterprise/>
Cloud version only available for opensource projects.

Docker based agents

```
CPU threads: 48
model name	: AMD EPYC 7401P 24-Core Processor
```


### TravisCI

Link: <https://travis-ci.com/>
Docs: <https://docs.travis-ci.com/user/tutorial/>
```
CPU threads: 2
model name	: Intel(R) Xeon(R) CPU
```

VMs based Agents
GitHub only
Slow

- Appveyor:

### Semaphore

Link: <https://semaphoreci.com/>

Free:
  Standard
    1 x Linux / Docker
    1 x macOS
    $10/Month Usage = 1300 Min

  Open-source
  4 x Linux / Docker
  1 x macOS

Paid:
  Pay-as-you-go
    Linux/Docker/Android: starts at $0.000125/sec
    macOS/iOS: $0.0050/sec

Self-Hosted: coming soon...

Different VM sizes available:
Linux
Linux-2 (2 vCPU @ 3.4GHz (Turbo 4.0GHz), 4GB RAM, 25GB RAM drive)
Linux-4 (4 vCPU @ 3.4GHz (Turbo 4.0GHz), 8GB RAM, 35GB RAM drive)
Linux-8 (8 vCPU @ 3.4GHz (Turbo 4GHz), 16GB RAM, 45GB RAM drive)
macOS
macOS-4 (4 vCPU @ 2.7GHz E5-2697v2, 8GB RAM, 50GB drive)
macOS-8 (8 vCPU @ 2.7GHz E5-2697v2, 16GB RAM, 50GB drive)

## Good old friends

Jenkins:
  Pros:
    - multiple jobs per 'agent' - executors
    - pluginable
  Cons:
    - good old Java monster
    - self-hosted only

TeamCity:
  Pros:
    - multiple built-in features
      - displaying code coverage, tests results in dashboards, statistics, etc.
    - self-hosted and cloud beta: <https://blog.jetbrains.com/teamcity/2019/12/sign-up-for-the-teamcity-cloud-beta/>
    - Old school .Net developers should love it!
    - not so hard to maintenance
    - docker version available: <https://hub.docker.com/r/jetbrains/teamcity-server/>
  Cons:
    - build configurations (job definitions) number is limited and it depends on how many agent licences you buy
      - 100 build configurations free
      - 3 build agents free
    - one agent licence gives you
      - 10 additional build configurations
      - costs 299 EUR

## Links

- List of Continuous Integration services: <https://github.com/ligurio/awesome-ci>
