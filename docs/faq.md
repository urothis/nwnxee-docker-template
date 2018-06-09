# Frequently asked questions
On this document we will try to address most of the common questions/issues that most people run into when they are using the NWNXEE Template base project. To this end, we have split the questions in three categories:
* Linux
* Windows
* Other

The first two cover each individual operating system issues, so you will find issues specific to those platforms only. On the "Other" section you will find things that can happen on both platforms, or some miscellaneous issues that might arise.

## Linux
(This section is yet to be filled. We will once we have more feedback from users :P)

## Windows
### Should I enable "Experimental Features" on Docker for Windows?
As a rule of thumb, we highly recommend **enabling** this on Docker, since some features of NWNXEE require this set to enabled. If you are unsure if your setup has this enabled, on *Docker for Windows* system tray icon, right click and select *Settings*. Once inside, find *Daemon* and you will see a check box called with "Experimental Features". Make sure this is selected.

### Issues when pulling images from Docker Hub
This issue happens whenever you do ```docker-compose up```, or similar command. If you get the following error message (Or something that really looks like this) then you are having this issue!

```
F:\nwnxee-template-master>docker-compose up Pulling db (mysql/mysql-server:5.7)... 
ERROR: Get https://registry-1.docker.io/v2/mysql/mysql-server/manifests/5.7: unauthorized: incorrect username or password
```

In order to solve this you have to run ```docker logout``` and make sure that you've logged out from your Docker Hub account. In general, you will **NEVER** need to login using nwnxee-template to pull Docker images. But if you still need it, you need to login with your username / password, insted of e-mail /password.

**Source** <br />
[Docker Forums Thread](https://forums.docker.com/t/unauthorized-incorrect-username-or-password/35677)

## Other
(This section is yet to be filled. We will once we have more feedback from users :P)