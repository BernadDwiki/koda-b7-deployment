## 1.
```
bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ sudo adduser koda
bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ sudo adduser dako

bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ sudo addgroup devteam

bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ sudo usermod -aG devteam koda
bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ sudo usermod -aG devteam dako

bernaddwiki@bernaddwiki-ThinkPad-T420s:~$ mkdir srv
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ mkdir projectX
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv/projectX$ 
```

## 2.
```
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ sudo chown -R koda:devteam projectX
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ ls -l
total 4
drwxrwxr-x 2 koda devteam 4096 Apr 16 18:22 projectX
```

## 3.
```
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ sudo chmod g=rx,o= projectX
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ ls -l
total 4
drwxr-x--- 2 koda devteam 4096 Apr 16 18:22 projectX
```

## 4.
```
bernaddwiki@bernaddwiki-ThinkPad-T420s:~/srv$ su koda
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ cd projectX
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ touch README.md
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ mkdir src
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ mkdir data
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ cd src
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/src$ touch app.sh
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/src$ cd ..
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ cd data
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/data$ touch input.txt
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/data$ cd ..
```

## 5.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/src$ chmod ug+x,o-x app.sh
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/src$ ls -l
total 0
-rwxrwxr-- 1 koda koda 0 Apr 16 18:53 app.sh
```

## 6.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/data$ chmod u=rw,go= input.txt
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX/data$ ls -l
total 0
-rw------- 1 koda koda 0 Apr 16 18:54 input.txt
```

## 7.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ chown -R :devteam src
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ chmod -R g=rwx src
```

## 8.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ chown -R koda:devteam projectX
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ ls -l
total 4
drwxr-x--- 4 koda devteam 4096 Apr 16 18:52 projectX
```

## 9.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ chmod o-w,g+w projectX
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ ls -l
total 4
drwxrwx--- 4 koda devteam 4096 Apr 16 18:52 projectX
```

## 10.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ chmod a+r,u+w,go-w,a-x README.md
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv/projectX$ ls -l
total 8
drwxrwxr-x 2 koda devteam 4096 Apr 16 18:54 data
-rw-r--r-- 1 koda devteam    0 Apr 16 18:52 README.md
drwxrwxr-x 2 koda devteam 4096 Apr 16 18:53 src
```

## 11.
```
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ sudo chown -R dako:devteam projectX
koda@bernaddwiki-ThinkPad-T420s:/home/bernaddwiki/srv$ ls -l
total 4
drwxrwx--- 4 dako devteam 4096 Apr 16 18:52 projectX
```