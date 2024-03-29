# awsome-cheatsheet ~ beta
Just my personal notes for daily usage as SysAdmin 
This will get updated soon
## VIM

 **comment multiply lines:**
 
  select with `shift + V` then `:s/^/#`
  
**uncomment multiply lines:**

  select with `shift + V` then `:s/#/`

**Force write with root permision**

  `:w !sudo tee %`
  
  
 **Replace pattern in file**
 `:%s/foo/bar/g`
  

**Insert text into multiple lines at once** [refrence](https://riptutorial.com/vim/example/7301/insert-text-into-multiple-lines-at-once#:~:text=vim%20Inserting%20text%20Insert%20text%20into%20multiple%20lines%20at%20once&text=Use%20%E2%86%91%20%2F%20%E2%86%93%20%2F%20j%20%2F,all%20the%20lines%20you%20selected.)

  `ctrl + v` then use `j | k` to select lines and press `Shift + i` 
  Type the string
  press `Esc` to insert into all lines
  
## TMUX

**Add horizontal pane**
  
  `ctrl + b` then `Shift "`
  
**Add vertical pane**
  
  `ctrl + b` then `Shift %`
  
**[C]reate new window**

  `ctrl b` then `c`
  
**Move pane to a new window**
  `ctrl b ` then `!`
 
**[N]ext window**

  `ctrl b` then `n`
 
 **Enable scroll**
  `ctrl b ` then `[`
  
 **Use Ctrl + Left/Right to move forward/back one word in tmux within Mobaxterm**

Edit your ~/.tmux.conf and add lines:

`set-window-option -g xterm-keys on`
If you don’t want to make it permanent just yet, do:

`ctrl-b :set-window-option xterm-keys on`
Reload your config in tmux by doing:

`ctrl-b :source-file ~/.tmux.conf`

## Docker

### commands
```bash
sudo docker system prune -a -f

sudo docker rm -v $(sudo docker ps -a -q -f status=exited)

sudo docker rmi -f  $(sudo docker images -f "dangling=true" -q)

docker volume ls -qf dangling=true | xargs -r docker volume rm

docker logs --since 30s -f <container_name_or_id>

docker logs --since 30s -f <container_name_or_id>

echo "" > $(docker inspect --format='{{.LogPath}}' <container_name_or_id>)

truncate -s 0 /var/lib/docker/containers/*/*-json.log

```

### docker compose

access host network from container in specific network namespace
```
extra_hosts:
  - "host.docker.internal:host-gateway"
```

## Disk

```du -cha --max-depth=1 / | grep -E "M|G"```

## Process

``` fuser -k <PID> ```

``` ps aux | awk '$8=="Z" {print $2}' ```
