# hookd2gs

`hookd2gs` is a simple wrapper for `D2GS.exe` which does a couple things:

* Automatically restarts D2GS on error (`RtlpWaitForCriticalSection` for example)
* Waits 5mins on any restart, and notifies the players of the restart
* Skips the wait if no players are connected

If you'd like to see support for your OS, more options, or more features, open an issue.

## Usage

```sh
Usage of hookd2gs:
  -host string
        address of d2gs telnet daemon (default "localhost:8888")
  -p string
        d2gs admin password (for telnet)
  -pf string
        path to file containing d2gs admin password (for telnet)
```

## Example

First copy `hookd2gs` into your d2gs directory. Then:

```sh
cd d2gs
echo -n "telnetpassword" > .pw
./hookd2gs -pf .pw
```

It's better to use `pf` over `p` so your password isn't in the process list.
