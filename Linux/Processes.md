## Processes
- tasks that lunch any program or run a command.
- Each task gets a unique identifier called PID (Process ID).
- The task ends when you close the program or it completes execution. Some tasks run in the foreground, requiring your direct interaction.
  Others run in the background, operating silently without user input.

#### Commands
ps | show asks for the current terminal session.
ps -A | display all the tasks in the machine.
ps aux | detail information from the task.
sudo lsof (log file path) | find the process that is running into a specific log file.

Source: https://commandlinux.com/how-to/linux-list-processes/#:~:text=How%20do%20I%20see%20all,top%20or%20htop%20commands%20instead.
