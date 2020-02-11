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
#### **Start html File in VM:**  
```
python -m SimpleHTTPServer <port_num> 
// the address to access from browser: http://vm_ip:<port>/chart.html
// i.e. http://ip:8000/chart.html, must run this command in the directory of the html file
```

#### **Check if a dependency alrealy installed:**  
```
$ dpkg -s pkg_name

```
