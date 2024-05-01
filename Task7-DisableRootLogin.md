## Disable Root Login

```
After doing some security audits of servers, xFusionCorp Industries security team has implemented some new security policies. One of them is to disable direct root login through SSH.
Disable direct SSH root login on all app servers in Stratos Datacenter.
```

### Objective of the above task: 

In order to secure your Linux server, it is a good practice to disable direct root login. By doing so, you prevent malicious users from gaining access to the root account, which has the highest level of access and privileges on the server.

Disabling direct root login means that you will no longer be able to log in to the server as the root user, instead, you will need to log in as a regular user and then use the "sudo" command to perform administrative tasks. This adds an extra layer of security to your server by requiring an additional step before granting root access.

The process of disabling direct root login involves making changes to the SSH configuration file on your server. You will need to create a new user account with administrative privileges, edit the SSH configuration file to disallow root login and restart the SSH service to apply the changes.

### Resolution

#### Step 1: Login on the App server 1 as per the task and switch root user

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1572).png)

![altText](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1573).png)


#### Step 2: Edit the /etc/ssh/sshd_config file and change the PermitRoot value from yes to no

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1574).png)

#### Replace the "#PermitRootLogin" yes with "PermitRootLogin" no

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1575).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1576).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1577).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1578).png)


#### Step 3: Now restart the service of ssh 

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1579).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1580).png)


```
Now by this root got logged out and unable to login again, same need to do with other servers (app2 and app3)
```

#### Step 4:  Login on the App server 2 as per the task and switch root user

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1581).png)


#### Step 5: Edit the /etc/ssh/sshd_config file and change the PermitRoot value from yes to no

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1582).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1583).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1584).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1585).png)


#### Step 6: Restart the service 

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1586).png)


#### Step 7: Login on the App server 3 as per the task and switch root user

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1587).png)


#### Step 8: Edit the /etc/ssh/sshd_config file and change the PermitRoot value from yes to no

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1588).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1589).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1590).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1591).png)


#### Step 9: Restart the service

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1592).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1593).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1594).png)

![alt Text](https://github.com/srabhayraj/KodeKloud-Engineer-Linux-Tasks/blob/main/metadata/task7/Screenshot%20(1595).png)





