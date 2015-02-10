
Logging Subsystem
=================

Goals:

1. performance (string formatting is avoided)
2. simplicity
3. machine-readable (log processing becomes trivial).

Binary Logging
--------------

I have worked on many projects over the years that involve processing
logs, sometimes *HUGE* amounts of logs.  It's very frustrating parsing
free-formatted, whatever-the-developer-felt-like-writing log files
into useful data.  Binary logging steps around the problem by making
the logs machine readable from the start.

Reading the Logs
----------------

In the ``scripts`` directory you will find ``catlog``, which will process
either stdin, or a path arg.  It can synchronize with the output of
``tail``, or ``tail -f``.

Log Levels
----------

I intend to add a layer that supports log levels, backward compatible
with this code, in that the first item of '*data' will be an integer
log level.