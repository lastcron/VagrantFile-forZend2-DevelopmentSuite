# VagrantFile for Zend2 Framework Development
-------------------------------------------------------------------------------------------
This is a Vagrant file with the entire stack and tools for Zend2 Framwework Development so you can start developing locally right away.

Plese feel free to contribute or add recomendations to it. 
Initially proposed by @lastcron on May 5th 2015

You will find below the DESCRIPTION OF WHAT'S INCLUDED  , DETAIL OF CONFIGURATIONS & DEFAULT PASSWORDS and a RECOMMENDATIONS TO GET STARTED.

DESCRIPTION OF WHATS INCLUDED
--------------------------------------------------------------------

Ive included a little descrition explaining why every package has been included in the Vagrant File.

This vagrant was initially created with the online tool at https://puphpet.com/ and includes the following configurations and packets:

A)Ubuntu 14.0 LTS 64 Bits
I've decided to use this OS because you can easily start one for production in any Cloud Provider. My personal choice is Amazon Web Services and this machine is just 2 clicks away.

B)MySql (Version 5.6)
Needed for Data persistency. Choosen because of the great tools for interacting with it. MySql Workbench is my preferred choice for this , altough there are many in the market.

C)PHP (Version 5.6)
Of course , it is the base of ZEND 2 FrameWork

D)Zend 2 Framework
Complete set of libraries of Zend Framework

E)Apache Server ( I'll Update the exact version later)
In order to run the Framwework.

F)Git (http://git-scm.com/)
For code versioning purposes. If your development host is Windows i recommend to download Git for Windows which is another great Open Source implementation of Git for Windows. 

G)Composer (https://getcomposer.org/)
PHP Library to keep a centralized list of packages for your project. It allows to declare php packages name and version in a single file. With a single command all packages get installed/updated. Useful to keep all developers in the same page.

H)Doctrine 2.4.2 ( http://www.doctrine-project.org/ )
This is an Object Relational Mapping (ORM) of wide usage and preference in order to build an abstraction layer between your controllers and your database. In case you want to change from DB Engine in the future you only need to change the code in a single place.

I)Twitter Bootstrap 3.3.4 ( http://getbootstrap.com/) Included on May 5th 2015
This a CSS framework built and used by twitter , it allows fast deployment of nice views trough the use of predefined classes.

J)Jquery 1.10.2 ( https://jquery.com/)
This is a Javascript engine that allows to save lots of time with predefined classes. Our main interest with this tools is to enable the usage of Ajax calls in an easy to use format

K)PHPUnit (https://phpunit.de/)
PHP Library for building class tests fast and easy in your project.

L)Xdebug (http://xdebug.org/)
PHP package that enables interactive code debugging from netbeans.

L)WebMin (http://www.webmin.com/)
This is a nice GUI for Machine administration. Accesible trough : https://192.168.10.1:10000 . You will need to use any Ubuntu admin user & password. Below is the default one.

DEFAULT CONFIGURATIONS & PASSWORDS
--------------------------------------------------------------

VIRTUAL MACHINE
-----------------------------------------
1 CPU
1024 MB RAM
Folder Mapping:  Host folder Source: ./  with VM /var/www/z2

UBUNTU
------------------------------------------
User: root
Password: root

NETWORK
------------------------------------------
IP: 192.168.10.1
Hostname: local.z2
Defautl WebSite for Z2 Application: http://Z2Development.local  ( You will need to modify your host file locally to add this reference)

MYSQL
-------------------------------------------
Host Address: 192.168.10.1
Port: 3306
Root User: root
Root Password: mysql
Connect using SSH tunnel, username vagrant and SSH key generated at puphpet/files/dot/ssh/id_rsa. This key is generated after your initial $ vagrant up!

WebMin
------------------------------------------
Point your browser to: https://192.168.10.1 and use "root" and "root" as user and password respectively. This is because root is an admin site in ubuntu.

RECOMMENDATIONS TO GET STARTED
-----------------------------------------------------------

In order to get started with ZEND 2 Framework development you should at least install in your host machine the following programs:

A)Vagrant to be able to run this vagrant file. Get it here ( https://www.vagrantup.com/downloads.html)

B)NetBeans . This is the IDE for development and debugging. Just create a new Zend2 Project while pointing to the shared folder. Get it here ( https://netbeans.org/downloads/)

C)MySql Workbench. To interact with the MySql Database just point a new connection to the MySql configuration explained above. Get it here ( https://www.mysql.com/products/workbench/)

D)VirtualBox. For running vagrant virtual machine. Get it Here (https://www.virtualbox.org/wiki/Downloads)

Great! Now Lets get Started!!
--------------------------------

1.First , Using the console create a folder  wherever  you want your source files stored and get into it. eg: C:/cd Z2Test( Windows ) or $cd z2Test (Linux).

2.Extract the downloaded  zip file from this repository and put inside your folder

3.Open a terminal window and go into the folder and then into the \zf2skeleton\vagrant folder

4.Run $ vagrant up and go grab a coffee

5.Add this to your hosts file:
192.168.10.1 Z2Development.local

6.Browse to http://Z2Development.local in the browser, you should see the Zend Framework 2 skeleton application. 
If you go to http://Z2Development.local/bad you should see a ZF2 404 page, not the apache 404 page. 

Read the instructions!
------------------------------------
After you run $ vagrant up you'll get a list of instructions. Please read them if you have any questions or problems! They will answer most of the frequently asked questions

The config file
------------------------------------
Everything in your VM is controlled via the /zf2skeleton/vagrant/puphpet/config.yaml file. Here, you can choose which packages you want installed and change the settings for many things.

If you change anything, you can have it take effect within your virtual machine by running $ vagrant provision. If you make changes before you actually spin up your vm, the changes will be applied on your first $ vagrant up.

Custom config file
----------------------------------
You can create a custom config file at puphpet/config-custom.yaml to override anything that you have defined in puphpet/config.yaml. This file is ignored by Git by default. Simply copy the structure from config.yaml and replace the values you want. You can also create completely new keys to define functionality not present in PuPHPet by default!







