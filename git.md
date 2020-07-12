D:\Git\etc\profile.d\git-prompt.sh



```js
else
#	PS1='\[\033]0;$TITLEPREFIX:$PWD\007\]' # set window title
	PS1='\[\033]0;$PWD\007\]' # set window title
	PS1="$PS1"'\n'                 # new line
	PS1="$PS1"'\[\033[32m\]'       # change to green
#	PS1="$PS1"'\u@\h '             # user@host<space>
	PS1="$PS1"'\[\033[35m\]'       # change to purple
    ------------------------
#	PS1="$PS1"'\t'
#	PS1="$PS1"'\T'
	PS1="$PS1"'\@'
#	PS1="$PS1"'\A'
#	PS1="$PS1"'\d'
    -------------------------
    
#	PS1="$PS1"'$MSYSTEM '          # show MSYSTEM
	PS1="$PS1"'\[\033[33m\]'       # change to brownish yellow
	PS1="$PS1"'\w'                 # current working directory
	if test -z "$WINELOADERNOEXEC"



	fi
	PS1="$PS1"'\[\033[0m\]'        # change color
#	PS1="$PS1"'\n'                 # new line
	PS1="$PS1"''                 # new line
	PS1="$PS1"'$ '                 # prompt: always $
fi
```



D:\Git\etc\bash.bashrc

