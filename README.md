# Jenkins_yamls
A repo for yaml-configuration files

##Jenkins setups

* Create SSH key. Place one to Jenkins and another one to GitHub
* Create a token for hook management:
	* Create a token on GitHub with *admin_repo* priviliges; 
	* Place this token to Jenkins as a "Secret text" credentials;
	* In Jenkins global settings in a GitHub section, add a GitHub server using credentials added on the previous step; Check "Manage hooks"
* In a job that is supposed to be triggered by a hook:
	* in "SCM" section fill in Git repository settings (repository URL, credentials, branch); SSH key from the first step may be used;
	* in a "Triggers" section check "GitHub hook trigger for GITScm polling".
* A hook on GitHub will be created automatically
