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
11. Installed Python packages:

    certifi (2018.1.18)
    
    chardet (3.0.4)
    
    click (6.7)
    
    Flask (0.12.2)
    
    httplib2 (0.10.3)
    
    idna (2.6)
    
    itsdangerous (0.24)
    
    Jinja2 (2.10)
    
    MarkupSafe (1.0)
    
    oauth2client (4.1.2)
    
    pip (9.0.1)
    
    psycopg2 (2.6.1)
    
    pyasn1 (0.4.2)
    
    pyasn1-modules (0.2.1)
    
    requests (2.18.4)
    
    rsa (3.4.2)
    
    setuptools (20.7.0)
    
    six (1.11.0)
    
    SQLAlchemy (1.2.1)
    
    urllib3 (1.22)
    
    Werkzeug (0.14.1)
    
    wheel (0.29.0)


12. In AMI console, give a static IP to the instance, and point the domain name to the IP.

13. In google developer console, use the URL of the domain name as Javascript and redirect origin, since google oauth doesn't accept IP addresses. 

## Third-party resources

https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vp

https://sg.godaddy.com/help/changing-the-ssh-port-for-your-linux-server-7306

https://www.ssh.com/ssh/putty/windows/puttygen

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html

https://help.ubuntu.com/community/UbuntuTime

https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps

https://www.postgresql.org/docs/8.1/static/manage-ag-createdb.html


## Authors

This project is the course work done by Shangyan Zhang.

## License

This project is licensed under Udacity's License to Educational Content 
- see the link https://www.udacity.com/legal/terms-of-service for details.


