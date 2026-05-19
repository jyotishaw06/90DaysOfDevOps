
Today I covered the basics of Linux architecture and understood how Linux works behind the scenes.

I learned:
Users and administrators manage processes using various commands and system signals.


Task 	 		    Command(s)		      Description
Monitoring		ps, top, htop	    	View running processes, PIDs, and resource usage.
Termination		kill, killall		    Send signals like SIGTERM (graceful) or SIGKILL (forced) to end a process.
Priority		  nice, renice		    Adjust the "niceness" value (-20 to 19) to change CPU priority.
Job Control		bg, fg, &	        	Run processes in the background or bring them back to the interactive foreground.

Systemd is a system and service manager for modern Linux operating systems
•	Initialize the system during boot
•	Manage and control system services
•	Replace the traditional SysV init system
•	Improve boot speed and performance
•	Provide centralized system management tools


Explain process states (running, sleeping, zombie, etc.)
Process states describe the current lifecycle phase of a program actively managed by an operating system. They indicate whether a program is actively using the processor, waiting on input/output (I/O), paused, or finishing its execution

•	Running (R): The process is actively executing on the CPU or is in the ready queue, waiting for its assigned slice of processing time. 
•	Sleeping/Waiting (S or D): The process is suspended, waiting for an event like I/O completion or a timer. It can be interruptible (can be woken by signals) or uninterruptible (cannot be interrupted and usually waits on hardware). 
•	Stopped (T): The process is paused, typically due to receiving a signal (like pressing Ctrl+Z in a terminal) or being debugged. 
•	Zombie (Z): The process has finished executing, but its parent process has not yet read its exit status. 

command:
ls: Lists the files and directories in your current location.
cd: Changes the current working directory.
pwd: Prints the full path of the current working directory.
mkdir: Creates a new directory.
rmdir: Removes an empty directory.
rm: Deletes files or directories; use -r for recursive deletion of folders.
touch: Creates a new empty file or updates the timestamp of an existing one.
cp: Copies files or directories.
whoami: Displays the username of the current active user.
echo: Prints a line of text or a variable to the terminal.


================================================================================================================================================


Today Day 03 of #90DaysOfDevOps 🚀

I also learned how to troubleshoot issues with services by step-by-step examining processes, service status, and logs.


 covered the Linux command.

Topic:
• File & Directory Management
• User & Permission Controls
• Process Management
• Package Installation
• Networking Commands


Process Management:-
top / htop: Display real-time dynamic view of active processes and resource usage.
ps -ef / aux: View a snapshot of currently running processes.
systemctl status <service>: Check the operational status of system services.
kill <PID> / killall <name>: Send a termination signal (SIGTERM) to a process.
kill -9 <PID> / pkill -9 <name>: Force kill an unresponsive process (SIGKILL).
bg / fg: Resume a suspended process in the background or bring it to the foreground.
nice / renice: Start a process with a modified priority or change the priority of an existing one


File System:-
ls -la: List all files/directories in long format, including hidden files (e.g., .bashrc).
df -h: Check available disk space for mounted filesystems.
du -sh <directory>: Display total size of a specific folder or file in human-readable format.
find <path> -name <file>: Search for specific files on the disk.
grep -rn <string> <path>: Recursively search for specific text patterns inside files.
chmod <permissions> <file>: Modify file permissions (e.g., chmod 755 script.sh).
chown <owner>:<group> <file>: Change file ownership


Networking:-
ip addr show / ip route: Display the IP addresses of network interfaces and view routing tables.
ping <host/IP>: Test reachability and latency to a remote server.
traceroute <host> / mtr <host>: Trace the exact network path packets take to reach a destination.
ss -tulnp / netstat -tulnp: Display listening TCP and UDP sockets and the processes attached to them.
curl -I <URL>: Inspect HTTP response headers from a server or web endpoint.
telnet <host> <port> / nc -zv <host> <port>: Test if a specific TCP port is open and accessible on a server.
nslookup <domain> / dig <domain>: Query DNS records and troubleshoot domain resolution issues. 

I also learned how to troubleshoot services by checking processes, service status, and logs step by step.

Special thanks to Shubham Londhe Bhaiya TrainWithShubham for this amazing #90DaysOfDevOps journey 💻🚀


GitHub Repository:


#AWS
#EC2
#Linux
#CloudComputing
#DevOps
#90DaysOfDevOps
#TrainWithShubham
#DevOpsKaJosh
#LearningInPublic
#Udaan
