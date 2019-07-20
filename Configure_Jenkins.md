Configure Jenkins
=================

* Check that the following plugins were installed (In case something is missed, 
install it):                                                                    
    * GitHub plugin                                                             
    * PowerShell plugin                                                         
    * SSH Agent plugin                                                          
    * Slave setupPlugin                                                         
    * Workspace Cleanup Plugin                                                  
    * SSH Agent Plugin                                                          
    * Parameterized Trigger plugin                                                 

* Create SSH key with **ssh-keygen**. Place one to Jenkins credentials and 
another one to GitHub. In Jenkins the **ID** of credentials should be 
**morriell** as this id is used in (one of jobs)[jobs/triggered\_job.yaml]
* In a repository, changes in wich should trigger Jenkins jobs (in my case this 
is (jenkins-test)[https://github.com/morriell/jenkins-test] repo), create a 
token for hook management:
	* Create a token on GitHub with **admin_repo** priviliges; 
	* Place this token to Jenkins as a "Secret text" credentials;
	* In Jenkins global settings in a GitHub section, add a GitHub server using
	credentials added on the previous step; Check "Manage hooks" tick.

* Create slave nodes:
	* for Linux *master* may be used or you may create another node. Put a label 
	_**linux**_ on this node.
	* for Windows some tuning is needed. Go to Jenkins -> Settings -> Global 
	Security Settings. In **Agents** section check **TCP port for inbound 
	agents** as random. Then in additional section check "Inbound TCP Agent 
	Protocol/4 (TLS encryption)". After this tunning the connection method 
	"Launch agent by connecting it to master" may be used. So, create a windows 
	slave using this connection method with _**windows**_ label. Then connect to
	the master from the slave.

<!--
* In a job that is supposed to be triggered by a hook:
	* in "SCM" section fill in Git repository settings (repository URL, 
	credentials, branch); SSH key from the first step may be used;
	* in a "Triggers" section check "GitHub hook trigger for GITScm polling".
* A hook on GitHub will be created automatically
-->
