Module consoletest -- a framework for running shellscripts examples.

In simplest use, end each module M to be tested with:

#python M.py
'''
 $ echo test
 test
'''

def _test():
    import consoletest
    consoletest.testmod()

if __name__ == "__main__":
    _test()


Then running the module as a script will cause the examples in the docstrings to get executed and verified:

    $ python M.py

This won't display anything unless an example fails, in which case the failing example(s) and the cause(s) of the failure(s) are printed to stdout, and the final line of output is "Test failed.".

Run it with the -v switch instead and a detailed report of all examples tried is printed to stdout, along with assorted summaries at the end.

You can force verbose mode by passing "verbose=True" to testmod, or prohibit it by passing "verbose=False".  In either of those cases, sys.argv is not examined by testmod.

There are a variety of other ways to run consoletest, including integration with the unittest framework, and support for running text files containing doctests.  There are also many ways to override parts of doctest's default behaviors.  See the Library Reference Manual for details.
