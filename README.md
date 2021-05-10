# What's this?

A web server to fetch screenshots from Rigol oscilloscopes.
More or less completely ripped off from [ds1054z/cli.py](https://github.com/pklaus/ds1054z/blob/master/ds1054z/cli.py)
by [Philipp Klaus](https://github.com/pklaus/ds1054z/).

# Why?

Collaboration. Sharing screenshots of interesting signals. Getting advice about weird stuff.

![Screenshot](https://raw.githubusercontent.com/ckuethe/pervoscope/main/ds1054z_screenshot.jpg)


# And the name?

Because peeping on oscilloscopes over the internet. Like exposed security cameras and baby monitors.

On that note, maybe you don't want to expose this to the internet if you're analyzing secret squirrels.

One more thing: it's not enabled by default, but the `--allow-stop` argument will place the scope into
`STOP` mode before capturing. Some captures can take a bit over two minutes to download and `STOP` mode
might speed that up a bit as well as being a bit more predictable about what is captured. Once complete
the scope with be returned to `RUN` mode if it was running when the capture started. Of course, if you
leave this server exposed to the internet with `--allow-stop` enabled, random idiots might be able to
interfere with your scope by stopping it at an inconvenient time.

# How

There's a systemd unit you can install to run pervoscope; the appropriate nginx, apache, or caddy
reverse proxy configuration is beyond the scope of this document. Beyond that, this server only
responds to [/, /ds1054z, or /rigol](blob/main/pervoscope.py#L104).

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
