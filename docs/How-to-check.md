How to try that it works
========================

WARNING
-------
The system is set up on my Home PC, so for some reason it may be out-of-work. In 
case you need to check it, but [Jenkins](https://github.com/morriell/jenkins-test) 
or some of it's slaves is off, please contact me <morriell@yandex.ru>.

Automatically per-commit
------------------------

1. Push any commit to [Jenkins-test](https://github.com/morriell/jenkins-test) 
repo
2. Go to [Jenkins](http://37.145.114.185:8080) and watch the 
[Triggered job](http://37.145.114.185:8080/job/Triggered\_job/) working. This 
job contains links to downstream jobs. Those downstream jobs that were triggered
on corresponding nodes and contain artifacts.

Manually
--------

1. Go to [Triggered job](http://37.145.114.185:8080/job/Triggered\_job/) and 
click "Run with parameters".
2. Set up parameters you wish to run with.
3. Watch the job running and calling downstream jobs. The artifacts may be found
in those downstream jobs.
