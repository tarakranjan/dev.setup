# About
---
 
 Toolkit to setup  Devleoper Box  for Single Page Application
 
 Single-Page Applications (SPAs) are Web apps that load a single HTML page and dynamically update that page as the user interacts with the app.

## Prerequisites
---

Install the following software on Host Machine

|  S.No |  Software         | Version        |  
|-------|-------------------|----------------|
|   1   |  [ansible]        |   |
|   2   |  [Virtual Box]    | 5.1.6 r110634  | 
|   3   |  [Vagrant]        |   | 
|   4   |  [JDK]            |   | 
|   5   |  [Maven]          |   | 
|   6   |  [Git CLI Client] |   |  
|   7   |  [NVM]            |   |    
|   8   |  [Node.js]        |   | 



 
## Ansible Installation
---


### For Mac

Via Homebrew

```sh

    brew install ansible
    sudo launchctl limit maxfiles 1024 unlimited

```

* OR 

Via Native Python. Ensure XCode is Installed

```sh

    sudo easy_install pip
    sudo pip install ansible --quiet

```

To Upgrade Ansible later
```sh

    sudo pip install ansible --upgrade

```




## Reference Shortcuts 
```sh

    mkdir -p provision/{setup,deploy}/{defaults,files,handlers,meta,tasks,templates,vars}

```

 
 
[Virtual Box]: https://www.virtualbox.org/wiki/Downloads 
[Vagrant]: https://www.vagrantup.com/downloads.html
[JDK]: http://www.oracle.com/technetwork/java/javase/downloads/index-jsp-138363.html
[Maven]: https://maven.apache.org/download.cgi       
[Git CLI Client]: https://git-scm.com/downloads
[NVM]: https://github.com/creationix/nvm
[Node.js]: https://nodejs.org/en/
[ansible]: http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-pip
 
* Last Updated: 19th Oct 2016 
 
 
 

 
