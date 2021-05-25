# King of The Hill

## king.txt
**Simple 1 line command:**
```bash
bash -c "while true; do echo 'name'> king.txt; chatter +ia 'king.txt'; sleep 1; done"
```

**Bash script:**
```bash
#!/bin/bash
while true; do
    echo -e "nexn" > /root/king.txt
    chattr +ia "king.txt"
done
```

**find Shells!!!**
```bash
ps -aef --forest
```

```bash
ps aux --forest
```

**Kill Shells:**
```
kill -9 pid
```

## Send A massage to other users
you can use `wall` for this or you can do it with `/dev/pts`

**Wall:**
```
wall "something"
```

**/dev/pts:**
for this thing you should find the pts number from `ps aux` or `ps -aef --forest`
after the you can easily do:
```bash
echo "something" > /dev/pts/ # and the number
```

