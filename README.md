# **home-server-docker**

## **Index**

Content of the repository

1. *[Dashy](./dashy_container)*
2. *[FileBrowser](./filebrowser_container)*
3. *[Heimdall](./heimdall_container)*
4. *[Homer](./homer_container)*
5. *[Mealie](./mealie_container)*
6. *[Pi-Hole](./pihole_container)*
7. *[Plex](./plex_container)*
8. *[Portainer](./portainer_container)*
9. *[Samba](./samba_container)*
10. *[Vsftpd](./vsftpd_container)*
11. *[Server1](./server1)*
12. *[Server1 ARM](./server1_arm)*
13. *[Server2](./server2)*

<hr>

## **Summary of the docker-compose files**

### **Dashy**

*[Dashy](./dashy_container)* is an open source, highly customizable, easy to use, privacy-respecting dashboard app.

### **FileBrowser**

*[FileBrowser](./filebrowser_container)* it is a page for uploading and downloading files stored on the server..

### **Heimdall**

*[Heimdall](./heimdall_container)* is a container that allows for easy management of links to the most commonly used websites and web applications.

### **Homer**

*[Homer](./homer_container)* is a dead simple static homepage for your server to keep your services on hand, from a simple yaml configuration file.

### **Mealie**

*[Mealie](./mealie_container)* is a container that allows for having a recipe book.

### **Pi-Hole**

*[Pi-Hole](./pihole_container)* is a network-level ad and tracker blocker application that acts as a DNS sinkhole, designed for use on a private network.

### **Plex**

*[Plex](./plex_container)* is a personal multimedia and streaming application.

### **Portainer**

*[Portainer](./portainer_container)* is an open-source container management tool that provides a user-friendly interface to manage Docker environments.

### **Samba**

*[Samba](./samba_container)* is a free and open-source implementation of the SMB/CIFS protocol that allows for file and printer sharing between different operating systems, particularly between Unix/Linux and Windows systems.

### **Vsftpd**

*[Vsftpd](./vsftpd_container)* it is a container that exposes an FTP service.

### **Server 1**

*[Server1](./server1)* is the docker-compose file that I use on my first server.

### **Server 1 ARM**

*[Server1 ARM](./server1_arm)* is the docker-compose file that I use on my ARM server.

### **Server 2**

*[Server2](./server2)* is the docker-compose file that I use on my second server.

<hr>

## **Execution instructions**

The following are the commands to mount the external drive:

```
# We use the terminal as root.
sudo su
# We search for the disk that we want to mount.
fdisk -l
# Command to obtain the UUID.
ls -l /dev/disk/by-uuid/
# The following command mounts the disk, and the directory can be changed to the one where we want to mount it.
echo UUID="{Disk name or UUID}" /mnt/external_storage exfat rw,user,exec,umask=000 0 0 | \
     sudo tee -a /etc/fstab
# You can either execute this command or restart the system.
mount -a
```

To execute the docker-compose, you should navigate to the location of the file and run the following command:

```
docker-compose up -d
```
