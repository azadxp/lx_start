

**Update and Upgrade the System:**
Before doing anything else, it is important to update and upgrade the system to ensure that all security patches and software updates are installed.


**Create a New User:**
Create a new user with sudo privileges to ensure that the server is not accessed with the default root account.
```
adduser seymur
```
```
usermod -aG sudo seymur
```



**Setup SSH Key Authentication:**
Set up SSH key authentication for the new user to allow secure remote access to the server.
 07 ssh keys create.md

` # If the root Account Uses SSH Key Authentication `

If you logged in to your root account using SSH keys, then password authentication is disabled for SSH. You will need to add a copy of your local public key to the new user’s `~/.ssh/authorized_keys` file to log in successfully.

Since your public key is already in the root account’s `~/.ssh/authorized_keys` file on the server, we can copy that file and directory structure to our new user account in our existing session.

The simplest way to copy the files with the correct ownership and permissions is with the `rsync` command. This will copy the root user’s `.ssh `directory, preserve the permissions, and modify the file owners, all in a single command. Make sure to change the highlighted portions of the command below to match your regular user’s name:


```
Note: The rsync command treats sources and destinations that end with a trailing slash differently than those without a trailing slash. When using rsync below, be sure that the source directory (~/.ssh) does not include a trailing slash (check to make sure you are not using `~/.ssh/`).

If you accidentally add a trailing slash to the command, rsync will copy the contents of the root account’s `~/.ssh` directory to the sudo user’s home directory instead of copying the entire `~/.ssh` directory structure. The files will be in the wrong location and SSH will not be able to find and use them.
```





**Configure the Firewall:**
Configure the firewall to restrict incoming and outgoing traffic to only necessary services.

```
ufw app list
```

```
Output
Available applications:
  OpenSSH
  ```

```
ufw allow OpenSSH
```

```
ufw enable
```

```
ufw status
```

UFW Essentials: Common Firewall Rules and Commands
 https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands

**Disable Root Login:**
Disable root login through SSH to ensure that the server is not accessed with the default root account.

**Install Fail2ban:**
Install Fail2ban to monitor the server's logs and block IP addresses that exhibit suspicious behavior.


**Install a Monitoring System:**
Install a monitoring system to keep an eye on the server's performance, uptime, and any potential security issues.

