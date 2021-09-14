## Setting up supervisor config
First, install supervisord using apt-get package.

Then go to this path /etc/supervisor/conf.d/ and create a file named celery.conf .

Write the following command to celery.conf  
```
[program:celery]
directory = /home/ubuntu/prod/api
command = /home/ubuntu/anaconda3/envs/api_env/bin/celery -A prodapi worker -l info --without-gossip --without-mingle --without-heartbeat -Ofair -P gevent
stdout_logfile=/var/log/supervisor/celery.log    
stderr_logfile=/var/log/supervisor/celery.log
user=ubuntu
```                                                                                                                                                  
Next, tell the Supervisor to know about the new config  
```
supervisorctl reread
```

Next, tell Supervisor to start the service
```
supervisorctl update
```

You can verify whether the process has been started using,
```
supervisorctl
```

## Optional: Enable supervisor web interface

  open the file located in
  ```
  nano /etc/supervisor/supervisord.conf
  ```

  Add the following line to the file
  ```
  [inet_http_server]
  port=*:9001
  username=admin
  password=admin
  ```

  Restart Supervisor
  ```
  systemctl restart supervisor
  ```
