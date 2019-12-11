# Cat files matching /var/log/messages* glob pattern

[Cat-messages.slax](https://github.com/jumation/cat-messages/blob/master/cat-messages.slax) prints the content of all the files in Junos `/var/log` directory matching the `messages*` glob pattern. Useful for searching something from all the log files including the compressed ones, e.g `op cat-messages | match bgpio-0-th`.

## Overview

As Junos does not support the `file show /var/log/messages*` command, then this script finds all the files in Junos `/var/log` directory matching the `messages*` glob pattern and prints the content of the files one by one using RPC behind the Junos `file show <filename>` command. Output is identical to Unix shell `zcat -f /var/log/messages*` except additional newlines after each `file show <filename>` command:
![op cat-messages example](https://github.com/jumation/cat-messages/blob/master/cat-messages_output.png)


## Installation

Copy(for example, using [scp](https://en.wikipedia.org/wiki/Secure_copy)) the [cat-messages.slax](https://github.com/jumation/cat-messages/blob/master/cat-messages.slax) to `/var/db/scripts/op/` directory and enable the script file under `[edit system scripts op]`. In case of two routing engines, the script needs to be copied to the `/var/db/scripts/op/` directory on both routing engines.


## License

[GNU General Public License v3.0](https://github.com/jumation/cat-messages/blob/master/LICENSE)
