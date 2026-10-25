## Data Engineering with Distributed Environment for Data Analytics: An One-Stop of Setup and Configuration in the Microsoft Windows Subsystem for Linux (WSL) - UBuntu 24.04

Note that this website only contains the setup, practical activities and shared WSL distro (https://github.com/choojun/wsl/releases). 

Data engineering involves building systems to collect and utilize data. This data typically supports subsequent analysis and data science, often incorporating machine learning. Making data usable generally requires significant computational resources, storage, and processing. In essence, data engineering is the design and development of systems that allow individuals to gather and analyze raw data from diverse sources and formats. This website provides a one-stop setup and configuration for the system using Microsoft WSL. Hereby, the website has also incorporated a suite of distributed-ready open source software and guided exploration through selected application samples in the following sections.

### A. Remove/Setup WSL

1. Hardware requirement: recommended **16GB RAM (or more)** and **CPU virtualization enabled** with **constant internet access** during exercises.
Suppose that your Windows has updated to the latest patches too (tested Windows 10 Pro with version 22H2)!  
Software reqirement:
   - Find Settings --> Apps --> Apps & features --> Related Settings --> Programs and Features --> Turn Windows features on or off, **or**
   - Find Settings --> System -->  Optional features --> Related Settings --> More Windows features --> Turn Windows features on or off.

3. Click (for setup) or unclick (for remove) the following items (if any available)
    - Hyper-V
    - Virtual Machine Platform
    - Windows Hypervisor Platform
    - Windows Subsystem for Linux.

4. Restart PC

5. Suppose that your PC accessible to the Internet (for huge files downloading), perform the search of required keyword, e.g., Ubuntu, in the Microsoft Store. Click on the Get button to download and intall the required distro, e.g., UBuntu-xx.xx, and laumch the installed distro via the created link in the Windows Start. A sudoer user will be created during the initial launching.

> To set up the required Ubuntu distro (same version), run the following commands in PowerShell as administrator.
>
> ~~~bash
> wsl --update
> (restart PC)
>
> wsl –-list --online
>
> wsl --install -d UBuntu-xx.xx
> (restart PC)
> ~~~
>
> You may install a specific version of distro under the PowerShell as Administrator, e.g., the adopted version as PC either in lab or your course mate. Then, locate your administrator username and password, after reboot and before first use.
>
> ![wsl_setup](https://github.com/user-attachments/assets/fae87c59-097a-43f4-bea1-1febbaf5e16a)
>




### B. Running Ubuntu on WSL

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





### C. Backup the Distro on WSL

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




### D. Restore (Import) the Distro on WSL

1. In Power Shell, list the installed distro on WSL before removing the same / targeted instance. Note that you need to know the exact name for this process, especially those who wants to restore it at some point on the same PC or on those PC with the same name for distribution of distro. Note that the 'unregister' command will unregister the distribution from WSL and deletes the root filesystems.
~~~bash
wsl –l –v
wsl --unregister <targeted distribution>
~~~

2. Import the distribution of distro with Power Shell. Note that you may import the same distribution of distro into multiple install location, and this is good to facilitate your software development and testing purposes.
~~~bash
wsl --import <distribution> <*install location> <filename.tar>
    e.g. wsl --import Ubuntu-22.04-test1 c:/Users/choojun/Documents/wsl/Ubuntu-22.04-test1 c:/Users/choojun/Documents/wsl/my-backup-Ubuntu-22.04.tar
~~~

3. In Power Shell, verify the distro has been imported correctly.
~~~bash
wsl –l -v
~~~

4. The beauty of using both export and import commands is that you can quickly and easily setup the same environment on multiple machines or setup multiple distros in the same machine. Your users and passwords will be retained, including anything you have installed using the package manager.

### Note for Apple MacOS users
If you are using Apple machines (MacBooks and iMacs with Intel/Apple Silicon processor), you may need to install VMware Fusion Pro (Free for personal use - https://blogs.vmware.com/teamfusion/2024/05/fusion-pro-now-available-free-for-personal-use.html ) to virtualize Ubuntu 24.04.x. You can find the specific 24.04.x installer at https://ubuntu.com/download/alternative-downloads. After completing the Ubuntu setup, follow the same instructions in Sections E to Z to set up the required environment.

| Requirements* (Tested with OpenJDK 17 - LTS) | Apache Hadoop | Appache Spark | Scala | Apache Kafka | Apache HBase | HappyBase / AIOHappyBase | Apache Derby | Apache Hive |
|---|---|---|---|---|---|---|---|---|
| [E. Hadoop Installation and Configuration](wsl_hadoop) | 3.4.1 |  |  |  |  |  |  |  |
| [F. HDFS File Operations and MapReduce](wsl_hdfs) | 3.4.1 |  |  |  |  |  |  |  |
| [G. Spark, PySpark Shell, Spark SQL and JupyterLab](wsl_pyspark) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [H. Spark and Machine Learning](wsl_pyspark_ml) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [I. Spark and Visualisation](wsl_pyspark_viz) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [J. Kafka Installation and Configuration](wsl_kafka) |  |  |  | 4.3.1 |  |  |  |  |
| [K. HBase Installation and Configuration](wsl_hbase) |  |  |  |  | 3.0.0 |  |  |  |
| [L. HappyBase / AIOHappyBase Installation and COnfiguration](wsl_happybase) |  |  |  |  |  | 1.2.0 / 1.4.0 |  |  |
| [M. Hive Installation and Configuration](wsl_hive) |  |  |  |  |  |  | 10.16.x | 4.2.1 |
> Needed WSL2, Web browser and Internet connection, SSH and PDSH, Python 3.12.x
>
> 
Read more required details at URLs
  1. Setup from the scratch - all sections of https://choojun.github.io/wsl
  2. Restore from the pre-setup WSL distro - download the latest release from URL https://github.com/choojun/wsl/releases and perform those steps in the section D of https://choojun.github.io/wsl (after identified your UBuntu version).


### Experimental Version (not stable yet)

| Requirement\Section |  [E](wsl_hadoop)  |  [F](wsl_hdfs_2) |  [G](wsl_pyspark_2) | [H](wsl_pyspark_ml_2)  |  [I](wsl_pyspark_viz_2)  |  [J](wsl_kafka_2)  |  [K](wsl_hbase_2)  |  [L](wsl_happybase_2)  |  [M](wsl_hive_2) |
|---------------------|:--------------------:|:--------------------:|:--------------------:|:--------------------:|:--------------------:|:--------------------:|:--------------------:|:--------------------:|:--------------------:|
| Hadoop              | 3.4.1 (> JDK8) | *1 | *1                  | *1 | *1 | *1                        | *1                   | *1     | *1        |
| Spark               |                |    | 4.0.4 (must jdk17)  | *1 | *1 |                           | *1                   |        | *1        |
| Scala               |                |    | Targeted on 2.13.x  |    |    | 2.13.x                    | Targeted on 2.13.x   |        |           |
| Jupyter Lab         |                |    | *1                  | *1 | *1 |                           |                      |        |           |
| Kafka               |                |    |                     |    |    | kafka_2.13-4.3.1 (jdk17)  | *1                   | *1     |           |
| HBase               |                |    |                     |    |    |                           | 3.x (jdk17)          | *1     |           |
| ?HappyBase          |                |    |                     |    |    |                           |                      | ?1.2.0 |           |
| aiohappybase        |                |    |                     |    |    |                           |                      | 1.4.0  |           |
| Derby               |                |    |                     |    |    |                           |                      |        | 10.16.x (jdk17) |
| Hive                |                |    |                     |    |    |                           |                      |        | 4.2.1 (matched Hadoop 3.4.1) |

> Needed WSL2, Web browser and Internet connection, SSH and PDSH, OpenJDK 17, Python 3.?.?
> 
-----------------------------------------------------------


## References:

https://www.kaggle.com/datasets/moxxis/harry-potter-lstm


