Update: 27-04-2023

There are package dependency issues on updating, see issue #3..

To update, run "dnf update --nobest"

Update: 19-04-2023

Well, well, well..


Something is ready.. not sure I should call it Alpha, Beta or Release Candidate, but I'll let you guys be the judges of that :)


But AWX-RPM 21.11.0 is now available for install..


The install playbook is available in the repo:


https://github.com/MrMEEE/awx-rpm-v2/tree/main/ansible


So far I have only tested on RHEL9, but CentOS Stream 9 and other variants should work as well..


Setup the AWX-RPM admin user, email and password in the inventory file, along with the hostname/IP of the machine to install to, and run:


ansible-playbook -i inventory awx-rpm-install.yml


and soon you should have a running AWX-RPM..


The webinterface will be available at https://<hostname>:8043/


Please report any issues at: https://github.com/MrMEEE/awx-rpm-v2/issues


Have fun, and feel free to report any issues and send any pull requests that makes sense..

---

Update: 28-02-2023

Lets create a community :)

First of all.. AWX-RPM is NOT, and I repeat NOT ready yet.. but I would say that the packaging is close to completed, and now there are some different stuff left:

- Getting all the services running

- Getting the services to talk to eachother

- Documentation

- Testing

- Building/modifying tools (needed for runtimes/installation)

And I could use some help.. I have created a RPM repo (GPG key and repo-file is in the description):

https://rpm.awx.wiki/AWX-RPM/

Which should be able to install on RHEL9 (probably also other EL9 like Alma/Rocky/Stream)

The installation for now should be something like (if someone have the time todo a writeup/test, I would appreciate it): [INSTALL](INSTALL.md)

I will try to create issues for the stuff that I find which is not working, and then we can hopefully solve it from there..

Happy bug hunting...

----
AWX-RPM Reignited

Hi guys

It's been some time.. And I know that there have been a lot of promises, and few of them have been kept..

The AWX-RPM project is back under my wings, and I hope push out new builds as fast as I can..

Recent work from the CentOS community and Red hat has made dependency building A LOT easier.. it's not perfect yet (and probably never will be), but it will make maintenance of the RPMS a lot less time consuming.

Because of this I have decided to completely reignite the AWX-RPM project, scrap all the old work (but keep the know-how) and if you want to follow the progress, follow this new repo, which will also be where new issues can be reported in time..

Right now I'm trying to build something to handle dependency building and exceptions to the depbuilding process... this is about 80% of the work..

From there I'll create the AWX-RPM core and services files and at some point create an installer..

When the core and services files are done, I'll see the project as Beta and ready for testing.. I hope this will happen within february, but it all depends on work pressure and family, so have patience.

However, when this is done, I'm really confident that automatic builds should be rolling out without needing much effort from my side.

Thanks for all your patience, support and feedback.

Talk to you all soon..

**Install guide, tools, utilities will be located at: https://awx.wiki in time.. they are outdated for now

**LinkedIn group for Questions, support, talk and more: https://www.linkedin.com/groups/13694893/


-----------------------------------

scripts:
```
buildsrc: Build src.rpm packages for the generated spec files
changeversion: Change the AWX version we are working on
checkbuilds: Check status of builds
getsources: Get source files for generated spec files 
mockbuild: Build the generated src.rpm-files to rpms with mock
pypi2spec: Generate specfiles for the requirement files
single-mockbuild: (re)build a single build, also generating a new src.rpm before build the rpm
```
