
Module consoletest.
===================


Framework for running console shell examples.

Simple Usage: Checking Examples in a Text File:

Another simple application of consoletest is testing interactive examples in a text file. This can be done with the testfile() function::

    import consoletest
    consoletest.testmod("example.txt")


That short script executes and verifies any interactive Python examples contained in the file example.txt.

::
    The example module
    ======================

    This is an example text file in reStructuredText format.
    
        $ echo Test
        test exemple Failed


Running doctest.testfile("example.txt") then finds the error in this documentation. This won't display anything unless an example fails, in which case the failing example(s) and the cause(s) of the failure(s) are printed to stdout, and the final line of output is "Test failed.".

::

    File "./example.txt", line 6, in example.txt
    Failed example:
        echo Test
    Expected:
        test exemple Failed
    Got:
        Test


testfile() won’t display anything unless an example fails. If an example does fail, then the failing example(s) and the cause(s) of the failure(s) are printed to stdout, using the same format.



