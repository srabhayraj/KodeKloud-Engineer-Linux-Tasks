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


## All about [Linux File Permission](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/data/LinuxFilePermissions.md)
