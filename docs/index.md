# CAPES Documentation

TODO: LOGO

CAPESstack is an operational-focused service hub for incident response, intelligence analysis, and 
hunt operations. These open source tools are segmented and self-hosted (offline if necessary). In this 
latest verion of the project, all services have been containerized.

---

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

---

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

After deployment, you can go to https://[CAPES-ip] to view the services.

Passwords are written to ~/capes_credentials.txt in the event that they're needed.

> Note the `capes_credentials.txt` file is written to the home directory of user 1000. If that isn't 
you, you'll need to adjust the `deploy_capes.sh` script.

Please see the documentation, especially the Post Installation Documentation.


To do:

    SSL reverse proxy (HTTPS everywhere)
    Moar Beats (Metric, audit)
    Documentation (yay)
    Integrate additional services from TheHive Project (Hippocampe, Cortex)
