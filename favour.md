1. To add a new user called *favour*, I used `useradd favour`. To gain permission from the root I used `sudo`

<img src="./Alt_images/useradd.jpg" alt="useradd favour">

2. To set an expiry date of 2 weeks for the user `favour`, I used `sudo chage -E <expiry date> <user>`. 

<img src="./Alt_images/expiry date.jpg" alt="sudo chage -E <expiry date> <user>">

To confirm the expiry date I used `sudo chage -l favour`.

<img src="./Alt_images/check date.jpg" alt="check date">



3. To prompt the user to change password on login, I used `sudo passwd -e favour`

<img src="./Alt_images/chage passwd.jpg" alt="change passwd">

To confirm the expiry date I used `sudo chage -l favour`.

<img src="./Alt_images/confirm.jpg" alt="confirm">

4. To attach the user *favour* to a group called *altschool* I first created the group using `sudo groupadd altschool`

<img src="./Alt_images/groupadd.jpg" alt="grpadd">

To confirm the group  exists, I used `sudo getent group`. 

<img src="./Alt_images/checkgrpadd.jpg" alt="cgrpadd">

The group *altschool* has been created. Now, to add *favour* to *altschool*, I used `sudo usermod -aG altschool favour`

<img src="./Alt_images/useraddgrp.jpg" alt="useraddgrp">


Let's see if the group *altschool* now has a user called *favour*

<img src="./Alt_images/cheusergrpadd.jpg" alt="cusergrpadd">

5. To allow altschool group to be able to run only cat command on /etc/, I set up an access control using `sudoers` file and opened using `sudo visudo`

![alt text](./Alt_images/visudo.jpg)

and then added the command `%altschool ALL=(ALL) /bin/cat /etc/*` for the group to run cat command on /etc/

![alt text](./Alt_images/cat.jpg)

6. To create another user `fave`and make sure that this user doesn't have a home directory i used `useradd -M fave`
