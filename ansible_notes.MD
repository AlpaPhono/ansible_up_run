# Studying Ansible

---

## Ansible UpandRunning notes

### Chapter 2
#### Installing Ansible

- Can be installed using one of the Python package managers
- Install Ansible inot a Python venv. (To avoid interfering with system)
- Ansible can manage windows systems but It can't be run by windows.

#### Loose Dependencies 
Some ansible plug-ins and modules require extra python libraries (working with windows or DOcker)
` pip install pywindrm docker `

#### Setting Up a Server for Testing 
The book suggests using Vagrant to set up a test server
*instructions on installing vagrant/virtualbox*

- Go to website and install virtualbox
> [install](https://www.virtualbox.org/wiki/Downloads)
- Install virtual box
>
 ```
    brew tap hashicorp/tap
    brew install hashicorp/tap/hashicorp-vagrant
```
- Run the following commands to create a Vagrant configuration file (Vagrantfile) for an Ubuntu/Focal 64-bit virtual machine image, and boot it:
```
    $ mkdir playbooks
    $ cd playbooks
    $ vagrant init ubuntu/focal64 $ vagrant up
```

The instructions in the book to run vagrant arent the best so I'll be referencing the hashicorp turtorials.
[tutorial](https://developer.hashicorp.com/vagrant/tutorials/getting-started/getting-started-project-setup)
---
__troubleShooting__

I went on AI to figure the problem
- Verify virtual box installation
	- ` vboxmanage --verison `
- Check Vagrant configuration can find virtualbox
	- ` vagrant box list `
So I ran ` vagrant up --provider virtualbox `
And I discovered that my version of virtualbox is too new for the version of vagrant I have installed.
---

