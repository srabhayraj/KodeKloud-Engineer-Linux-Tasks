## Linux File Permissions

```
There are new requirements to automate a backup process that was performed manually by the xFusionCorp Industries system admins team earlier. To automate this task, the team has developed a new bash script xfusioncorp.sh. They have already copied the script on all required servers, however they did not make it executable on one the app server i.e App Server 3 in Stratos Datacenter.

Please give executable permissions to /tmp/xfusioncorp.sh script on App Server 3. Also make sure every user can execute it.
```

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1678).png)

### Step 1: Login on  App server 3 as per mentioned in the task and switched to root user

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1679).png)


### Step 2: List the file along with the existing file permission

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1680).png)


### Step 3: As per the task all users need to have execute permission

```
Please note that in case of bash script, bash is the interpreter that is actually going to execute the script and the interpreter needs to read the script. So even if you have given it only executable permission, the interpreter i.e bash will not be able to execute it. So you had to give it read permission as well along with execute permission.
```

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1681).png)

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1682).png)


### Step 4: Verify the file permissions and execute the script from user

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1683).png)

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1684).png)

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1685).png)

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1686).png)

![Image](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task9/Screenshot%20(1687).png)







Everything about chmod command in Linux
What does it do?
chmod command is used to change permissions of a given file according to a certain mode which might be a set of octal characters or a set of alphabetical characters.
Permissions explained
Each file on your system has a certain set of permissions associated with it. There are three types of permissions that can be associated with a file:
Read permissions denoted by 'r'
Write permission denoted by 'w'
Execute permissions denoted by 'x'
You can check the permissions of a given file by using the following command:
ls -l <filename>
The output of this command will look something like this:
The string rwxr-xr-x represents the permissions of this file. It can further be divided in to three parts containing three characters each and we get the three components of file permissions in linux:
Owner permissions(rwx) - Permissions for the user who created the file. rwx means that this user can read, write and execute this file.
Group permissions(r-x) - Permissions for other users in the file's group. r-x means that the user can read and execute the file but cannot write to it.
Other user permissions(r-x) - Permissions for users who do not belong to the above categories. In this case these are the same as the group permissions.
Permission modes
There are two types of modes that can be given as input to the chmod command:
Set of octal characters
Consider the owner permissions in the above example. They are represented by rwx. Now consider r=4, w=2, x=1. Therefore rwx = 4 + 2 + 1 = 7. Therefore the octal character 7 represents that the user has the permissions to read write and execute the file.
Let us take another example. The group permissions in the above case is r-x. As we already know r=4 and x=1. We denote the empty slot by 0. Octal representation for r-x = 4 + 0 + 1 = 5. Therefore the octal character 5 represents that the user has permissions to read and execute the file but it cannot write to the file.
Similarly the other users' permissions evaluate to 5 in our case. Therefore the complete permissions of this file can be represented by the octal number 755.
To change the permissions of a file using the octal number mode we run:
chmod <octal number> <filename>
Now we want to change the permissions for this file to say, rw--r-xr--.
Owner permissions(rw-) = 4 + 2 + 0 = 6
Group permissions(r-x) = 4 + 0 + 1 = 5
Other user's permissions(r--) = 4 + 0 + 0 = 4
Now, for changing the file permissions we run:
chmod 654 chmod.txt
Values of r,w and x.
In the above sections we assumed values r=4, w=2 and x=1. Now let us discuss how these are derived. The three character permission string(rwx, r-x or r--) is nothing but a three bit binary string. Now by convention the first bit specifies read permission, second bit specifies the write permission and the third bit specifies the execute permission. If that bit is one, the user has that permission. Now we denote read by 'r' and if read is allowed there is a 1 on the first bit, which evaluates to 4 if the other bits are 0. Similarly the values for 'w' and 'x' can be calculated.
Set of alphabetical characters
The below image(copied from man page of chmod command) specifies the allowed characters and their meanings
We would add three more characters to this list. First one is 'a' which represents a union of all the users that is owner, group users and others. The second character is '+' which is specified to add a permission to a user, and the third character is '-' which is specified to revoke a permission from the user.
Now for changing file permission we run:
chmod <user type(u/g/o/a)><add/revoke(+/-)><permission type(r/w/x)>
To change the owner permissions of a file to read and write, we run:
chmod u+rw chmod.txt
To give a write permission to everyone, we run:
chmod a+w chmod.txt
To remove the write permission for others, we run:
chmod o-w chmod.txt
To change the permissions of a directory, we run:
chmod <permission> <directory name>
To change the permissions of a directory with its files and sub-directories recursively, we run:
chmod -R <permission> <directory name>
