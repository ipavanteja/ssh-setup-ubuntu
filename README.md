# SSH setup in Ubuntu Linux Server

### OpenSSH Server

#### Introduction

OpenSSH is a powerful collection of tools for the remote control of, and transfer of data between, networked computers. You will also learn about some of the configuration settings possible with the OpenSSH server application and how to change them on your Ubuntu system.

OpenSSH is a freely available version of the Secure Shell (SSH) protocol family of tools for remotely controlling, or transferring files between, computers. Traditional tools used to accomplish these functions, such as telnet or rcp, are insecure and transmit the user’s password in cleartext when used. OpenSSH provides a server daemon and client tools to facilitate secure, encrypted remote control and file transfer operations, effectively replacing the legacy tools.

The OpenSSH server component, sshd, listens continuously for client connections from any of the client tools. When a connection request occurs, sshd sets up the correct connection depending on the type of client tool connecting. For example, if the remote computer is connecting with the ssh client application, the OpenSSH server sets up a remote control session after authentication. If a remote user connects to an OpenSSH server with scp, the OpenSSH server daemon initiates a secure copy of files between the server and client after authentication. OpenSSH can use many authentication methods, including plain password, public key, and Kerberos tickets.

### Installation

Installation of the OpenSSH client and server applications is simple. To install the OpenSSH client applications on your Ubuntu system, use this command at a terminal prompt:

`sudo apt install openssh-client`

To install the OpenSSH server application and related support files, use this command at a terminal prompt:

`sudo apt install openssh-server`

In this case, we already installed openssh-server and client packages during the Ubuntu Linux Server installation.

![image.png](https://atlas.i.camp/uploads/images/gallery/2023-07/scaled-1680-/on6EL58At16LDWkd-image.png)

#### Generate SSH Keys for our Ubuntu Linux Server:

SSH allows authentication between two hosts without the need for a password. SSH key authentication uses a *private key* and a *public key*. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key

**Step 1:** Open Terminal and generate SSH keys using `ssh-keygen` command as shown below.

![image.png](https://atlas.i.camp/uploads/images/gallery/2023-07/scaled-1680-/anlFE2tbyYIF46qi-image.png)

**Step 2:** Enter the file in which to save the key in the default location(/home/linux/.ssh/id\_rsa):(optional). By default, the user can generate the keys using different algorithms like RSA, DSA, and ECDSA. We are going to generate SSH keys using the default RSA algorithm.At the prompt, type a secure passphrase. For more information

As shown below, our SSH key is generated.By default the public key is saved in the file `~/.ssh/id_rsa.pub`, while `~/.ssh/id_rsa` is the private key.

![image.png](https://atlas.i.camp/uploads/images/gallery/2023-07/scaled-1680-/bJVeGc5U4zAXlkiV-image.png)

**Step 3:** To view our SSH key files (public and private keys), change the directory to the location where SSH keys are stored. Using the command `cd ~/.ssh/` and use `ls` command to list files.

![image.png](https://atlas.i.camp/uploads/images/gallery/2023-07/scaled-1680-/TYkrWwn72R0JQmnv-image.png)

**Step 4:** To view the keys present in both public and private key files use the command `cat id_rsa.pub` from your current working directory

Public key

![image.png](https://atlas.i.camp/uploads/images/gallery/2023-07/scaled-1680-/iQGQTqGX8bJm8Umu-image.png)
