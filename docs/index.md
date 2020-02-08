# CAPES Docs

TODO: LOGO

## What is CAPES?

CAPES is an operational-focused service hub for segmented, self-hosted, and offline (if necessary) incident response, intelligence analysis, and hunt operations.

## Quickstart Guide

For those who don't need a full installation walkthrough, you can get rolling quickly with:

```shell
sudo yum install git -y
git clone https://github.com/capesstack/capes-docker.git
cd capes-docker
sudo sh deploy_capes.sh
```

This will start the automated build of:

- Install Docker
- Pull images and start a containerized services for:
    - Elasticsearch
    - Kibana
    - Heartbeat
    - Auditbeat
    - Packetbeat
    - Metricbeat
    - Etherpad
    - Gitea
    - Draw.io
    - Rocketchat
    - Mumble
    - TheHive
    - Nginx
    - CyberChef
    - Portainer

## Services

- Rocketchat (Chat)
- Etherpad (Collaboration-style documentation)
- Gitea (Version controlled documentation)
- TheHive (Incident Response)
- Draw.io (Diagramming)
- CyberChef (Data analysis)
- Mumble (VoIP)
- Beats (security auditing, network flows, and performance and health metrics)
- Kibana (Data visualization)
- Portainer (Container management)

TODO: OVERVIEW DIAGRAM







## Swag

Interested in some CAPES swag? Send me a email to contact [at] capesstack[.]io and I’ll send you some laptop decals.

If you’re interested in CAPES t-shirts, we parter with TeeSpring for those. Feel free to check out our [storefront](https://teespring.com/stores/capesstack). We don’t make a penny on these - 100% of the profits go to the National Alliance to End Homelessness.

## Training & Professional Services

While CAPES is a FOSS project (and always will be) we’ll attempt to support deployment questions via the GitHub Issues page, if you need training or PS, please feel free to check out some options over at [Perched](http://perched.io/)