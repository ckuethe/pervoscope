# What's this?

A web server to fetch screenshots from Rigol oscilloscopes.
More or less completely ripped off from [ds1054z/cli.py](https://github.com/pklaus/ds1054z/blob/master/ds1054z/cli.py)
by [Philipp Klaus](https://github.com/pklaus/ds1054z/).

# Why?

Collaboration. Sharing screenshots of interesting signals. Getting advice about weird stuff.

# And the name?

Because peeping on oscilloscopes over the internet. Like exposed security cameras and baby monitors.

# How

```
usage: pervoscope.py [-h] [-p PORT] [-H HOST] [-o RATIO] [-k KEEPALIVE]
                     [-t TIMEOUT] [-d] [-s]

optional arguments:
  -h, --help            show this help message and exit
  -p PORT, --port PORT
  -H HOST, --host HOST
  -o RATIO, --overlay RATIO
  -k KEEPALIVE, --keepalive KEEPALIVE
  -t TIMEOUT, --timeout TIMEOUT
  -d, --debug
  -s, --allow-stop
```
