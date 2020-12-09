# Resources

Something processes can get locked. Try:
```
sudo /etc/init.d/apache stop
sudo pgrep apache
```
If the above command returns anything, do:
```
sudo pkill -9 apache
```
Then start apache again:
```
sudo /etc/init.d/apache2 start
```
