![alt text](https://res.cloudinary.com/cdowebcast/image/upload/v1571648180/SHOUTcast%20Manager/logo_dp3hma.png "Scottish Borders Design Logo")

# Documentation #
I have moved the documentation to here: [SHOUTcast Manager Documentation Wiki](https://github.com/gaza1994/SHOUTcast-Manager/wiki)

# Screenshots #

### Main Dashboard ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/dashboard.jpg "SHOUTcast Manager Screenshot")

### Login ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/login.jpg "SHOUTcast Manager Screenshot")

### Login with 2 Factor Auth (Google Authenticator) ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/login_2fa.jpg "SHOUTcast Manager Screenshot")

### Home Screen ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/main_screen.jpg "SHOUTcast Manager Screenshot")

### AutoDJ Media Manager ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/media_manager.jpg "SHOUTcast Manager Screenshot")

### Javascript Widgets ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/widgets.jpg "SHOUTcast Manager Screenshot")

### Developers API to control SHOUTcast from Anywhere and Anything ###
The Documentation is built into the script
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/api.jpg "SHOUTcast Manager Screenshot")

### Admin Maintainence Screen ###
![alt text](https://scottishbordersdesign.co.uk/github/SHOUTcast-Manager/screenshots/maintaince_screen.jpg "SHOUTcast Manager Screenshot")

There are many other features including 
 - cPanel FTP creation
 - Login as a user
 - SHOUTcast binary settings editor
 - Full user profiles
 - WHMCS plugin to create and control the radios from WHMCS
 - SMARTY templating engine
 - Smart API key system
 - Multi Radio support for a single account
 - API and User actions log
 - Create and Edit Radios from the interface (WHMCS not required)
 - Multi Media Upload (cPanel _not_ required)


# What is this? #
SHOUTcast manager was created 4 years ago to serve the purpose of hosting internet radios to as many as possible - Recently with all the issues of the legacy SHOUTcast binary not working it was updated to work with the latest SHOUTcast v2.x on all oses thats supported (Windows & Linux etc...) 

The software never sold very well, its been sitting "collecting dust" as some might say, so i've decided to just release it for free for many to try! 

I can offer limited support via my website (you'll need to register an account to get a copy of it) OR add an issue on GitHub and i'll look at it asap!

The copy you are seeing on here (GitHub.com) is for other developers to see the inner workings of such a script - You may required a license key to use this software which can be obtained here (its FREE dont worry - Just click the "Add to Cart" button): https://client.scottishbordersdesign.co.uk/scripts/15/Monthly+SHOUTcast+Manager.html


# Why SHOUTCast Manager? #
Currently (correct me if im wrong) this is the only fully featured FREE PHP SHOUTcast management tool avilable that has support for PHP 5.x, 7 & 7.1 and that has been configured to work with SHOUTcast v2 (with SHOUTcast v1.x legacy support!)

# Developers #
Feel free to fork, tweak and submit pull requests :)


# README #

Download and put the files on your server of choice.

### Server Checks ###

* You are running Linux or Windows (Linux is recomended)
* Glibc is installed (linux)
* sc_serv and sc_trans from the shoutcast directory is CHMOD to 755

### Script Install ###

_Have your license key handy from us_

* navigate to yourURL.com/install and follow the steps.

For full insutrctions on how to install and setup please read the following: http://client.scottishbordersdesign.co.uk/knowledgebase/9/SHOUTcast-Client

### SERVER REQUIREMENTS ###

- IonCube
- cPanel / WHM*
- MySQL server, version 4.1 or later
- A web server with PHP version 5.4+
- PHP MySQLi extension
- PHP cURL extension
- GlibC
- *Optional for FTP

### HOW TO INSTALL ###

1. Download and Extract the ZIP file downloaded from the client area onto your desktop

2. Upload the files to a web accessible directory on your web server

3. Create a MySQL database and a user in cPanel

4. Go to the URL you uploaded the files to (EG: http://shoutcast.yourdomain.tld/)

Follow the directions through the step-by-step installation pages. Some of the work will be done for you.

Main steps:

- Checking that all requirements are met
- Set directories playlists/, autodj/mp3s/, logs/ and servers/ as well as the config.php file writable
- Set each server as 777 CHMOD
- Create database and check that MySQL is running and connection works with given credentials
- Create tables from create.sql, save db settings to config.php and general settings to config table,
as well as set admin's name and password.
- Remove or rename the install folder in the install directory to be able to log in

NOTE! If you are running this on Windows, you need to edit the registry keys listed in the pstools.reg
file in the wintools/ directory before starting to use this. This is for the process tools to work in the background.

5. To ensure the servers are running in a good condition and to enable the bitrate checking, you will need to add the following CRON job.

*/5 * * * * php /path/to/shoutcast/cron/cron.php


### SETTING UP WHMCS API ###

Open your favourite FTP program and navigate to WHMCS Directory/modules/servers/

Extract the WHMCS API zip file to your desktop and navigate to modules/servers and upload the sbdShoutcast folder into the above FTP location

In WHMCS navigate to http://whmcs/admin

Click on Setup, Products/Services, Servers

Click Add New server and input the following details

* Name: You Choose
* Hostname: input url without http:// (Example shoutcast.yourdomain.tld)
* IP Address: URL to shoutcast installation/api (Example: http://shoutcast/yourdomain.tld/api/) The trailing '/' is important
* Assigned IPs: put your server ip in here
* Server Stat: URL to shoutcast installation/stats/


* Type: SbdShoutcast
* Username: (your super user username)
* Password: (your super user password)


Setup is now complete, You can now add a product service of type SbdShoutcast.
Each shoutcast product needs the following custom fields:

![alt text](https://res.cloudinary.com/cdowebcast/image/upload/v1571648180/SHOUTcast%20Manager/foreach.png "WHMCS Module Config")

If you want your users to be able to select how much space they need for the AutoDJ remove the setting in the product and do the following (these exact settings must be used, including the name!, prices can be changed.)

![alt text](https://res.cloudinary.com/cdowebcast/image/upload/v1571648180/SHOUTcast%20Manager/autodj.png "AutoDJ Dashboard Config")

Thenin your product go to Configurable Options and select the one you have just created.
