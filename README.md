## Svcstat.py

This is a simple python script which will iterate through a config file, and determine if a list of processes are running or not. It is intended to be added to your shell's init script and be run at login to facilitate expedient triage of system issues.

####Default configuration file locations
The script will first try to read `~/.svcstat`, and will subsequently try to read `/usr/local/etc/svcstat.conf`

#### Specifying the config file to use
the script may be told the path of the configuration file explicitly by invoking the script with the `-f configfilepath` option

## Config File format

The configfile is a csv. Every line is treated as a seperate process to search for.

If there is only one element on a line, that string is used as both the pretty name displayed by svcstat, and the name to search for in the process tree.

If there are two elements on a line, the first element is treated as the pretty name for the process, and the second element is searched for in the process tree.

##### Example

    [user@svchost ~]$ cat /usr/local/etc/svcstat.conf
    foo
    foobar,goobar
    Apache Webserver,httpd
    sshd
    [user@svchost ~]$ svcstat.py
    foo: Not Running
    foobar: Not Running
    Apache Webserver: Running
    sshd: Running

## Contributing

I would love this script to be way more awesome! Do you have an idea for improvement? Great! I'd love your help!

Please fork the repo, and submit a pull request with your changes.

## Questions

  * Email: Wolf@wolfspyre.com

  * IRC:    wolfspyre on freenode

  * Twitter: @loiosh

## Changelog

  * 0.1.1 06/29/14
    * Initial release
