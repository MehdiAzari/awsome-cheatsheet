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
 
**[N]ext window**

  `ctrl b` then `n`
 
 
## Docker
```bash
sudo docker system prune -a -f

sudo docker rm -v $(sudo docker ps -a -q -f status=exited)

sudo docker rmi -f  $(sudo docker images -f "dangling=true" -q)

docker volume ls -qf dangling=true | xargs -r docker volume rm

```
