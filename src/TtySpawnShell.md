# TTY Spawn Shell
## Full interactive tty

```bash
# Spawnshell
python3 -c 'import pty;pty.spawn("/bin/bash")'

# set TERM
export TERM=xterm

# For clear the screen
# Ctrl + Z

stty raw -echo; fg

# stty rows 38 columns 116

```

#### OS system spawn shell

```bash
echo os.system("/bin/bash")
```

#### Bash spawn shell

```bash
/bin/sh -i
```

#### Perl spawn shell

```bash
perl â€”e 'exec "/bin/sh";'
```

#### Ruby spawn shell

```bash
ruby: exec "/bin/sh"
```

#### Lua spawn shell

```bash
lua: os.execute("/bin/sh")
```

#### VI spawn shell
```
:!bash
```

#### VI(2) spawn shell

```bash
:set shell=/bin/bash:shell
```

#### Nmap spawn shell
```
!sh
```
