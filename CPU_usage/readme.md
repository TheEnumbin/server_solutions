# Problem: CPU Usage peaked.

Solution: Check which process is eating the CPU and Kill Them ALL

### How to Check??

#### From User Interface cpanel

Step 1 -> From Cpanel go to "Resource Usage"

Step 2 -> Go to Snapshot Tab

Step 3 -> Find out which process is eating the CPU.

#### From SHELL

-> From Cpanel, enable shell access. (Search Manage Shell in cpanel and it's intuitive)

-> Open terminal and write the comman below

`ssh -i ~/.ssh/id_rsa -p PORT_NUMBER HOSTING_USER@DOMAIN_NAME.com`

Here,

PORT_NUMBER = port number you will find in the Manage Shell in your cpanel

HOSTING_USER =
