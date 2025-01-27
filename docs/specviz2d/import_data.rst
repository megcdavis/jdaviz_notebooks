.. _specviz2d-import-data:

*****************************
Importing Data Into Specviz2D
*****************************

By design, Specviz2D only supports data that can be parsed as :class:`~specutils.Spectrum1D` objects,
as that allows the Python-level interface and parsing tools to be defined in ``specutils``
instead of being duplicated in Jdaviz.
:class:`~specutils.Spectrum1D` objects are very flexible in their capabilities, however,
and hence should address most astronomical spectrum use cases.

.. seealso::

    `Reading from a File <https://specutils.readthedocs.io/en/stable/spectrum1d.html#reading-from-a-file>`_
        Specutils documentation on loading data as :class:`~specutils.Spectrum1D` objects.

Specviz2D can either take both a 2D and 1D spectrum as input, or can automatically extract a 1D
spectrum if only a 2D spectrum is provided.  To view the extraction parameters and override the
extraction, see the :ref:`spectral extraction plugin <specviz2d-spectral-extraction>`.

.. _specviz2d-import-commandline:

Importing data through the Command Line
=======================================

You can load your data into the Specviz2D application through the command line (NOTE: this currently
only supports passing a 2D spectrum object and will automatically extract the 1D spectrum)::

    jdaviz specviz2d /my/directory/spectrum.fits


.. _specviz2d-import-gui:

Importing data through the GUI
==============================

You can load your data into the Specviz2D application
by clicking the :guilabel:`Import Data` button at the top left of the application's
user interface. This opens a dialogue where the user can select a file
that can be parsed as a :class:`~specutils.Spectrum1D`.

After clicking :guilabel:`Import`, the data file will be parsed and loaded into the
application.

.. _specviz2d-import-api:

Importing data via the API
==========================

Alternatively, users who work in a coding environment like a Jupyter
notebook can access the Specviz2D helper class API. Using this API, users can
load data into the application through code with the
:meth:`~jdaviz.configs.specviz2d.helper.Specviz2d.load_data`
method, which takes as input a :class:`~specutils.Spectrum1D` object or filename for the
2D spectrum and (optionally) the 1D spectrum.
