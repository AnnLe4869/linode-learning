# Important points to remember

1. Space and escape character in shell script is very sensitive. For example `export name=john` will work and `export name = john` will throw error.  
   ---> Strictly follow the syntax and if error happens when syntax "seem" to be correct, check for space
   
2. You should follow basic set up for Linux, which is [instructed by DigitalOcean](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04)

2. In case somethings go wrong and you cannot connect to the Linux machine, try

   - Exit the current session and connect again
   - Try other method to connect
   - Try `ping` the Linux machine to see whether it's responsive or not. Note that `ping` only test whether we can establish a network connection with that Linux machine or not. Still work even when that Linux machine is not a web server. If we can receive reply then the Linux machine is up and running. If not, problem likely on Linux machine side. Try reboot it. 
   - Reboot the Linux machine. Wait a bit for the machine finish setting up before attempting to connect again.
   - If `ping` success but other access methods fail (like `ssh` or `sftp`) then problem probably on the firewall. Remember `ufw` is different from DigitalOcean firewall dashboard and using both at the same time may cause conflict. DigitalOcean dashboard won't show the `ufw` setup. `ufw` default is to disable all port except the port that explicitly said to be open and port 22 for `ssh` is not an exception to not get disable. 

3. Nginx config usually requires root access to perform any action or config

4. Any commands typed on an SSH session will be tied to that session, and if that session is closed (i.e close window) those commands will be terminated.  
   ---> This explains why Gunicorn that run on local SSH session stops when we close that session and we cannot access the web server any move.

   Note that some actions like `nginx` running or `crontab` running is not tied to local SSH session.
