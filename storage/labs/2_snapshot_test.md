```
1) Using WinCP to upload data to master node
2) Log in to jeekhen user
3) run 'hdfs dfs -mkdir precious'
4) run 'hdfs dfs -put SEBC-master.zip precious'
5) Go to CM -> HDFS -> File Browser -> 'Navigate to /home/jeekhen/precious folder'
6) Click enable Snapshot for this folder
7) Input the name into the folder
8) run 'hdfs dfs -rm -r precious' to remove the file
9) Go back to CM and browse to the precious directory
10) Select restore to directory

```