PyPLN
=====

PyPLN is a distributed pipeline for natural language processing, made in Python.
We use `NLTK <http://nltk.org/>`_ and `ZeroMQ <http://www.zeromq.org/>`_ as
our foundations. The goal of the project is to create an easy way to use NLTK
for processing big corpora, with a Web interface.

We don't have a production release yet, but it's scheduled on our
`next milestone <https://github.com/namd/pypln.backend/issues?milestone=1>`_.

PyPLN is sponsored by `Fundação Getulio Vargas <http://portal.fgv.br/>`_.

License
-------

PyPLN is free software, released under the GPLv3
`<https://gnu.org/licenses/gpl-3.0.html>`_.


Documentation
-------------

Our documentation is hosted using `GitHub Pages <http://pages.github.com/>`_:

- `PyPLN Documentation <http://pypln.org/docs>`_
  (created using `Sphinx <http://sphinx.pocoo.org/>`_)
- `Code reference <http://pypln.org/docs/reference/>`_
  (created using `epydoc <http://epydoc.sourceforge.net/>`_)


Requirements
------------
You will need some Python packages, `libmagic <http://www.darwinsys.com/file/>`_,
 `poppler utils <http://poppler.freedesktop.org/>`_ and
 `libfreetype <http://www.freetype.org/>`'s development headers.

To install dependencies (on a Debian-like GNU/Linux distribution)::

    sudo apt-get install python-setuptools libmagic-dev poppler-utils libfreetype6-dev fonts-dejavu
    pip install virtualenv virtualenvwrapper
    mkvirtualenv pypln.backend
    # we need to install Cython first because of the way pip handles C extensions
    pip install Cython
    pip install -r requirements/production.txt

You will also need to download some NLTK data packages. You can do so
executing::

    python -m nltk.downloader genesis maxent_treebank_pos_tagger punkt



Developing
----------

To run tests::

    workon pypln.backend
    pip install -r requirements/development.txt
    make test


..  TODO: The PYTHONPATH issue should be fixed once we organize the directory
    structure. As soon as this is fixed, we must update this instructions.


See our `code guidelines <https://github.com/namd/pypln.backend/blob/develop/CONTRIBUTING.rst>`_.
