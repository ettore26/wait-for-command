# wait-for-command

`wait-for-command` is a Posix sh compliant pure shell script which works in BusyBox. Inspired by [wait-for-it.sh](https://github.com/vishnubob/wait-for-it).

## ./wait-for-command.sh `--help`

<pre>
Usage: wait-for-command.sh [-c 'COMMAND']
       wait-for-command.sh [OPTION]... [-c 'COMMAND']
       wait-for-command.sh [-c 'COMMAND'] [OPTION]...

wait-for-command.sh compares a command exit status to some given number(s) 
for a period of time. If comparison is successfully 
wait-for-command.sh returns 0, otherwise 1.

Example: wait-for-command.sh -c 'echo > /dev/tcp/127.0.0.1/5432'
	  wait-for-command.sh -s 0 57 -c 'curl 127.0.0.1:5432'
	  wait-for-command.sh -c 'nc -z 127.0.0.1 5432' -s 0 -t 20
		 
Options:
  -c, --command ['COMMAND']   execute a COMMAND.
  -s, --status [NUMBER]...    target exit status of COMMAND, default 0.
  -t, --time [NUMBER] 	      max time to wait in seconds, default 10.
  -q, --quiet                 do not make any output, default false.
      --help	              display this help.

Notice that quotes are needed after -c/--command for multi-argument 
COMMANDs.

Specifying a same option more than once overrides the previews. 
So "wait-for-command.sh -c 'nothing' -c 'curl 127.0.0.1:5432'" will be 
the same as "wait-for-command.sh -c 'curl 127.0.0.1:5432'". 
It does not apply to option "-q, --quiet".
</pre>
