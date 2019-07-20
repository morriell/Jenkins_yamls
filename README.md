Jenkins\_yamls
=============

A repo for yaml-configuration files

The task
========

Please, implement CI project with following requirements:

Environment: 
------------

1. jenkins master + 2 slaves:

	* Linux
	* Windows

2. Choose Linux distributive and Windows version by yourselves.


Work-flow requirements: 
-----------------------

1. A git commit to some project triggers following jobs in parallel:

	* a job on a windows host
	* a job on a linux host

2. Also, a user should be able to trigger the same work-flow and have options to
specify:

	- platform: windows, linux or both.
	- git branch or tag

3. Windows and linux job must output hardware parameters in the unified format:

	* Host name:
	* OS version:
	* CPU cores: 
	* RAM:
	* HDD size: for C:\ or /
	* HDD disk usage: for C:\ or /

4. Hardware parameters from p.3 have to be published as a job artifact.
5. The work-flow have to be implemented using Jenkins Job Builder tool.
6. The jobs must not require specific third party tools and relay on generic 
software which is always available on a minimal OS install.

7. The jobs must not require admin privileges.

Jenkins setups
==============

* Create SSH key. Place one to Jenkins and another one to GitHub
* Create a token for hook management:
	* Create a token on GitHub with *admin_repo* priviliges; 
	* Place this token to Jenkins as a "Secret text" credentials;
	* In Jenkins global settings in a GitHub section, add a GitHub server using
	credentials added on the previous step; Check "Manage hooks"
* In a job that is supposed to be triggered by a hook:
	* in "SCM" section fill in Git repository settings (repository URL, 
	credentials, branch); SSH key from the first step may be used;
	* in a "Triggers" section check "GitHub hook trigger for GITScm polling".
* A hook on GitHub will be created automatically
