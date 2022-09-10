# marcopolo
save current working directory and cd you back anytime, anywhere

`marco` and `polo` are two shell scripts, polo must be executed by `source polo` to work correctly.

Whenever you execute `marco` the current working directory should be saved, then when you execute `polo`, no matter what directory you are in, `polo` should `cd` you back to the directory where you executed `marco`. 


marco:

```
#!/bin/bash
pwd > ~/study/mit_missing/shell_lec2/exer2/lastpolo.log
echo "Current working directory saved. Use polo to cd you back."
```

polo:

```
#!/bin/bash
lastpath=$(cat /home/geng/study/mit_missing/shell_lec2/exer2/lastpolo.log)
echo "$lastpath"
cd "$lastpath" 
```

.bashrc:

```
alias polo='source /home/geng/study/mit_missing/shell_lec2/exer2/polo'
PATH=$PATH:/home/geng/study/mit_missing/shell_lec2/exer2
export PATH
```
