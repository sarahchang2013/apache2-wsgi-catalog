# apache2-wsgi-catalog
Udacity project to host the catalog app on amazon lightsail with apache2 and wsgi.

## Access

IP address: 13.250.151.187;
SSH port: 2200;
URL: http://www.cspectra.com

## Configurations

1. Disable remote root login.

2. Change the SSH port from 22 to 2200, in the "Networking" tab of AMI console, change port number accordingly.

   ( When changing the SSH port, make sure that the firewall is open for port 2200 first, so that you don't lock yourself out of the server.)

3. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).

4.  Configure the local timezone to UTC.

5.  Install and configure Apache to serve a Python mod_wsgi application.

6.  Install and configure PostgreSQL. Create an empty database named catalog, and its user named catalog. 

7.  Install git.

8.  Clone this catalog repository to /var/www/. 

9.  Change Apache .conf file:

    sudo vi  /etc/apache2/sites-enabled/000-default.conf

    Add this line before the closing tag: 

    WSGIScriptAlias / /var/www/catalog/catalog.wsgi

10. Run python __init__.py in the catalog folder, install any missing package.

    sudo -H pip install foo

11. In AWS console, give a static IP to the instance, and point the domain name to the IP.

12. In google developer console, use the URL of the domain name as Javascript and redirect origin, since google oauth doesn't accept IP addresses. 


## Authors

This project is the course work done by Shangyan Zhang.

## License

This project is licensed under Udacity's License to Educational Content 
- see the link https://www.udacity.com/legal/terms-of-service for details.


