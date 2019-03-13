# bash-settings
*notes about preferred bash settings in case my laptop is stolen, again* :broken_heart:
_____

## [oh my zsh](https://github.com/robbyrussell/oh-my-zsh)

## Custom terminal commands

## subl
adapted from [this guide](https://ashleynolan.co.uk/blog/launching-sublime-from-the-terminal)

```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

## How to
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

## Commands

`ln -s /usr/local/bin/terraform /usr/local/bin/tf`
`ln -s ~/shortcut/write-running-notes /usr/local/bin/write-note`

```
#!/bin/bash
today=`date +%m/%d/%Y`
printf "##########\n$today\n##########\n\n" | cat - ~/_notes/running_notes.txt > ~/temp_notes.txt && mv ~/temp_notes.txt ~/_notes/running_notes.txt
open -a Sublime\ Text ~/_notes/running_notes.txt
```
