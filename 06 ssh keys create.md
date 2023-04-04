


**Create SSH key:**
    Open a terminal on your local machine.
    Type the following command and press Enter:

```
ssh-keygen -t rsa -b 4096 -C "your_email@tsii.exam"
```
You will be prompted to enter a file name to save the key pair. The default file name is id_rsa and the default save location is the user's home directory. Press Enter to accept the default file name and location, or specify a different name and location.
You will be prompted to enter a passphrase. You can leave it blank for no passphrase, or enter a passphrase to secure the key. Make sure to remember the passphrase, as it will be required to use the key.
The key pair is now generated and saved on your local machine.

**Copy the key to a server:**

    Log in to the remote server using your username and password.
    Create the .ssh directory in your home directory if it doesn't exist:

```
mkdir ~/.ssh
```
Copy the contents of the public key file (id_rsa.pub by default) to the authorized_keys file in the .ssh directory:

```
cat /path/to/public/key/id_rsa.pub >> ~/.ssh/authorized_keys
```
Change the permissions on the .ssh directory and the authorized_keys file to ensure they can only be read and written by the user:

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```


**Test the new key:**

Open a new terminal window on your local machine.

Type the following command to connect to the remote server:

```
ssh username@remote_server_ip_address
ssh azad@10.8.244.183
```


If you set a passphrase for the key, you will be prompted to enter it. If not, you will be logged in automatically.

**Troubleshooting:**

If you have trouble connecting to the remote server, make sure that you have copied the public key correctly and that the permissions are set correctly on the .ssh directory and authorized_keys file.

If you get an error message indicating that the remote server refused the connection, make sure that SSH access is enabled on the server and that the correct port is specified.

If you continue to have issues, try running the SSH connection in verbose mode by adding the -v flag to the SSH command to see more detailed error messages.











