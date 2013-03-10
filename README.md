phpkit
======

PHP Backdooring framework using include() and php://input to execute code.

phpkit-0.2a

Stealth PHP Backdooring Utility - Insecurety Research 2013

This is a simple kit to demonstrate a very effective way of
backdooring a webserver running PHP.
Essentially, it functions by parsing out any valid PHP code
from raw HTTP POST data sent to it, and executing said PHP.

No eval() or other suspect calls are in the serverside script,
the code is executed by the include() function. The php://input
data stream (which is basically "anything sent via raw POST) is
used to "capture" the raw POST data, and when parsed by include()
the code sent is executed.

USAGE (server side backdoor):
Upload "odd.php" to the webserver by any means necessary.

USAGE (client side application):
For a shell, just run:
./phpkitcli.py --url http://example.tld/path/to/shell.php

This will automatically attempt to spawn a shell prompt.
Please note, the shell is non interactive in that you cannot
run programs like "nano" or "vi" via it. You know what I mean.

This version includes a file uploader!
To upload files, do the following:

./phpkitcli.py --url http://example.tld/path/to/shell.php --mode UPLOAD --lfile /path/to/local/file --rfile /path/on/server/for/file

This should upload your file to the remote server and save it to the path specified.

Prerequisites:
You must have the python "requests" module installed.
- On Debian/Ubuntu: sudo apt-get install requests
- On anything else: pip install requests

Please send me any bugs :)

- NOTE: if you want a real web backdoor, try Weevely or Webhandler.
- http://github.com/epinna/Weevely
- http://github.com/lnxg33k/webhandler


