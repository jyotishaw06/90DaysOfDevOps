Day 02 – Linux Architecture, Processes, and systemd

•	The core components of Linux (kernel, user space, init/systemd)

Linux is structured into two main memory areas: Kernel Space and User Space. These layers communicate via a System Call Interface (SCI), ensuring the core operating system remains stable even if a user application fail.

1.	The Linux kernel is the heart of the system, acting as a bridge between hardware and software.

•	Process Management: Schedules which tasks use the CPU and for how long.
•	Memory Management: Keeps track of how much memory is used, by what, and handles virtual memory to protect processes from each other.
•	Device Drivers: Acts as an interpreter between the kernel and physical hardware (like keyboards, disks, or GPUs).
•	System Calls: Provides the specific gateway (API) that user-space programs must use to request hardware services, such as reading a file or sending data over a network. 
2.	User space is the unprivileged memory area where all non-kernel applications and services run. This isolation prevents a crashing web browser from taking down the entire operating system
System Libraries: Includes tools like GNU C Library (glibc), which translate standard programming commands into kernel-ready system calls
User Applications: This includes everything from command-line shells (like Bash) to graphical environments (like GNOME) and everyday apps like browsers or office suites
Daemons: Background services that manage things like printing, network connections, or scheduled tasks

3.	 Init System (systemd)
The init process is the very first process started by the kernel during boot (assigned PID 1). Most modern Linux distributions use systemd as their default init system

System Initialization: Once the kernel is loaded, systemd takes over to mount filesystems and start essential user-space services in parallel to speed up boot times

Service Management: It monitors and manages the lifecycle of all other processes (services). If a critical service crashes, systemd can be configured to restart it automatically

Unit Files: systemd uses "units" (.service, .target, .mount) to define how different parts of the system should behave and which ones depend on others. 

System Journal: It includes journald, a centralized logging system that collects data from the kernel and all managed services

•	How processes are created and managed
In Linux, a process is a program in execution, managed by the kernel to ensure efficient multitasking and resource allocation

Process Creation
Processes in Linux are created through a unique "copy-and-replace" mechanism rather than starting from scratch

•	The fork() System Call: A running "parent" process creates an exact duplicate of itself called a "child" process. The child inherits the parent's environment, memory space, and open files but receives its own unique Process ID (PID). 

•	The exec() System Call: After forking, the child process typically uses an exec variant to replace its program code with a new executable (e.g., running ls or a web browser). 

•	The clone() System Call: Modern Linux kernels use clone() as the underlying implementation for both fork() and thread creation, allowing for more granular control over resource sharing.

•	Init Process: All processes eventually trace back to the init process (often systemd), which has PID 1 and is created by the kernel during boot. 


Process States
•	A process moves through several states during its lifecycle, which can be explored in detail on Medium: 
•	Ready/Runnable: Waiting in a queue to be assigned to a CPU by the scheduler.
•	Running: Actively executing instructions on the processor.
•	Sleeping (Waiting): Paused while waiting for an event, such as user input or a file to load.
•	Stopped: Manually suspended by a user or system signal.
•	Zombie: A process that has finished execution but still has an entry in the system's process table because its parent hasn't acknowledged its exit status yet

Management and Tools
Users and administrators manage processes using various commands and system signals.


Task 	 		    Command(s)		      Description
Monitoring		ps, top, htop	    	View running processes, PIDs, and resource usage.
Termination		kill, killall		    Send signals like SIGTERM (graceful) or SIGKILL (forced) to end a process.
Priority		  nice, renice		    Adjust the "niceness" value (-20 to 19) to change CPU priority.
Job Control		bg, fg, &	        	Run processes in the background or bring them back to the interactive foreground.

==========================================================
•	What systemd does and why it matters
Systemd is a system and service manager for modern Linux operating systems
•	Initialize the system during boot
•	Manage and control system services
•	Replace the traditional SysV init system
•	Improve boot speed and performance
•	Provide centralized system management tools

Managing Services with systemd
Systemd provides a unified framework to manage services, system resources, and configurations efficiently. Services are organized into units, and systemctl is the main utility to control them.

Primary Utilities:
•	systemctl: Controls services and units (start, stop, enable, disable, status). Central for service management.
•	journalctl: Accesses system logs maintained by systemd. Supports filtering by service, time, or priority.
•	hostnamectl: Configures system hostname dynamically.
•	localectl: Sets system locale and keyboard layout.
•	timedatectl: Manages system time, date, and timezone settings.
•	systemd-cgls: Displays the hierarchy of cgroups for running processes.
•	systemadm: Provides a graphical or simplified interface to manage services using systemctl commands.



===========================================================
•	Explain process states (running, sleeping, zombie, etc.)
Process states describe the current lifecycle phase of a program actively managed by an operating system. They indicate whether a program is actively using the processor, waiting on input/output (I/O), paused, or finishing its execution

•	Running (R): The process is actively executing on the CPU or is in the ready queue, waiting for its assigned slice of processing time. 
•	Sleeping/Waiting (S or D): The process is suspended, waiting for an event like I/O completion or a timer. It can be interruptible (can be woken by signals) or uninterruptible (cannot be interrupted and usually waits on hardware). 
•	Stopped (T): The process is paused, typically due to receiving a signal (like pressing Ctrl+Z in a terminal) or being debugged. 
•	Zombie (Z): The process has finished executing, but its parent process has not yet read its exit status. 
•	Orphan: An active process whose parent has terminated or crashed. It is automatically re-parented to a system daemon (like systemd) to ensure it gets properly cleaned up.


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
