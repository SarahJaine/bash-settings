# bash-settings
*notes about preferred bash settings in case my laptop is stolen, again* :broken_heart:
_____

## [oh my zsh](https://github.com/robbyrussell/oh-my-zsh)

## subl command 
adapted from [this guide](https://ashleynolan.co.uk/blog/launching-sublime-from-the-terminal)

```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

## custom terminal commands
1. create file containing desired bash script `open-db-schema`.  Example script:
```
#!/bin/bash
open -a Preview ~/shortcut/db-schema
```
2. mark bash script file as executable
```
$ chmod +x open-db-schema
```
3. create a symbolic link between your script and a keyword of your choosing
```
┌── ln(1) link, ln -- make links
│   ┌── Create a symbolic link.
│   │                         ┌── the path to the intended symlink
│   │                         │   can use . or ~ or other relative paths
│   │                  ┌──────┴──────────┐
ln -s ~/open-db-schema /usr/local/bin/sch
      └───────┬───────┘
              └── the path to the original file/folder
                  can use . or ~ or other relative paths
```
4. Now `$ sch` will open contents of `/shortcut/db-schema` with Preview app
