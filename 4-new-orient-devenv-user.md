**1\. Add them as a user**

```
$ sudo useradd freddie
```

**2\. Add their password to the system**

```
$ sudo passwd freddie
```

**3\. Add them to the `developers` group**

```
sudo usermod -a -G developers conrad
```

**4\. Change the SSHD config so that they can log into the devbox with a password**

```
$ sudo vim /etc/ssh/sshd_config
```

Add the following to the bottom of the file:

```
Match User freddie
PasswordAuthentication yes
```

**5\. Restart SSHD**

```
$ sudo service sshd restart
```

**6\. Add them to the devbox dashboard**

That's a file change, you'll have to do that manually
