Jenkins\_yamls
=============

A repo for yaml-configuration files

* [How to set up the workflow locally](docs/How-to-set-up.md)
	* [Configure Jenkins](docs/Configure_Jenkins.md)
* [How to check the workflow](docs/How-to-check.md)

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
