# Installation

This is stuff.

## Requirements

There has not been extensive testing with these requirements, but all of these services have run without issue on a single virtual machine with approximately 20 users and no issue for a week (I’m sure it would have kept running, 1 week was just when we stopped our testing). That said, your mileage may vary.

- clean installation of Centos/7

While the OS version isn’t a hard requirement, all testing and development work has been done with CentOS 7.6 (Core).


Get CAPES
Finally, here we go.

sudo yum install git -y
git clone https://github.com/capesstack/capes-docker.git
cd capes-docker
sudo sh deploy_capes.sh


Get Started
After the CAPES installation, you should be able to browse to http://your_capes_system (or http://your_capes_IP if you don’t have DNS set up) get get to the CAPES landing page and start setting up services by following the post installation steps.

Although most of these services are fairly intuitive, I strongly recommend that you look at the Build, Operate, Maintain guides for these services before you get going too far. A few of the services launch a configuration pipeline that is obnoxious to restart if you don’t complete it the first time (I’m looking at you TheHive and Gitea).