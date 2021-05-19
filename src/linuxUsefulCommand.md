# useful commands on Linux
## SUID Commands
`find / -user root -perm /4000 2>/dev/null`
`find / -perm -u=s -type f 2>/dev/null`
`find / -type f -name '*.txt' 2>/dev/null`
`find / -user root -perm -4000 -exec ls -ldb {}; > /tmp/suid`
`getcap -r / 2>/dev/null`

## What version of the system ?
`cat /etc/issue`
`cat /etc/*-release`
`cat /etc/lsb-release`
`cat /etc/redhat-release`

## What is its kernel version ?
`cat /proc/version`
`uname -a`
`uname -mrs`
`rpm -q kernel`
`dmesg | grep Linux`
`ls /boot | grep vmlinuz`

## What is the environment variables ?
`cat /etc/profile`
`cat /etc/bashrc`
`cat ~/.bash_profile`
`cat ~/.bashrc`
`cat ~/.bash_logout`
`env`
`set`

## Service settings, there is any wrong allocation?
`cat /etc/syslog.conf`
`cat /etc/chttp.conf`
`cat /etc/lighttpd.conf`
`cat /etc/cups/cupsd.conf`
`cat /etc/inetd.conf`
`cat /etc/apache2/apache2.conf`
`cat /etc/my.conf`
`cat /etc/httpd/conf/httpd.conf`
`cat /opt/lampp/etc/httpd.conf`
`ls -aRl /etc/ | awk ‘$1 ~ /^.*r.*/`

## Is there any cron jobs ?
`crontab -l`
`ls -alh /var/spool/cron`
`ls -al /etc/ | grep cron`
`ls -al /etc/cron*`
`cat /etc/cron*`
`cat /etc/at.allow`
`cat /etc/at.deny`
`cat /etc/cron.allow`
`cat /etc/cron.deny`
`cat /etc/crontab`
`cat /etc/anacrontab`
`cat /var/spool/cron/crontabs/root`