# Linux Interview Questions

A list of gathered interview questions relating to operating linux.

## 1. How can you see which kernel version a system is currently running?
- `uname` prints system info
- `uname -a` prints all system info (host name, os, kernel, kernel version, release, architecture etc.)
- `uname -v` kernel version
- `uname -r` kernel release

## 2. How can you check a system's current ip address?
- `ifconfig` Interface configuration
- `ip addr who` Shows all devices
- `ip addr show eth0` Gives all info for ethernet0

## 3. How do you check for free disk space?
- `df -ah` Gives all file systems (`-a`) in human readable formatting (`-h)`
- Look for harddrive partitions. Something like `/dev/sda1`
- Check suze, used, avail etc.

## 4. How do you manage services on a system?
- `service udev status` checks status of service on old system version
- `systemctl status udev` for new versions

## 5. How would you check the size of a given directory's contents on a disk?
- `ls` to list everything
- `du -sh ./my_directory` gets the disk use

## 6. How would you check for open ports?
- `netstat -tulpn` gives you list of all listening ports
- `sudo netstat -tulpn` gives some extra info such as Program name
- Check local address of ports in a listening state. Also can check the Program name listening on that socket.

## 7. How do you check CPU usage for a process?
- `ps aux | grep nginx` check the process nginx
- `top` gives a lot of info about all processes

## 8. How would you mount a new usb stick in your system?
- `ls /mnt` lists the mounting directory
- `mount /dev/sda2 /mnt` will mount a directory to a target location
- `mount` gives list of mounts

## 9. How do you look up something you don't know?
- `man <command>` gives the manual of a given command
- eg. `man ps` gives description of the `ps` command with examples at the bottom most often

## 10. What can you do when you can't find your answer in `man`?
- Google, stackoverflow, serverfault

## 11. How can you search for a file?
- `find / -type f -name "filename"`

## 12. sudo shortcut
- Oops, I forgot to add `sudo` to the start of my command!
- Use `sudo !!` to call your previous command with sudo attached.

## 13. Killing and yanking text (cut and paste)
- `ctrl + k` cuts from your current position in the cmd line to the end.
- `ctrl + u` cuts from current position to the beginning of the line.
- `ctrl + w` kills the previous word.
- To yank back, use `ctrl + y`.

### Example of a use
- Say you type the command `find /var/log -type f -mtime +1`
- You realise that you need to `sudo`.
- `ctrl + u` cuts to the beginning of the line.
- Type `sudo` and `ctrl + y`.
- ie. `ctrl + u` + `sudo ` + `ctrl + y`.

## 14. Continue editing in text editor (uses $EDITOR)
- Use `ctrl + x + e` to continue editing in text editor.
- Editor is defined as `$EDITOR`.

## 15. Paste argument of previous command
- Say you use `ping 8.8.8.8`.
- Use `alt + .` to get the argument of your last successful command. In this case `8.8.8.8`.

## 16. Unbork your terminal
- Got a messed up temrinal?
- `reset`
