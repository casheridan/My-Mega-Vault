## General/Useful Utilities

| Name        | Command                  | Use                                                                                                       | Example                                                  |
| ----------- | ------------------------ | --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| Web Get     | `wget`                   | downloads files from the web via HTTP                                                                     | `wget [http/https]://[url or ip address]/[file path]`    |
| Secure Copy | `scp`                    | allows transfer of files between two computers using the SSH protocol (provides both auth and encryption) | `scp [file destination] [user]@[ip address]:[file path]` |
| HTTPServer  | `python3 -m http.server` | creates server to serve files off of for commands like `curl` and `wget`                                  | `python -m http.server`                                  |

#### <u>Tips</u>
- Secure Copy can be reversed and download a file from somewhere by stating the host url first then the file destination.
	- `scp <user>@<IP addr>:<remote file path> <destination path>`
- Using the curl or wget command to get files from the server created with HTTPServer 
	- `wget http://<localhost/local ip>:<port>/<path>`

---

## Processes 101

#### <u>Viewing Processes</u>

| Name                   | Command  | Use                                                    | Example    |
| ---------------------- | -------- | ------------------------------------------------------ | ---------- |
| Processes              | `ps`     | lists any running processes in our user's session      | `ps` |
| Auxilary Processes     | `ps aux` | lists other user's and system processes.               | `ps aux` |
| Dynamic Process Viewer | `top`    | provides a dynamic real-time view of running processes | `top` |

#### <u>Managing Processes</u>

| Name              | Command | Use                                                                                                  | Example/Formatting             |
| ----------------- | ------- | ---------------------------------------------------------------------------------------------------- | ------------------- |
| Terminate Process | `kill`  | used to terminate a running process by its PID, specify how cleanly it is terminated with the signal | `kill [signal] [PID]` |         |         |                                                                                                      |                     |

#### <u>Getting Processes/Services to Start on Boot</u>

| Name           | Command     | Use                                            | Example/Formatting                                           |
| -------------- | ----------- | ---------------------------------------------- | ------------------------------------------------------------ |
| System Control | `systemctl` | allows to interact with systemd process/daemon | `systemctl [option] [service]` | Ex: `systemctl start apache2` |

#### <u>An Introduction to Backgrounding and Foregrounding in Linux</u>

<u>Backgrounding</u>
Using the `&` operator to background a process can be useful when scripting. `Ctrl + Z` can also be used when we need to background a process, `Ctrl + Z` can also be used to pause the execution of a script or command

<u>Foregrounding</u>
When a process is running in the background, to bring it back to the foreground we can use the `fg` command

### <u>Tips</u>
- When the `ps` command is ran, it will display (in order left -> right):
	- the process id, the terminal associated with the process, the time it took to ran, and the command that was ran in the process.
- Alternativley, when the `ps aux` command is ran, it will display (in order left -> right):
	- the user, process id, CPU usage percent, memory usage percent, VSZ, RSS, the terminal associated with the process, the stat, the time stamp that it was started, how long it took to run the process, and the command associated with the process
- There are 3 signals that you can use to terminate a process with the `kill` command
	- **SIGTERM** - Kills the process, but allows it to perform cleanup tasks before completing
	- **SIGKILL** - Kills the process, doesn't allow cleanup
	- **SIGSTOP** - Stops/suspends a process
- There are 4 options for `systemctl`
	- **Start** - Starts a service, doesn't turn start on boot-up on
	- **Stop** - Stops a running service, doesn't turn start on boot-up off
	- **Enable** - Starts a service and allows service to start on boot-up
	- **Disable** - Stops a running service and stops a service from starting on boot-up

---

## Maintaining Your System: Automation

#### <u>Crontab</u>

Crontab is a startup process, crontab is responsible to facilitating and managing cron jobs. A crontab is simply a special file with formatting that is recognised by the cron process to execute each line step-by-step.

Crontabs require 6 specific values
| Value | Description                          |
| ----- | ------------------------------------ |
| MIN   | What minute to execute at            |
| HOUR  | What hour to execute at              |
| DOM   | What day of the month to execute at  |
| MON   | What month of the year to execute at |
| DOW   | What day of the week to execute at   |
| CMD   | The actual command that will be executed                                     |

Backing up files. To backup "cmnatic's" "Documents" every 12 hours. The following formatting will be used: `0 12 * * * cp -R /home/cmnatic/Documents/var/backups`

The `*` denotes a wildcard and is used when we do not wish to provide a value for that specific field. Crontabs can be edited by using `crontab -e`, where you can use a CLI editor (like nano) to edit the crontab.

---

## Maintaining Your System: Package Management

#### <u>Introducing Packages & Software Repos</u>

When developers wish to submit their software to the community they will submit it to an "apt" repository. If approved, their programs and tools will be released to the public.

When using `ls` in the `etc/apt` folder you can see the different apt repos you can access. The OS vendors will maintain their own repositories but you may add your own community repos to the list. They can be added using the `add-apt-repository` command or by listing another provider.

#### <u>Managing Your Repositories (Adding and Removing</u>

The `apt` command is a part of the package management software also named apt. Apt contains a whole suite of tools that allows us to manage the packages and sources of our software, and to install or remove software at the same time.

Whilst you can install software through the use of package installers such as `dpkg`, the benefits of apt means that whenever we update our system -- the repository that contains the pieces of software that we add also gets checked for updates.

---

## Maintaining Your System: Logs

Located in the /var/log directory, these files and folders contain logging information for applications and services running on your system. The Operating System  (OS) has become pretty good at automatically managing these logs in a process that is known as "rotating".

These services and logs are a great way in monitoring the health of your system and protecting it. Not only that, but the logs for services such as a web server contain information about every single request - allowing developers or administrators to diagnose performance issues or investigate an intruder's activity. For example, the two types of log files below that are of interest:

-   access log
-   error log

There are, of course, logs that store information about how the OS is running itself and actions that are performed by users, such as authentication attempts.