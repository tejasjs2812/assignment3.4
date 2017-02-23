# assignment3.4
1. Explain the importance of Namenode in Hadoop cluster
Name node is also known as master node which is the center piece of HDFS. It keep strack of data, where it is kept in cluster. If a client want to locate a file, it communicates with name node to locate a file in the cluster.
A name node is-
1. NameNode only stores the metadata of HDFS – the directory tree of all files in the file system, and tracks the files across the cluster.
2. NameNode does not store the actual data or the dataset. The data itself is actually stored in the DataNodes.
3. NameNode knows the list of the blocks and its location for any given file in HDFS. With this information NameNode knows how to construct the file from blocks.
4. NameNode is so critical to HDFS and when the NameNode is down, HDFS/Hadoop cluster is inaccessible and considered down.
5. NameNode is usually configured with a lot of memory (RAM). Because the block locations are help in main memory.
Name node has two parts-
1. Edit Logs- It maintains transactional data and keep changing on live cluster. Edit logs keep track of all transactional and activity data i.e the data get generated when DDL activities are done. It keeps a copy of itself in the HardDisk as well as in RAM.
2. FSImage- It maintains the merged data which is not changing on live cluster. It persists data on the hard disk of the name node machine. This is kept as only the previous and latest version. Also present in RAM of name node but untouched in live clusters.
-The above two logs are together called name node meta data.
- Name node daemon keeps this above meta data in RAM of high end machine while the name node is up and running for faster access.
- Whenever cluster is brought up, the edit logs get merged into FS Image resulting in latest version of FSImage.
- Name node caters the client request and process according to request to return the result to client.
- Multiple data nodes are connected with one name node and these name node and data node works on heart beat mechanism, Data nodes keep sending on heart beats to name node to state that I am alive and can be assigned some task.
- Name node holds all the meta data in main memory in the running cluster.

Que.2. Practice the beginners commands for HDFS from the below link
Commands 

1. get - get a file present in hadoop system to local, it has checksum.
hadoop fs -put  /home/acadgild/max-temp.txt /user/acadgild/hadoop/max-temp.txt

2. put- put file from hadoop to local, has checksum
hadoop fs -put /user/acadgild/hadoop/max-temp.txt /home/acadgild

3. mkdir- make new directory
hadoop fs -mkdir tejasjs

4. rm- remove file from directory
hadoop fs -rm /user/acadgild/hadoop/max-temp.txt

5. copyToLocal 
copyToLocal will copy file from hadoop fs to local
hadoop fs -copyToLocal /user/acadgild/hadoop/max-temp.txt /home/acadgild

6.copyFromLocal-will copy file from local to hadoop fs
hadoop fs -copyFromLocal /home/acadgild /user/acadgild/hadoop/max-temp.txt 

7. Option -
hadoop fs
will  give every possible option of the command 

8.Help
will give neccessary help when required
hadoop fs -help

9.list
list of all the files present 
hadoop fs -ls /user/acadgild/hadoop

10.cat 
display the containt present in the file
hadoop fs -cat /user/acadgild/hadoop/max-temp.txt

11. fsck-
The command ‘fsck’ is used for checking the consistency of a file system
 hadoop fsck /user/acadgild/hadoop/max-temp.txt
 
 12.Balancer-
 The command ‘balancer’ will check for work load on nodes in cluster and balance it.
Syntax: hadoop balancer

13.Check directory space-
The command will show the file size occupied by file inside cluster.
Syntax: hadoop dfs -du -s -h /user/acadgild/hadoop/max-temp.txt

Screenshots attached





-Screenshots are attached....
