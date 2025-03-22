# Problem: CPU Usage peaked.


Solution: Check which process is eating the CPU and Kill Them ALL


### How to Check and Fix??


#### From User Interface cpanel


Step 1 -> From Cpanel go to "Resource Usage"


Step 2 -> Go to Snapshot Tab


Step 3 -> Find out which process is eating the CPU.




#### From SHELL


Step 1 -> From Cpanel, enable shell access. (Search Manage Shell in cpanel and it's intuitive)


Step 2 -> Open terminal and write the comman below


``` ssh -i ~/.ssh/id_rsa -p PORT_NUMBER HOSTING_USER@DOMAIN_NAME.com ```


Here,


   PORT_NUMBER = port number you will find in the "Manage Shell" in your cpanel


   HOSTING_USER = username you will find in the "Manage Shell" in your cpanel


   DOMAIN_NAME = your main domain


   id_rsa = private ssh key to connect the shell. [How to Create SSH Keys](#)


Step 3 -> Get the  id_rsa private key passpharse and put it when asked


Step 4 -> Now you are in the server. Now you can check the processes that is eating your CPU with some commands. I have listed them below.


```top``` - Shows you CPU usage in real time


```htop``` - Same as top but better visual overview


```vmstat``` - Shows CPU performence over time.


And many other.


[For mariaDb processed that is database processes]


-> Log into your db server with the command below


```mysql -u USER_NAME -p``` - Here USER_NAME is the user name for the db


Put the password correspondant to the user.


-> ```SHOW PROCESSLIST``` - This will list all the processes that is running currently.


From these find the process and kill it with the command below.


#### Pro Tip


-> The command below will give you all the running processes with the KILL command.


```SELECT CONCAT('KILL ', id, ';') FROM information_schema.processlist WHERE command != 'Sleep';```


-> Copy and paste the result in the terminal and the proccess will be killed and your CPU will be free.


***NOTE : Remember to format the query result if is has any extra character or not.