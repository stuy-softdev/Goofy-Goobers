# how-to :: HOW TO DEPLOY A FLASK APP ON A DROPLET
---
## Overview
Deploying a flask app on our droplet allows us to run various applications using the resources of the virtual machine

### Estimated Time Cost: 30 minutes

### Prerequisites:

- Have a droplet set up
- Make sure you can SSH into an account with sudo access
- Make sure that your droplet has all available updates

### Instructions

1. SSH into an account with sudo access on your droplet
2. Install mod_wsgi and necessary requirements by running `$ sudo apt-get install libapache2-mod-wsgi-py3 python-dev`
3. Make sure mod_wsgi is enabled by running `$ sudo a2enmod wsgi`
4. Move into the directory that will store your app by running `$ cd /var/www`
5. Create the initial directory that will store your app by running `$ sudo mkdir <AppName>`
6. Make the contents of that directory editable by running `$ sudo chown -R $USER:$USER <AppName>/` and `$ sudo chmod -R 777 <AppName>/`
7. Exit the droplet by pressing `Ch-D`
8. Navigate to the folder containing folder `<AppName>/` which contains your application
9. Secure copy it into the correct location in your droplet by running `$ scp -r <AppName>/ user@droplet.ip:/var/www/<AppName>`
10. SSH back into the account with sudo access
11. Enter the folder containing your application by running `$ cd /var/www/<AppName>/<AppName>`
12. Use a file editor to make sure that the contents of your folder have the following structure:
    __init__.py
    static/
      css/
      js/
13. Install pip by running `$ sudo apt-get install python3-pip`
14. Install Flask by running `$ sudo pip install Flask`
15. Run your python file by running `$ python3 __init__.py`

### Resources
* [How to set up SSH shortcuts (to make it easier to SSH into that user with sudo perms)](https://piazza.com/class/kv0wqn7faux3ye?cid=169)
* [Commands to make sure droplets have available updates](https://piazza.com/class/kv0wqn7faux3ye?cid=167)

---

Accurate as of (last update): 2021-01-19

#### Contributors:  
Julia Nelson, pd1  