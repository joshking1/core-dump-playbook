# core-dump-playbook notes 

This playbook is performing a series of tasks to configure core dump on an Ubuntu server. Here's a breakdown of each task:

Create Core Dump Directory: This task creates a directory at /var/coredumps with the permissions 0755. This directory will be used to store core dump files.

Enable Core Dump: This task adds a line to the /etc/security/limits.conf file, specifying that all users can generate core dumps without any size limit. 

This allows core dumps to be created when an application crashes.

Adjust Core Dump Pattern: This task adds a line to the /etc/sysctl.conf file, specifying the pattern for naming core dump files. 

The pattern includes information such as the executable name, process ID, and timestamp.

Set Core Dump Permission: This task adds a line to the /etc/sysctl.conf file, setting the value of fs.suid_dumpable to 2. 

This value allows core dumps for setuid programs, which are executables that run with the privileges of the file owner.

Load New Sysctl Settings: This task runs the sysctl --system command to load the new settings specified in the /etc/sysctl.conf file. 

This ensures that the changes made to the sysctl configuration take effect.

Overall, this playbook creates a directory for storing core dump files, adjusts system limits and configurations to allow core dumps, and reloads the sysctl settings to apply the changes.
