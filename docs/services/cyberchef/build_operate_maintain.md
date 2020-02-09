# CyberChef
CyberChef was created, and is maintained, by the Government Communications Headquarters (GCHQ). GCHQ is one of the UK's security and intelligence agencies, working with its partners in MI5 and SIS. All credit for the service goes to their talented team.

_There are around 150 useful operations in CyberChef for anyone working on anything vaguely Internet-related, whether you just want to convert a timestamp to a different format, decompress gzipped data, create a SHA3 hash, or parse an X.509 certificate to find out who issued it._

_It’s the Cyber Swiss Army Knife._

## What
A simple, intuitive web app for analyzing and decoding data without having to deal with complex tools or programming languages. CyberChef encourages both technical and non-technical people to explore data formats, encryption and compression.

## Why
Digital data comes in all shapes, sizes and formats in the modern world – CyberChef helps to make sense of this data all on one easy-to-use platform.

## How
The interface is designed with simplicity at its heart. Complex techniques are now as trivial as drag-and-drop. Simple functions can be combined to build up a "recipe", potentially resulting in complex analysis, which can be shared with other users and used with their input.

For those comfortable writing code, CyberChef is a quick and efficient way to prototype solutions to a problem which can then be scripted once proven to work.

## Who
It is expected that CyberChef will be useful for cybersecurity and antivirus companies. It should also appeal to the academic world and any individuals or companies involved in the analysis of digital data, be that software developers, analysts, mathematicians or casual puzzle solvers.

## Documentation / Installation
See the [Build, Operate, Maintain page](build_operate_maintain.md) for detailed instructions.  

## Project Link
https://github.com/gchq/CyberChef

---

# CyberChef Build, Operate, Maintain
CyberChef was created, and is maintained, by the Government Communications Headquarters (GCHQ). GCHQ is one of the UK's security and intelligence agencies, working with its partners in MI5 and SIS. All credit for the service goes to their talented team.

_There are around 150 useful operations in CyberChef for anyone working on anything vaguely Internet-related, whether you just want to convert a timestamp to a different format, decompress gzipped data, create a SHA3 hash, or parse an X.509 certificate to find out who issued it._

_It’s the Cyber Swiss Army Knife._

There should probably be more here but...those GCHQ guys got their stuff together.

## Build

### Installation
Run the [CAPES deployment script](../deploy_capes.sh) or deploy manually:

Deploying with CAPES (recommended):
```
sudo yum install -y git
git clone https://github.com/capesstack/capes-docker.git
cd capes-docker
sudo sh deploy_capes.sh
```
Browse to `https://[CAPES-system]` and click the "CyberChef" from the "Services" dropdown.

Deploying manually:
```
sudo yum install -y docker
sudo groupadd docker
sudo usermod -aG docker "$USER"
sudo systemctl enable docker.service
sudo systemctl start docker.service
sudo docker run -d --restart unless-stopped --name capes-cyberchef -p 8000:8080 remnux/cyberchef:latest
```
Browse to `https://[CAPES-system]:8000`

## Operate
Drag the Operation to the Recipe, enter your input, and click "Bake!".

There are lots to experiment with.

## Maintain

### Package Locations
CyberChef location - https://hub.docker.com/r/remnux/cyberchef

### Update CyberChef
When it's time to update CyberChef, you can just grab the newest image and rerun the container build.
```
sudo docker pull remnux/cyberchef:latest
sudo docker stop capes-cyberchef
sudo docker rm capes-cyberchef
sudo docker run -d --network capes --restart unless-stopped --name capes-cyberchef -p 8000:8080 remnux/cyberchef:latest
```

## Troubleshooting
In the event that you have any issues, here are some things you can check to make sure they're operating as intended.

Is Docker running?
```
sudo systemctl status docker.service
```
Check to make sure it's active, if it isn't, try starting it with `sudo systemctl start docker.service`

Is the Cyberchef container running
```
sudo docker ps -a
```
Check to make sure that it isn't exited. Try `sudo docker start capes-cyberchef` or `sudo docker logs capes-cyberchef` to get a closer look.

Is the site accessible locally?
```
curl [capes_IP]:8000
or, check from inside the container with
sudo docker exec -it capes-cyberchef bash
curl localhost:8080
```

Check with the CyberChef project maintainers at https://github.com/gchq/CyberChef

If you're still unable to access the CyberChef page from a web browser, [please file an issue](https://github.com/capesstack/capes-docker/issues).
