
# QCM

### HTTPS testing
Classic commands (40 pts)

Which command line tools could you use to get the **SSL certificate information** from a remote **HTTPS website**?

_Multiple answers expected._

- `certutil`
- `telnet`
- `openssl`
- `curl`

### Locale categories
Locale (60 pts)

Which of the following is **not** a standard POSIX locale category?

- `LC_MONETARY`
- `LC_CTYPE`
- `LC_COLLATE`
- `LC_MESSAGES`
- `LC_METRIC`

### Filename Hierarchy Standard
File systems (20 pts)

Which of the following directory names is **not** part of the Filename Hierarchy Standard?

- `/media`
- `/srv`
- `/var/lock`
- `/data`
- `/usr/src`
- `/proc`

### Package update command
Installing/Updating (20 pts)

On a system running **Fedora 29**, which of the following commands will update the **firefox** package via the package manager?

- `# yum update firefox`
- `# aptitude update firefox`
- `# rpm -Uvh firefox`
- `# dnf update firefox`
- `# apt-get update firefox`

### Quitting vim
Vim (20 pts)

Which **vim** commands are equivalent to "**save and quit**"?

_Multiple answers expected._

- `:wq`
- `:x`
- `:v`
- `:sq`
- `:sf`

### Postfix config
Emailing (40 pts)

What is the function of this **Postfix** configuration?

```android
relayhost =
relay_transport = relay
relay_domains = static:ALL
smtpd_end_of_data_restrictions = check_client_access static:discard
```

- It forwards all mail with no restrictions.
- It accepts all mail, then discards it.
- It forwards mail from local senders, but discards everything else.
- This configuration produces an error.
- It rejects all mail.

### Vim and sudo
Vim (40 pts)

Why is it dangerous to grant a non-root user the ability to edit a specific file with `vim` as root via `sudo`?

- It is difficult to write a `sudoers` policy that does not contains sensitive files.
- It's not dangerous, it just doesn't work. Attempting to add the `sudoers` policy results in an error.
- The user can source a different, unintended file from within `vim` while it is running as root.
- There is a security vulnerability in `sudo` that makes it unsuitable for granting access to any editor.

### Hosts file
Networking (20 pts)

Consider the following `/etc/hosts` file:

```android
127.0.0.1 localhost localhost.localdomain localhost4 localhost4.localdomain4 alice
::1 localhost localhost.localdomain localhost6 localhost6.localdomain6 ip6-localhost ip6-loopback
ff02::1 ip6-allnodes
192.168.0.10 bob
192.168.0.0/24 home
```

Which entry is **invalid**?

- `127.0.0.1`
- `::1`
- `ff02::1`
- `192.168.0.10`
- `192.168.0.0/24`

### Systemd packages
Systemd (40 pts)

Which of the following classic Linux utilities has **not** had its functions integrated into **systemd**?

- Syslog
- SysVinit
- PAM
- Udev
- ConsoleKit

### Disk backup
Classic commands (40 pts)

Which command could you use to back up a disk device **without** mounting it first?

- cp
- rsync
- dd
- tar
- cpio

### DNS lookup
Classic commands (20 pts)

Which command is used to get information about **DNS records**?

- `netstat`
- `ip`
- `dig`
- `route`
- `hostname`

### Locale basics
Locale (20 pts)

What is the purpose of **locales** in Linux?

- Locales are sets of language/cultural rules, used by programs to display output correctly.
- Locales are geographic locations, used for GeoDNS and other applications requiring location mapping.
- Locales are language translation rules that used to be stored locally; however, now most programs run text through Google Translate.
- Locales are not used on Linux; only Windows has them.

### Mount read-only
File systems (20 pts)

Consider the following `mount` output:

```android
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
devpts on /dev/pts type devpts (rw,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,size=1233498k,nr_inodes=353272,mode=755)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=31,pgrp=1,timeout=0,minproto=5,maxproto=5,direct)
/dev/xvdb on /home type ext4 (rw,relatime,discard,data=ordered)
```

Which filesystem is mounted **read-only**?

- `securityfs`
- `devpts`
- `tmpfs`
- `systemd-1`
- `/dev/xvdb`

### Resource bottlenecks
Performance (20 pts)

If a poorly-performing system is frequently using up its **swap space**, what resource is likely to be its main bottleneck?

- CPU time
- Disk space
- Network bandwidth
- Inodes
- RAM

### View the contents of a file
Classic commands (20 pts)

Which of the following commands can **not** show you the contents of a file?

- `emacs`
- `grep`
- `less`
- `ls`
- `cat`
- `vim`














# Text

# Code
