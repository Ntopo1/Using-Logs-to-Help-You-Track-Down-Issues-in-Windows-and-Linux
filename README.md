<h1> Using Logs to Help You Track Down an Issue in Windows and Linux</h1>
<h2>Description</h2>
<p>In this lab, I'll use logs to help you troubleshoot and track down issues in a Windows environment and a Linux environment. I will update out-of-date software, find and delete files, modify file permissions, find and terminate specific processes in both Windows and Linux.</p> 
<br />
<h2>Utilities Used</h2>
<ul>
    <li><b>Windows</b> -The operating system used for first half of the lab</li>
    <li><b>Event View</b> -Program used to view event logs</li>
    <li><b>File Explorer</b> -Program used to find files</li>
    <li><b>Task Manager</b> -Program used to view running processes and programs</li>
    <li><b>Ubuntu</b> -The operating system used for the second half, the Linux portion.</li>
</ul>
<br />
<h3>Windows Tasks:</h3>
<h4>Task 1: Low Disk Space</h4>
<p>To view the error logs, I opened the Event Viewer program and navigated to the Application logs inside of the Windows Logs file. Click the first error log in the Application pane to view the first error log. You can see the issue in the details tab toward the bottom. </p> 
<p align="center">
<img src="https://i.imgur.com/jcFwg5r.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> The log states "Error: Disk space is super low, fix it!" I then open the file viewer program. I select "This PC" on the navigation panel on the left. I filter my search to show all files larger than 4GB.</p>
<p align="center">
<img src="https://i.imgur.com/U4oTEVk.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> Once the search results are returned, I deleted the file by right-clicking it and selecting the delete option, you could also delete the file by selecting it and hitting the delete button on your keyboard.</p>
<br /> 
<p align="center">
<img src="https://i.imgur.com/ExD8KmC.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="center">
<img src="https://i.imgur.com/8TC0j45.png" height="80%" width="80%" alt="average height"/>
</p>
<br />
<br />
<h4>Task 2:Edit File Permissions</h4> 
<p>I returned to Event Viewer to view the second log. </p> 
<br /> 
<p align="center">
<img src="https://i.imgur.com/PukYfiP.png" height="80%" width="80%" alt="max"/>
</p>
<p align="left"> The details of the second error log states, "Error: Write Permission Denied for 'Everyone' C:\Users\Temp\super_secret_file.txt". I then swapped back to File Viewer and navigate to the file in the log, right click the file and selected properties</p> 
<p align="center">
<img src="https://i.imgur.com/zY1FxRp.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> I selected the Security tab at the top of the file properties pane. I selected edit, then chose the "Everyone" group and clicked the "Write" box to give the group the ability to write to the file. I applied the changes and hit ok in both panes.</p>
<br /> 
<p align="center">
<img src="https://i.imgur.com/fYDxJ7i.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h4>Task 3:End or Kill a Process</h4>
<p>I returned to Event Viewer to view the third log. </p> 
<br /> 
<p align="center">
<img src="https://i.imgur.com/hsBlxYe.png" height="80%" width="80%" alt="max"/>
</p>
<p align="left"> The details of the third error log states, "Error: Process totally_not_malicious.exe is malicious, terminate the process immediately!". I then opened the task manager by hitting ctrl+shift+esc. I found the task in the list of processes, right clicked it and selected End Task </p> 
<p align="center">
<img src="https://i.imgur.com/32VFquC.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> I selected the Security tab at the top of the file properties pane. I selected edit, then chose the "Everyone" group and clicked the "Write" box to give the group the ability to write to the file. I applied the changes and hit ok in both panes.</p>
<br /> 
<br />
<h4>Task 4:Update out-of-date Software</h4> 
<p>I returned to Event Viewer to view the 4th log. </p> 
<br /> 
<p align="center">
<img src="https://i.imgur.com/kpAUZUg.png" height="80%" width="80%" alt="max"/>
</p>
<p align="left"> The details of the fourth error log states, "Error: VLC-Package out of date, upgrade to the latest version". I opened the program, clicked the help tab at the top and selected Check for Updates. </p> 
<p align="center">
<img src="https://i.imgur.com/oZBB2ul.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> The program found that there were updates available and asked if I wanted to download them. I selected yes.</p>
<br /> 
<p align="center">
<img src="https://i.imgur.com/qITZUaE.png" height="80%" width="80%" alt="average height"/></p>
<p align="left"> I then installed the updates by selecting install. </p> 
<p align="center">
<img src="https://i.imgur.com/kyIE3Ey.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h4>Task 5: Remove a Corrupted File </h4>
<p>I returned to Event Viewer to view the last log. </p> 
<br /> 
<p align="center">
<img src="https://i.imgur.com/yYKZEgY.png" height="80%" width="80%" alt="max"/>
</p>
<p align="left"> The last log states "Error: There is a corrupted file found in C:\Users\corrupted_file. Remove this file". I located the corrupted file in File Explorer by navigating to the stated file path. Right clicked the file and deleted it. </p> 
<p align="center">
<img src="https://i.imgur.com/lw7ioZi.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br /> 
<h3>Linux Tasks:</h3>
<h4>Task 1: Low Disk Space</h4>
<p>I started by viewing the system logs in the /var/logs/ directories.</p> 
<p align="center">
<img src="https://i.imgur.com/kkpvNTW.png" height="80%" width="80%" alt="average height"/>
</p>
<p align="left"> I listed the files in the home directory with the du command, piped the results to the sort command, and used the -n and -r  flags to sort and treat the string output on each line as a number (the file size), and to sort in reverse order so that the largest files are listed first. Then piped the results to list the top 5 results. I then removed the large file. </p>
<p align="center">
<img src="https://i.imgur.com/FqfTfq9.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h4>Task 2: Remove a Corrupted File</h4>
<p>I used a similar command to list all of the files in the /home/lab/directory and used the rm command to remove the file.</p> 
<p align="center">
<img src="https://i.imgur.com/9pq4MNj.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h4>Task 3: Update out-of-date Software</h4>
<p>I started by using the command 'sudo apt-get update' followed by 'sudo apt-install'. Some dependencies were missing so those needed to be installed as well. I entered 'Y' when prompted to approve the additional disk space needed.</p> 
<p align="center">
<img src="https://i.imgur.com/MBv4yzz.png" height="80%" width="80%" alt="average height"/>
</p>
<br />
<br />
<h4>Task 4: Terminate or Kill a Process</h4>
<p>I used the 'ps' command to list the processes current running with the '-ef' to list every running process in full-format-listing. I used the 'kill' command to end the malicious program, process ID(PID) 316.</p> 
<p align="center">
<img src="https://i.imgur.com/xGb4hTX.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h4>Task 5: Edit File Permissions</h4>
<p>For the final task, I changed directories to /home/lab/. I changed the permission for everyone to be able to be able to read, write and execute for the file 'super_secret_file.txt' by using the 'chmod 777' command. I then listed the permissions of all files and directories within the /home/lab/ directory using the '-la' flags to make sure everyone has access to the file.</p> 
<p align="center">
<img src="https://i.imgur.com/Y4EnDlG.png" height="80%" width="80%" alt="average height"/>
</p>
<br /> 
<br />
<h3>Conclusion:</h3>
<p >This exercise is a perfect example of how much more efficient using a command line interface(CLI) can be. It may take more time to remember the commands, but it's certainly quicker than navigating through a graphical user interface(GUI). Finding error logs will not always be clustered and as straightforward as this lab, the same thing applies to file names, they will not always have such obvious names.</p>
