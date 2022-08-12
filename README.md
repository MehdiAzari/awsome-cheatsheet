# awsome-cheatsheet

## VIM

comment multiply lines:
  select with `shift + V` then `:s/^/#`
  
uncomment multiply lines:
  select with `shift + V` then `:s/#/`

Force write with root permision
  `:w !sudo tee %`
