This is a Nagios plugin for checking SSHFP records. It checks that
all SSHFP records correspond to a key the server offers, that all keys
the server offers have SSHFP records, and that all SSHFP records are
correct. Incorrect SSHFP records are considered CRITICAL; missing or
superfluous ones are considered WARNING.

Requires Python 3, dnspython, and the ssh-keyscan program. (On Debian,
that means ``python3-dnspython`` and ``openssh-client``.) Currently
happens to work under Python 2 also, but this has not been tested as
extensively.

Here's a ``define command`` stanza for it:

    define command {
      command_name check_sshfp
      command_line /path/to/check_sshfp '$HOSTADDRESS$'
    }

MIT license.
