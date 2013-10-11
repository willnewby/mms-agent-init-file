mms-agent-init-file
===================

An init.d file for MongoDB's MMS Agent on CentOS (probably works for Fedora and RHEL too, but I haven't tested it). I couldn't find an init script for MMS and I didn't want to run the agent in a screen, so I decided to write this. Fixes and updates welcome.

Installation
===
Drop this file in /etc/init.d and make sure it's 0755 (executable). Also, this script assumes that your mms-agent files are in /opt/mms-agent.

Usage
====

<pre>
<code>
[root@mongo-node-01 willnewby]# service mms-agent start
Starting MMS Daemon: OK
[root@mongo-node-01 willnewby]# 
</code>
</pre>

<pre>
<code>
[root@mongo-node-01 willnewby]# service mms-agent stop
Stopping MMS Daemon: OK
[root@mongo-node-01 willnewby]# 
</code>
</pre>

<pre>
<code>
[root@mongo-node-01 willnewby]# service mms-agent restart
Stopping MMS Daemon: OK
Starting MMS Daemon: OK
[root@mongo-node-01 willnewby]# 
</code>
</pre>

<pre>
<code>
[root@mongo-node-01 willnewby]# service mms-agent status
MMS Agent running
[root@mongo-node-01 willnewby]# 
</code>
</pre>


Assumptions
====
There are a number of assumptions that the script makes, that you can change if you so desire
 - Your mms-agent files live in /opt/mms-agent
 - Your mongodb log directory is /var/log/mongo (which is the RPM default)
 - /var/lock/subsys exists as a directory. (If this is missing, you likely have other problems)