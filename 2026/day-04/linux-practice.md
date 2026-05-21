#90DaysOfDevOps | Day 04
Challenge By TrainWithShubham Shubham Londhe
#UdaanBatch11

Today I practiced Linux commands and worked in the Linux sandbox. It helped me learn by doing and made the experience more interesting.
A huge thanks to Manoj Dhanda and Shubham Londhe for learning platform. 
Excited to continue my DevOps learning journey and improve my practical skills every day!


I created my own Linux command cheat sheet focused on:

File & Navigation

1.	ls -la				 # list all files (hidden too)
2.	find / -name hello.txt		#search file
3.	tree				#directory structure
4.	pwd				#print current directory
5.	cd ..				#Go to previous directory

Permissions & ownership

6.	chmod 777 file		#give all permission
7.	chmod +x script.sh 		#make executable
8.	chown user:user file		#change owner
9.	umask 			#show default permission

Log & searching

10.	 grep -r “text”			#search text in files
11.	 tail -f logfile.log		#live log monitoring
12.	 awk ‘{print $1}’ file 		#print first column
13.	 sed -i ‘s/old/new/g’ file	#replace text
14.	 journalctl -xe			#system log (deatiled)
15.	 less file.log			#view log file page by page

Disk & Memory

16.	 df -h 				#disk usage
17.	 du -sh * 			#size of files/directories
18.	free -m 			#memory usage
19.	top 				#process monitoring
20.	 htop 				#better top (if installed)

Networking

21.	curl -I https//:example.com #check header
22.	wget <url> 			#download file
23.	 ping google.com 		#check connectivity
24.	nslookup			#DNS lookup
25.	dig domain.com 		#DNS lookup(advanced)

Process Managment

26.	 ps aux | grep nginx  		#find process
27.	 Kill -9 pid 			#force kill process
28.	 Pkill process_name		#kill by name


Compression 

29.	 tar -xvf file.tar.gz		#extract archive
30.	ssh user@server-ip 		#connect to sever


31.	systemctl status service	#services status
32.	systemctl restart service 	#restart services
33.	journalctl -u service -f 	#log for service


