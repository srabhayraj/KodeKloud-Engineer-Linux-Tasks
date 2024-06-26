## Linux User Files

```
There was some users data copied on Nautilus App Server 1 at /home/usersdata location by the Nautilus production support team in Stratos DC. Later they found that they mistakenly mixed up different user data there. Now they want to filter out some user data and copy it to another location. Find the details below:

On App Server 1 find all files (not directories) owned by user yousuf inside /home/usersdata directory and copy them all while keeping the folder structure (preserve the directories path) to /ecommerce directory.
```

#### Step 1: Logged in into App server 1 and switched to root account 

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1561).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1562).png)


#### Step 2: List the files and folders in the given path using ls -l path

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1564).png)


#### Step 3: Check or list the ecommerce directory (destination directory) where the files need to be copied

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1565).png)


#### Step 4: Find the number of files (not directory) owned by user in the mentioned path
```
The find command helps us search for files as well as directories. Typically, this search depends on different criteria like file type, file name, and more.
-type f – instructs the find command to only look for files
```

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1566).png)


#### Step 5: As per the task find the files name by user & copy with folder structure
```
-exec cp - Tells you to execute the 'cp' command to copy files from source to destination directory.
The –parents option ensures the files are copied with their original directory structure. Meanwhile, the placeholder {} holds each file found, while /ecommerce is the path to copy the files to
```

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1567).png)


#### Step 6: List the files copied in the destination folder /ecommerce/home/usersdata

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1568).png)


#### Step 7: Click on Check and confirm 

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1569).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task6/Screenshot%20(1571).png)
