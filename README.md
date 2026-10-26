## Data Engineering with Distributed Environment for Data Analytics: An One-Stop of Setup and Configuration in the Microsoft Windows Subsystem for Linux (WSL) - UBuntu 24.04

Note that this website only contains the setup, practical activities and shared WSL distro (https://github.com/choojun/wsl/releases). 

Data engineering involves building systems to collect and utilize data. This data typically supports subsequent analysis and data science, often incorporating machine learning. Making data usable generally requires significant computational resources, storage, and processing. In essence, data engineering is the design and development of systems that allow individuals to gather and analyze raw data from diverse sources and formats. This website provides a one-stop setup and configuration for the system using Microsoft WSL. Hereby, the website has also incorporated a suite of distributed-ready open source software and guided exploration through selected application samples in the following sections.

| Section (Tested with WSL2 and Ubuntu 24.04 - LTS) | Windows 7 | Windows 10 | Windows 11 |
|---|---|---|---|
| [A. Remove/Setup WSL](wsl_setup.md) | ❌ | ✔ | ✔ |
| [B. Running Ubuntu on WSL](wsl_ubuntu.md) | ❌ | ✔ | ✔ |
| [C. Backup the Distro on WSL](wsl_backup.md) | ❌ | ✔ | ✔ |
| [D. Restore (Import) the Distro on WSL](wsl_restore.md) | ❌ | ✔ | ✔ |

### Note for Apple MacOS users
If you are using Apple machines (MacBooks and iMacs with Intel/Apple Silicon processor), you may need to install VMware Fusion Pro (Free for personal use - https://blogs.vmware.com/teamfusion/2024/05/fusion-pro-now-available-free-for-personal-use.html ) to virtualize Ubuntu 24.04.x. You can find the specific 24.04.x installer at https://ubuntu.com/download/alternative-downloads. After completing the Ubuntu setup, follow the same instructions in Sections E to Z to set up the required environment.

| Section (Tested with OpenJDK 17 - LTS) | Apache Hadoop | Appache Spark | Scala | Apache Kafka | Apache HBase | AIO/HappyBase | Apache Derby | Apache Hive |
|---|---|---|---|---|---|---|---|---|
| [E. Hadoop Installation and Configuration](wsl_hadoop.md) | 3.4.1 |  |  |  |  |  |  |  |
| [F. HDFS File Operations and MapReduce](wsl_hdfs.md) | 3.4.1 |  |  |  |  |  |  |  |
| [G. Spark, PySpark Shell, Spark SQL and JupyterLab](wsl_pyspark.md) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [H. Spark and Machine Learning](wsl_pyspark_ml.md) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [I. Spark and Visualisation](wsl_pyspark_viz.md) |  | 4.0.4 | 2.13.18 |  |  |  |  |  |
| [J. Kafka Installation and Configuration](wsl_kafka.md) |  |  |  | 4.3.1 |  |  |  |  |
| [K. HBase Installation and Configuration](wsl_hbase.md) |  |  |  |  | 3.0.0 |  |  |  |
| [L. HappyBase / AIOHappyBase Installation and COnfiguration](wsl_happybase.md) |  |  |  |  |  | 1.2.0 / 1.4.0 |  |  |
| [M. Hive Installation and Configuration](wsl_hive.md) |  |  |  |  |  |  | 10.16.x | 4.2.1 |
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
https://learn.microsoft.com/en-us/windows/wsl/
https://ubuntu.com/
https://hadoop.apache.org/
https://openjdk.org/
https://spark.apache.org/
https://www.scala-lang.org/
https://kafka.apache.org/
https://hbase.apache.org/
https://happybase.readthedocs.io/
https://github.com/python-happybase/aiohappybase
https://hive.apache.org/
https://db.apache.org/derby/
https://jupyter.org/
https://www.python.org/


https://www.wikipedia.org/
https://www.tablesgenerator.com/
https://www.kaggle.com/datasets/moxxis/harry-potter-lstm
https://linuxiac.com/windows-subsystem-for-linux-explained-wsl-wsl2/
https://web.facebook.com/groups/1073126727485389/posts/1624393212358735


