ec2ssh
======

By Boris Kuzmanovic, Viafoura.

ec2ssh is a shell script that makes connecting to ec2 servers __ridiculously easy__.

ec2ssh displays your instances in a simple digest-like menu and prompts you to enter the server number. Once you enter it, the script opens an ssh connection to the server.

Usage
-----

Parameters are optional, but very handy if you run many sites. The parameter acts as a filter to narrow down the list of servers.

``` shell
$ ec2ssh
 No.	  Instance	Sec. group	Domain name                             	Tag
   1	i-af23fa32	sg-223af233	ec2-107-20-76-111.compute-1.amazonaws.com	LIVE Web A
   2	i-232abc23	sg-223af233	ec2-107-22-12-222.compute-1.amazonaws.com	LIVE Web B
   3	i-892a98b3	sg-ccca2223	ec2-107-22-12-223.compute-1.amazonaws.com	DEV MySQL A
   4	i-123ab23c	sg-ccca2223	ec2-107-22-12-224.compute-1.amazonaws.com	DEV MySQL B
   5	i-98ca2532	sg-ccca2223	ec2-107-22-12-225.compute-1.amazonaws.com	DEV MySQL C
Enter server number, server range (e.g. 3..5) or list of servers (e.g. 2 3 4 8 9): 1
Ssh-ing to ec2-107-20-76-111.compute-1.amazonaws.com
```

If you include a parameter the list would be narrowed down to servers whose instance, security group, domain name or tag matches the parameter. This is extremely useful if you run lots of instances. Example parameters:

+ `ec2ssh live` - lists all servers whose tag contains 'LIVE'
+ `ec2ssh mysql` - lists all servers whose tag contains 'MySQL'
+ `ec2ssh sg-223af233` - lists all servers in the specified security group
+ `ec2ssh i-98ca2532` - lists a specific server matched by its instance id.

Note: Matches are case insensitive.

When prompted for the server(s) you can enter one or more numbers in the following format:

+ `3` - Ssh to third server in the menu
+ `1 4` - Ssh to first and forth server
+ `1..4` - Ssh to all servers in the range from 1 to 4, i.e. 1, 2, 3 and 4.

When you specify multiple servers, it connects you to the first one. When you exit, it ssh's you to the next, etc.

Dependancies
------------

ec2ssh is a bash script that requires [Amazon EC2 API tools](http://aws.amazon.com/developertools/351) and awk (comes with most Mac, Unix and Linux systems by default).

Practical uses
--------------

+ Manual deployments
+ Server (instance) maintenance
+ One-off tasks that take less time than writing deployment scripts
+ You ♥ ssh.

Copyright
---------

Copyright © 2012 [Viafoura.com](http://viafoura.com/). See LICENSE.txt for further details.