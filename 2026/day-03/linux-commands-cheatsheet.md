Today Day 03 of #90DaysOfDevOps 🚀

I also learned how to troubleshoot issues with services by step-by-step examining processes, service status, and logs.

Covered the Linux command.

Topic:
• File & Directory Management
• User & Permission Controls
• Process Management
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

I also learned how to troubleshoot services by checking processes, service status, and logs step by step.

Special thanks to Shubham Londhe Bhaiya TrainWithShubham for this amazing #90DaysOfDevOps journey 💻🚀
