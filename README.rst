
====================
Leonardo Geo Widgets
====================

Leonardo widgets related with Geo such as Google Map Widget or photo gallery with Geolocation etc..

.. contents::
    :local:

Installation
------------

.. code-block:: bash

    pip install -e git+https://github.com/leonardo-modules/leonardo-geo.git#egg=leonardo_geo

or as leonardo bundle

.. code-block:: bash

    pip install django-leonardo["geo"]

Load new template to db

.. code-block:: bash

    python manage.py sync_all -f

Optional settings (styles in live_settings)
---------------------

Google maps styles (example):

You can insert `JSON format of Google maps`_ styles to LIVE SETTINGS.

.. _JSON format of Google maps: https://gist.github.com/dresl/b6234e39adf019c64e15dc50f53374ca

or

Leaflet maps styles:

Available styles: https://www.mapbox.com/api-documentation/#styles

Or you can create your own: https://www.mapbox.com/help/create-a-custom-style/

Optional Dependencies
---------------------

For advance widgets and features this module use GeoDjango_ is used so a spatial database is required.  We recommend PostGIS. Django's docs include some `installation instructions`_ although it is renowned for being tricky.

.. _GeoDjango: https://docs.djangoproject.com/en/1.4/ref/contrib/gis
.. _`installation instructions`: https://docs.djangoproject.com/en/1.4/ref/contrib/gis/install

Spatialite is another option although it can be tricky to set up.  On Ubuntu,
you can do the following:

.. code:: bash

    $ sudo apt-get install spatialite-bin libspatialite3 libgeos++-dev libgdal-dev libproj0

The ``pysqlite`` python package is also required although it doesn't support C
extensions by default.  To work-around this, there are two options:

1. Download the package, edit ``setup.cfg`` to enable C extensions and install:

.. code:: bash

    $ pip install pysqlite --no-install
    $ vim $VIRTUAL_ENV/build/pysqlite/setup.cfg
    $ pip install pysqlite

2. Use a custom branch:

.. code:: bash

   $ pip install git+git://github.com/tinio/pysqlite.git@extension-enabled#egg=pysqlite

.. _`pysqlite`: http://code.google.com/p/pysqlite


Read More
---------

* https://github.com/django-leonardo
