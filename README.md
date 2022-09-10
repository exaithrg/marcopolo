# marcopolo
save current working directory and cd you back anytime, anywhere, even if the terminal is restarted.

![image-20220910142913316](README.assets/image-20220910142913316.png)

`marco` and `polo` are two shell scripts, polo must be executed by `source polo` to work correctly.

Whenever you execute `marco` the current working directory should be saved, then when you execute `polo`, no matter what directory you are in, `polo` should `cd` you back to the directory where you executed `marco`. 


marco:

```bash
#!/bin/bash
pwd > ~/study/mit_missing/shell_lec2/exer2/lastpolo.log
echo "Current working directory saved. Use polo to cd you back."
```

polo:

```bash
#!/bin/bash
lastpath=$(cat /home/geng/study/mit_missing/shell_lec2/exer2/lastpolo.log)
echo "$lastpath"
cd "$lastpath" 
```

.bashrc:

```bash
alias polo='source /home/geng/study/mit_missing/shell_lec2/exer2/polo'
PATH=$PATH:/home/geng/study/mit_missing/shell_lec2/exer2
export PATH
```

PS: if you just want to go back to the last working directory, just use `cd -`

