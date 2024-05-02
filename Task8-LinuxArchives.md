## Linux Archives

```
On Nautilus storage server in Stratos DC, there is a storage location named /data, which is used by different developers to keep their data (non confidential data). One of the developers named mariyam has raised a ticket and asked for a copy of their data present in /data/mariyam directory on storage server. /home is a FTP location on storage server itself where developers can download their data. Below are the instructions shared by the system admin team to accomplish this task.

a. Make a mariyam.tar.gz compressed archive of /data/mariyam directory and move the archive to /home directory on Storage Server.
```

### Infrastructure Details

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1597).png)


### Resolution

#### Step 1: Firstly login onto storage server, and then switch to root user.

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1598).png)


#### Step 2: Archive the mentioned folder /data/mariyam using tar -czvf command

```
[The tar (short for Tape ARchiver) command is the most widely used archiving utility in Linux systems. Available directly in the terminal, the tar command helps create, extract, and list archive contents.
--create/-c	Operation	Creates a new archive.
--verbose/-v	Option	Shows the file tar works on while running.
--gzip/-z	Option	Read or write compressed archives through gzip format.
--file=<archive>/-f <archive>	Option	Specifies the file.]
```

```
tar -czvf <archive> <file(s) or location(s)
```

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1599).png)


#### Step 3: Move the tar file to /home directory.

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1600).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1601).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task8/Screenshot%20(1602).png)



