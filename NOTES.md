# Important points to remember

1. Space and escape character in shell script is very sensitive. For example `export name=john` will work and `export name = john` will throw error.  
   ---> Strictly follow the syntax and if error happens when syntax "seem" to be correct, check for space

2. In case somethings go wrong and you cannot connect to the Linux machine, try

   - Exit the current session and connect again
   - Try other method to connect
   - Try `ping` the Linux machine to see whether it's responsive or not. Note that `ping` only test whether we can establish a network connection with that Linux machine or not. Still work even when that Linux machine is not a web server
   - Reboot the Linux machine

3. Nginx config usually requires root access