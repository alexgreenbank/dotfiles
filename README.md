# dotfiles
A dump of public dotfiles and useful scripts

| file | description  |
|---|---|
| .screenrc | Screen config file  |
| beep | Make a terminal beep every second |

## .screenrc

Don't know where I found this but it creates a nice caption line at the bottom of the terminal window with hostname, window names, loadavg and date/time.
```
shell -${SHELL}
caption always '%{gk}[ %{G}%H %{g}][ %{w}%?%-w%?%{=b kR}%n %{W}%t%{= w}%?%+w%?%?%= %{g}][%{B}%l%{=b g}][ %{B}%D %d-%m %c %{g}]'
```

## beep

Simple shell script to echo an ASCII `BEL` character every second. I use it to let me know something running in another terminal/screen window has finished. Screen gives a nice "Bell in window X" message when it starts to go off if you haven't already heard it (I don't always have headphones in).

Note: You can either use `echo -n ` (that's a Ctrl+V then Ctrl+G) or use `printf "\a"`. It seems the `printf` option is more readable in git/scripts...

I normally stick this as /usr/bin/beep
```sh
#!/bin/sh

while true
do
	printf "\a"
	sleep 1
done
```

## License

All files are free to use without attribution.
