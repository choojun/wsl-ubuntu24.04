<img width="206" height="80" alt="ubuntu_backup" src="https://github.com/user-attachments/assets/70319677-0a44-4029-8f85-7218ee3fc4ca" />

# C. Backup the Distro on WSL

1. In Power Shell, list the installed distro on WSL with the following command. Note that you need to know the exact name to create a backup
~~~bash
wsl –l -v
~~~

2. Change the directory that you want to save your backup with command ‘cd’. At the destination of directory, perform the following command to export the distribution of distro with Power Shell.
~~~bash
wsl --export <distribution> <filename.tar>
    e.g. wsl --export Ubuntu-22.04 my-backup-Ubuntu-22.04.tar
~~~

3. Alternatively, instead of using ‘cd’ to get to the destination directory, you may specify the file location and filename as part of export process in the Power Shell as follows.
~~~bash
wsl --export <distribution> <file location with filename.tar>
    e.g. wsl --export Ubuntu-22.04 c:/Users/choojun/Documents/wsl/my-backup-Ubuntu-22.04.tar
~~~

<img width="206" height="80" alt="ubuntu_backup" src="https://github.com/user-attachments/assets/74c465db-944a-4e49-a786-c75c6a178b51" />
