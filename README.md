Test-Driven Data Analysis (Python TDDA library)
===============================================

Installation
------------

The simplest way to install all of the TDDA Python modules is using *pip*:

    pip install tdda

The full set of sources, including all examples, are downloadable from
PyPi with:

    pip download --no-binary :all: tdda

The sources are also publicly available from Github:

    git clone git@github.com:tdda/tdda.git

Documentation is available at http://tdda.readthedocs.io.

If you clone the Github repo, use

    python setup.py install

afterwards to install the command-line tools (`tdda` and `rexpy`).


*Level 0:*
----------

The `tdda.referencetest` library is used to support
the creation of *reference tests*, based on either unittest or pytest.

These are like other tests except:

  1. They have special support for comparing strings to files
     and files to files.
  2. That support includes the ability to provide exclusion patterns
     (for things like dates and versions that might be in the output).
  3. When a string/file assertion fails, it spits out the command you
     need to diff the output.
  4. If there were exclusion patterns, it also writes modified versions
     of both the actual and expected output and also prints the diff
     command needed to compare those.
  5. They have special support for handling CSV files.
  6. It supports flags (-w and -W)  to rewrite the reference (expected)
     results once you have confirmed that the new actuals are correct.

The package includes docstrings, available with:

    >>> from tdda import referencetest
    >>> help(referencetest)

For more details from a source distribution or checkout, see the `README.md`
file and examples in the `referencetest` subdirectory.

*Level 1:*
----------

The `tdda.constraints` library is used to 'discover' constraints
from a (Pandas) DataFrame, write them out as JSON, and to verify that
datasets meet the constraints in the constraints file.

For usage details:

    >>> from tdda import constraints
    >>> help(constraints)

For more details from a source distribution or checkout, see the `README.md`
file and examples in the `constraints` subdirectory.

The `tdda` repository also includes `rexpy`, a tool for automatically
inferring regular expressions from a single field of data examples.

The package also has doc strings, which you can see with:

    >>> from tdda import rexpy
    >>> help(rexpy)

*Resources*
-----------

Resources on these topics include:

  * TDDA Blog: http//www.tdda.info
  * Quick Reference Guide ("Cheatsheet"): http://www.tdda.info/pdf/tdda-quickref.pdf
  * Full documentation: http://tdda.readthedocs.io
  * General Notes on Constraints and Assertions: http://www.tdda.info/constraints-and-assertions
  * Notes on using the Pandas constraints library:
    http://www.tdda.info/constraint-discovery-and-verification-for-pandas-dataframes
  * PyCon UK Talk on TDDA:
      - Video: https://www.youtube.com/watch?v=FIw_7aUuY50
      - Slides and Rough Transcript:   http://www.tdda.info/slides-and-rough-transcript-of-tdda-talk-from-pycon-uk-2016

All examples, tests and code should run under Python2 and Python3.

