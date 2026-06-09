The Linux command 

=>cat /etc/hostname reads and displays the system's per
=>du -sh /var/log/* 2>/dev/null | sort -h | tail -5   powerful tool used to analyze and display the disk space usage of files and directories log file sorting 
=>ls -la ~    lists the contents of your current working directory. Not only that, by default Linux hides all files that start with a dot (.)

->#sudo apt install nginx
->#sudo ufw allow 'Nginx HTTP' -- Allow default HTTP (Port 80) traffic
-># systemctl status nginx --Check if the Nginx service started successfully
--------------------------------------------------------------------------------------------------------
Stop Nginx:							systemctl stop nginx
nginx Start Nginx: 						systemctl start nginx
Restart Nginx: 						systemctl restart nginx
Reload Configuration (No Downtime): 			systemctl reload nginx
Enable Start on Boot: 					systemctl enable nginx
 If service is not found, list all services			systemctl list-units -- type=service
Check if service is enabled on boot			systemctl is-enabled nginx

Key File Locations
•	/var/www/html: The default directory where your web content/HTML files are stored.
•	/etc/nginx: The primary configuration directory containing all server settings.
•	/etc/nginx/nginx.conf: The main configuration file.
•	/etc/nginx/sites-available/: Directory where individual website server blocks (virtual hosts) are configured.
•	/var/log/nginx/: Directory containing system error (error.log) and traffic (access.log) logs
A web application service called 'myapp' failed to start after a server reboot.
What commands would you run to diagnose the issue?
Write at least 4 commands in order.

1.	#systemctl status nginx  First check: Is the service running or failed?
2.	#journalctl -u nginx -n 50 -e   This displays the last 50 lines (-n) and jumps to the end (-e) of the specific service's logs, making it easier to pinpoint exact error messages.
3.	#systemctl is-enabled nginx   This will return either enabled or disabled.

Your manager reports that the application server is slow.
You SSH into the server. What commands would you run to identify
which process is using high CPU?

#ps aux --sort=-%cpu | head -10

A developer asks: "Where are the logs for the 'docker' service?"
The service is managed by systemd.
What commands would you use?

 # Check service status first
systemctl status ssh

# View last 50 lines of logs
journalctl -u ssh -n 50

# Follow logs in real-time
journalctl -u ssh -f

A script at /home/user/backup.sh is not executing.
When you run it: ./backup.sh
You get: "Permission denied"

What commands would you use to fix this?

Step 1: Check current permissions
Command: ls -l /home/user/backup.sh
Look for: -rw-r--r-- (notice no 'x' = not executable)

Step 2: Add execute permission
Command: chmod +x /home/user/backup.sh

Step 3: Verify it worked
Command: ls -l /home/user/backup.sh
Look for: -rwxr-xr-x (notice 'x' = executable)

Step 4: Try running it
Command: ./backup.sh



