Mini-Jenkins
============

A Mini Jenkins with Blue Ocean plugin for pipeline
development/experimentations.


In This Repo
------------

You'll find a Vagrant environment consisting of a single VM: Bob Jenkins, the Jenkins master. This is an Ubuntu Xenial (16.04) base box, with 4 cores, and 4GB of RAM. It will set up Jenkins with Ansible (via Vagrants ansible_local provisioner) locally on the guest, therefore there is no need to set up anything on the host machine except VirtualBox + Vagrant.

Jenkins default username/password: admin/admin.

Usage
=====

Start and setup
---------------

    vagrant up

Where's the Jenkins port?
-------------------------

After the setup is complete and successfull, you can query the port forward for
the guests 8080 port via the following vagrant cli:

    vagrant port

Here's how it looks like in action
----------------------------------

[![asciicast](https://asciinema.org/a/430eCRoh4ZIdCfVD73of1sERQ.png)](https://asciinema.org/a/430eCRoh4ZIdCfVD73of1sERQ)


F.A.Q.
------

- Q: It has timeouts during the jenkins plugin installations...
 A: (sh)It happens, the jenkins ci mirror is not so reliable, try again via
 the `vagrant provision` command until it succeeds.

Happy hacking!
