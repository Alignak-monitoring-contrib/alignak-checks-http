Alignak checks package for HTTP/HTTPS
=====================================

Checks pack for checking HTTP/HTTPS Web services


Installation
------------

From PyPI
~~~~~~~~~
To install the package from PyPI:
::
   pip install alignak-checks-http


From source files
~~~~~~~~~~~~~~~~~
To install the package from the source files:
::
   git clone https://github.com/Alignak-monitoring-contrib/alignak-checks-http
   cd alignak-checks-http
   sudo python setup.py install


Documentation
-------------

Configuration
~~~~~~~~~~~~~

To use this checks package, you must install some external plugins.
We recommand that you download and install the Monitoring plugins: https://www.monitoring-plugins.org/download.html

Check if it exists a binary package for your OS distribution rather than compiling and installing from source.
Else, the source installation procedure is explained `here<https://www.monitoring-plugins.org/doc/faq/installation.html>`_.
An abstract::

    $ gzip -dc monitoring-plugins-2.x.tar.gz | tar -xf -
    $ cd monitoring-plugins-2.x
    $ ./configure
    $ make

    $ make install

    $ make install-root
    $ # This for plugins requiring setuid (check_icmp ...)

After compilation and installation, the plugins are installed in the */usr/local/libexec* directory.

Alignak configuration
~~~~~~~~~~~~~~~~~~~~~

You simply have to tag the concerned hosts with the template you are interested in.
::

    define host{
        use                     dns, ftp, http
        host_name               my_host
        address                 127.0.0.1
    }



Each template declares the associated services on the concerned host.
You can easily adapt the configuration defined in the ``templates.cfg``, ``services.cfg`` and ``commands.cfg`` files.


Bugs, issues and contributing
-----------------------------

Contributions to this project are welcome and encouraged ... issues in the project repository are
the common way to raise an information.

License
-------

Alignak Pack Checks NRPE is available under the `GPL version 3 license`_.

.. _GPL version 3 license: http://opensource.org/licenses/GPL-3.0