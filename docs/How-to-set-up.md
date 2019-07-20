How to set up the workflow locally
==================================

1. [Install Jenkins](https://jenkins.io/doc/book/installing/). Remember the 
password.
2. [Configure Jenkins](Configure\_Jenkins.md)

3. [Install Jenkins Job Builder](https://docs.openstack.org/infra/jenkins-job-builder/)
4. Clone **Jenkins\_yamls** repository:

```
git clone git@github.com:morriell/Jenkins_yamls.git ./
```

5. Create a configuration file for **JJB** named jenkins\_jobs.ini. This file 
should be placed in a root of just-downloaded repo. The file should look as 
follows:

```
[jenkins]
query_plugins_info=False
user=jenkins
password=*jenkins_admin_pass*
url=http://127.0.0.1:8080

```

*This file was excluded from the repo as it contains sencible data*

The password for this configuration is the same as you have used while 
installing Jenkins in a step 1.

6. Run **JJB** to install tasks:

```
jenkins-jobs --conf ./jenkins_jobs.ini update jobs
```

7. [Check](How-to-check.md) the workflow running.
