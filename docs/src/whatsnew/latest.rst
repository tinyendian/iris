.. include:: ../common_links.inc

|iris_version| |build_date| [unreleased]
****************************************

This document explains the changes made to Iris for this release
(:doc:`View all changes <index>`.)


.. dropdown:: :opticon:`report` |iris_version| Release Highlights
   :container: + shadow
   :title: text-primary text-center font-weight-bold
   :body: bg-light
   :animate: fade-in
   :open:

   The highlights for this major/minor release of Iris include:

   * N/A

   And finally, get in touch with us on :issue:`GitHub<new/choose>` if you have
   any issues or feature requests for improving Iris. Enjoy!


📢 Announcements
================

#. Welcome to `@ESadek-MO`_ and `@TTV-Intrepid`_  who made their first contributions to Iris 🎉


✨ Features
===========

#. `@ESadek-MO`_ edited :func:`~iris.io.expand_filespecs` to allow expansion of
   non-existing paths, and added expansion functionality to :func:`~iris.io.save`.
   (:issue:`4772`, :pull:`4913`)


🐛 Bugs Fixed
=============

#. `@rcomer`_ and `@pp-mo`_ (reviewer) factored masking into the returned
   sum-of-weights calculation from :obj:`~iris.analysis.SUM`. (:pull:`4905`)

#. `@schlunma`_ fixed a bug which prevented using
   :meth:`iris.cube.Cube.collapsed` on coordinates whose number of bounds
   differs from 0 or 2. This enables the use of this method on mesh
   coordinates. (:issue:`4672`, :pull:`4870`)

#. `@bjlittle`_ and `@lbdreyer`_ (reviewer) fixed the building of the CF
   Standard Names module ``iris.std_names`` for the ``setup.py`` commands
   ``develop`` and ``std_names``. (:issue:`4951`, :pull:`4952`)

#. `@lbdreyer`_ and `@pp-mo`_ (reviewer) fixed the cube print out such that
   scalar ancillary variables are displayed in a dedicated section rather than
   being added to the vector ancillary variables section. Further, ancillary
   variables and cell measures that map to a cube dimension of length 1 are now
   included in the respective vector sections. (:pull:`4945`)


💣 Incompatible Changes
=======================

#. N/A


🚀 Performance Enhancements
===========================

#. `@rcomer`_ and `@pp-mo`_ (reviewer) increased aggregation speed for
   :obj:`~iris.analysis.SUM`, :obj:`~iris.analysis.COUNT` and
   :obj:`~iris.analysis.PROPORTION` on real data. (:pull:`4905`)


🔥 Deprecations
===============

#. N/A


🔗 Dependencies
===============

#. `@rcomer`_ introduced the ``dask >=2.26`` minimum pin, so that Iris can benefit
   from Dask's support for `NEP13`_ and `NEP18`_. (:pull:`4905`)
#. `@trexfeathers`_ advanced the Cartopy pin to ``>=0.21``, as Cartopy's
   change to default Transverse Mercator projection affects an Iris test.
   See `SciTools/cartopy@fcb784d`_ and `SciTools/cartopy@8860a81`_ for more
   details.
   (:pull:`4968`)
#. `@trexfeathers`_ introduced the ``netcdf4!=1.6.1`` pin to avoid a problem
   with segfaults. (:pull:`4968`)


📚 Documentation
================

#. `@ESadek-MO`_, `@TTV-Intrepid`_ and `@trexfeathers`_ added a gallery example for zonal
   means plotted parallel to a cartographic plot. (:pull:`4871`)


💼 Internal
===========

#. `@rcomer`_ removed the obsolete ``setUpClass`` method from Iris testing.
   (:pull:`4927`)

#. `@bjlittle`_ and `@lbdreyer`_ (reviewer) removed support for
   ``python setup.py test``, which is a deprecated approach to executing
   package tests, see `pypa/setuptools#1684`_.  Also performed assorted
   ``setup.py`` script hygiene. (:pull:`4948`, :pull:`4949`, :pull:`4950`)


.. comment
    Whatsnew author names (@github name) in alphabetical order. Note that,
    core dev names are automatically included by the common_links.inc:

.. _@TTV-Intrepid: https://github.com/TTV-Intrepid



.. comment
    Whatsnew resources in alphabetical order:

.. _NEP13: https://numpy.org/neps/nep-0013-ufunc-overrides.html
.. _NEP18: https://numpy.org/neps/nep-0018-array-function-protocol.html
.. _pypa/setuptools#1684: https://github.com/pypa/setuptools/issues/1684
.. _SciTools/cartopy@fcb784d: https://github.com/SciTools/cartopy/commit/fcb784daa65d95ed9a74b02ca292801c02bc4108
.. _SciTools/cartopy@8860a81: https://github.com/SciTools/cartopy/commit/8860a8186d4dc62478e74c83f3b2b3e8f791372e