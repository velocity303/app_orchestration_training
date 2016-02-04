## Application Orchestration Training

### Setup Instructions

1. Clone this repository down to your local environment on your machine.
```
git clone https://github.com/velocity303/app_orchestration_training.git
```
2. Install Vagrant ([installation documentation](https://docs.vagrantup.com/v2/installation/))
3. Install Virtualbox ([Virtualbox Download](https://www.virtualbox.org/wiki/Downloads))
4. Install required vagrant plugins for vagrant environment
```
  $ vagrant plugin install oscar
  $ vagrant plugin install vagrant-hosts
  $ vagrant pluing install vagrant-reload
  $ vagrant plugin install vagrant-multiprovider-snap
```

5. Bring up environment with vagrant up puppet-master

### General Overview
 1. Slides Providing General Overview (10 min)
    - App Orchestration Terminology
      - Environment Graph
      - Component
      - Environment Resource/Service
    - Common Use Cases
      - LAMP Stack
      - Load Balancer + Web App
      - Clear and Defined Deployments for Infrastructure (Not only applications)
 2. Demonstration of App Orchestration Setup in detail (15 min)
    - Run through of key setup requirements:
      - Create user for orchestration and assign correct permissions.
      - Orchestrator.conf
      - app_managmenet puppet.conf setting
      - Change use_application_services from false to true in PE Infrastructure group in the console.
      - Use cached catalogs - Mirroring functionality of direct puppet. Use puppet code for this?
      - Disable pluginsync
      - site{} block in site.pp - Importance and relation to Environment Scope
 3. Self runthrough of App Orchestration setup + initial snapshot of set up environment (10 min)
 4. Introductory Set Up of App Orchestration with Wordpress (preloaded example - 10 min)
    - Students to walk through the steps - mostly uncommenting already made code vs writing themselves.
    - Running through puppet app show/ puppet job run - modifying site block etc.
 5. Recap of first exercise ( 5 minutes )
 6. Walk through recommendations for preexisting profiles becoming App Orchestration examples. ( 20 min )
    - defined types vs. class declarations for applications
    - creation of an environment service resource - format and parameter matching.
 7. Exercise of transforming existing profiles to work with Application Orchestration ( 15 min )
    - Recommendation for integrating preexisting profiles for app orchestration - find some simple examples.
 8. Recap and touch on how integration with code manager/direct puppet can lead to defined deployment windows for customers vs. depending on git push's and code manager deploys for this functionality. ( 15 min )
 9. If time permits - third example with more advanced topics - using require instead of consume/ 3 or more nodes involved.

# How to use this stack

This stack bootstraps itself by

1. Installing with an answer file that configures code manager to pull down from the app orchestration training control repo. 
2. Running a code manager deployment
3. Running puppet agent -t

# This Vagrant Stack is Based on the puppet-debugging-kit and npwalker-control-repo

Please follow the setup instructions for the debugging kit before cloning down this repo.

https://github.com/Sharpie/puppet-debugging-kit
https://github.com/npwalker/control-repo.git
