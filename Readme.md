# About
---
 
 Toolkit to setup  Devleoper Box  for Single Page Application
 
 Single-Page Applications (SPAs) are Web apps that load a single HTML page and dynamically update that page as the user interacts with the app.

## Prerequisites
---

Install the following software on Host Machine

|  S.No |  Software         | Version        |  
|-------|-------------------|----------------|
|   1   |  [ansible]        | 2.1.2.0        |
|   2   |  [Virtual Box]    | 5.1.6 r110634  | 
|   3   |  [Vagrant]        | 1.8.6          | 
|   4   |  [JDK]            | 1.8.0_60       | 
|   5   |  [Maven]          | 3.3.9          | 
|   6   |  [Git CLI Client] | 2.10.1         |  
|   7   |  [NVM]            | 0.26.1         |    
|   8   |  [Node.js]        | v5.5.0         | 

* Last Updated: 19th Oct 2016 

 
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

Check Ansible Installation
```sh

    ansible -i inventory -m ping all
    ansible -i inventory -m setup all

```


To Install Java, Maven, Node, NPM etc
```sh

    ansible-playbook mac.setup.playbook.yml -i inventory 

```

##### Workspace Setup

```sh
cd  /Users/$USER
mkdir -p Workspace/B2B 
cd Workspace/B2B
```

##### Cloning From  Git Repo
```sh
git clone git@git.learn.cisco:b2b/knowledgecenter.git
git clone https://github.com/rajasoun/dev.setup.git
```

##### Start the Vagrant
```sh
export KC_DIR=/Users/$USER/Workspace/B2B/knowledgecenter
echo "export KC_DIR=/Users/$USER/Workspace/B2B/knowledgecenter" >> ~/.bashrc
vagrant up
```


## Reference Shortcuts 
```sh

    mkdir -p provision/{setup,deploy}/{defaults,files,handlers,meta,tasks,templates,vars}
    ansible-vault encrypt provision/setup/files/* --vault-password-file ./.vault_pass
    ansible-vault decrypt provision/setup/files/* --vault-password-file ./.vault_pass

```

 
 
[Virtual Box]: https://www.virtualbox.org/wiki/Downloads 
[Vagrant]: https://www.vagrantup.com/downloads.html
[JDK]: http://www.oracle.com/technetwork/java/javase/downloads/index-jsp-138363.html
[Maven]: https://maven.apache.org/download.cgi       
[Git CLI Client]: https://git-scm.com/downloads
[NVM]: https://github.com/creationix/nvm
[Node.js]: https://nodejs.org/en/
[ansible]: http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-pip
 
 
 
 

 
