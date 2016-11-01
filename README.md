# Test Docker Volume

```
+ docker run -it --rm testimage1
-rw-rw-r-- 1 root root 12 Dec 31  2000 /data/testfile.txt | Contents: Test file 1
+ docker run -it --rm testimage2
-rw-rw-r-- 1 root root 12 Feb  1  2002 /data/testfile.txt | Contents: Test file 2
+ docker run -it --rm -v 6d5042350259cf5207a5a6f9c9b8496d9baec35070de9e3a9fd3c9917b411745:/data testimage1
-rw-rw-r-- 1 root root 12 Dec 31  2000 /data/testfile.txt | Contents: Test file 1
+ docker run -it --rm -v 6d5042350259cf5207a5a6f9c9b8496d9baec35070de9e3a9fd3c9917b411745:/data testimage2
-rw-rw-r-- 1 root root 12 Dec 31  2000 /data/testfile.txt | Contents: Test file 1
+ docker run -it --rm -v 6d5042350259cf5207a5a6f9c9b8496d9baec35070de9e3a9fd3c9917b411745:/data ubuntu:16.04 cat /data/testfile.txt
Test file 1
6d5042350259cf5207a5a6f9c9b8496d9baec35070de9e3a9fd3c9917b411745
```
