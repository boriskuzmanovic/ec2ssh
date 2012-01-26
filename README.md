ec2ssh
======

By Boris Kuzmanovic, Viafoura.

ec2ssh is a shell script that makes connecting to ec2 servers __ridiculously easy__.

ec2ssh displays your instances in a simple digest-like menu and prompts you to enter the server number. Once you enter it, the script opens an ssh connection to the server.

``` shell
$ ec2ssh
 No.	  Instance	Sec. group	Domain name                             	Name
   1	i-af23fa32	sg-223af233	ec2-107-20-76-111.compute-1.amazonaws.com	LIVE Web A
   2	i-232abc23	sg-223af233	ec2-107-22-12-222.compute-1.amazonaws.com	LIVE Web B
   3	i-892a98b3	sg-ccca2223	ec2-107-22-12-223.compute-1.amazonaws.com	DEV MySQL A
   4	i-123ab23c	sg-ccca2223	ec2-107-22-12-224.compute-1.amazonaws.com	DEV MySQL B
   5	i-98ca2532	sg-ccca2223	ec2-107-22-12-225.compute-1.amazonaws.com	DEV MySQL C
Enter server number, server range (e.g. 3..5) or list of servers (e.g. 2 3 4 8 9): 1
Ssh-ing to ec2-107-20-76-111.compute-1.amazonaws.com
```

You can ssh to a single server or a range of servers. Examples of user input:

+ `3` - Ssh to third server in the menu
+ `1 4` - Ssh to first and forth server
+ `1..4` - Ssh to all servers in the range from 1 to 4, i.e. 1, 2, 3 and 4.

Copyright
---------

Copyright © 2012 Boris Kuzmanovic. See LICENSE.txt for further details.