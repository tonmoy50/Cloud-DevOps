The project directory that holds manage.py file:
```
sudo chmod 775 api
sudo chown :www-data api
```
Database SQLite Permission:
```
sudo chown ubuntu:www-data db.sqlite3                                                                                                                                                                      
sudo chmod g+w db.sqlite3              
```
To configure the project directory that holds media and static:
```
sudo chown www-data:www-data -R bengal-meat.ai/
cd bengal-meat.ai/
```
To static/media folders:
```
sudo chown ubuntu:www-data -R media  
sudo chmod g+w media    
sudo chown ubuntu:www-data -R static
sudo chmod g+w static
```
To see the error and access log:
```
sudo tail -f /var/log/apache2/error.log
sudo tail -f /var/log/apache2/access.log
```                                                                                                                                                                    
To restart Apache server:
```
sudo /etc/init.d/apache2 restart    
```
To configure the default configuration file:
```                                                                                                                                                                                                                                         
 Alias /static/ /var/www/bengal-meat.ai/static/
    <Directory /var/www/bengal-meat.ai/static>
      Require all granted
    </Directory>

    Alias /media/ /var/www/bengal-meat.ai/media/
    <Directory /var/www/bengal-meat.ai/media>
      Require all granted
    </Directory>

    <Directory /home/ubuntu/prod/api/prodapi>
      <Files wsgi.py>
        Require all granted
      </Files>
    </Directory>

    WSGIDaemonProcess prodapi python-home=/home/ubuntu/anaconda3/envs/api_env python-path=/home/ubuntu/prod/api
    WSGIProcessGroup prodapi
    WSGIScriptAlias / /home/ubuntu/prod/api/prodapi/wsgi.py
```
To setup, Apache follow this URL

To install environment dependent mod-wsgi do the following:
```
sudo apt-get install apache2-dev
pip install mod-wsgi
```
Get the environment variable from this command and set it to the apache config file:
```
mod_wsgi-express module-config
sudo nano /etc/apache2/apache2.conf
```
Check the apache config test:
```
sudo apache2ctl configtest
```
Make sure that the file has these permission set in /var/www directory:
```
drwxr-xr-x    =>  bengal-meat.ai
drwxrwxr-x  =>  media
drwxrwxr-x  =>  static
-rw-rw-r--    =>  file
```

## Reference:
- https://www.digitalocean.com/community/tutorials/how-to-serve-django-applications-with-apache-and-mod_wsgi-on-debian-8
