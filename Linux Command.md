## **Linux Command**  
#### **Go to directory:**  
```
// go to next level
$ cd folder_name
// go to upper level
$ cd ..
```
#### **Find our space used:**  
```
$ df -hT
$ sudo apt-get autoremove --purge
```
#### **Remove:**
```
$ rm -rf folder
```

#### **Copy file to another directory:**  
```
$ cp /path/to/file/filename /new/path
```

#### **Change authority:**  
```
$ chmod -R 777 filename
```

#### **Copy file from guest machine to host machine:**
```
// in host machine, run
$ scp username@guest_ip:/file/path/filename /host/path/to/store
```
