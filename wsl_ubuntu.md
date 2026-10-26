<img width="206" height="80" alt="ubuntu" src="https://github.com/user-attachments/assets/5cc44314-c0ce-4caa-9bc5-780c7094d0b3" />

# B. Running Ubuntu on WSL

1. Suppose that the required distro as default, run the following command with Power Shell.
~~~bash
wsl ~
~~~

2. Suppose that more than one distro setup in WSL, e.g. after importing backup distro, you may list them and run the particular distro (using created user account AND remember to change it home directory using command ‘cd  ~’) with commands as follows.
~~~bash
wsl –l -v
wsl –d <distro name> -u <created user in distro>
    e.g. wsl –d Ubuntu-22.04 –u tarumt
~~~
> You need to run the following command to update your WSL (mandatory) after performing the Windows Update, regardless Windows 10 or Windows 11
~~~bash
> wsl --update
~~~
> Note that you need to configure your Windows (on Domain, Public and Private Profiles) if you failed to update the WSL.
> ![wsl_firewall](https://github.com/user-attachments/assets/192025eb-3c2b-452d-8298-37134f9e8b73)


3. You may set the targeted distro as default with commands as follows.
~~~bash
wsl –-set-default <distro name>
    e.g. wsl –set-default Ubuntu-22.04
wsl –l -v
~~~

4. Even when issue ‘exit’ command, it does not turn off your WSL distro. You may terminate a running WSL distro with commands as follows.
~~~bash
wsl –t <distro name>
    e.g. wsl –t Ubuntu-22.04
~~~

5. Alternatively, you may issue the following command to terminate a running Linux, e.g. Ubuntu, as follows. Note that you need to provide a valid password (current user) when prompt. The WSL distro may terminate a few minutes later.
~~~bash
sudo shutdown now
~~~



