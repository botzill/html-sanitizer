==========
Change log
==========

`Next version`_
===============

- Added a system check which validates sanitizer configurations early
  when using Django.


`1.6`_ (2018-06-29)
====================

- Fixed another edge case where a tag which is allowed to be empty was
  erroneously removed if it contained not only whitespace but also a
  ``<br>`` tag.


`1.5`_ (2018-06-01)
====================

- Fixed a few edge whitespace normalization edge cases and a bug where
  removing an empty tag removed all whitespace.
- Added `black <https://github.com/ambv/black>`_ for automatically
  formatting the Python code.
- By default, links with ``target="_blank"`` get an additional
  ``rel="noopener"`` attribute (`Article by Mathias Bynens
  <https://mathiasbynens.github.io/rel-noopener/>`_). If you're
  overriding the list of allowed attributes for anchor tags you must
  add ``rel`` to your list.


`1.4`_ (2018-03-29)
====================

- Corrected the required lxml version in ``install_requires``.
- Added comments and testing for more edge cases.
- Changed the cleaner to not drop form elements; instead, ``<form>`` is
  converted to ``<p>``, and form elements are preserved.
- Added an ``is_mergeable`` hook for conditionally preventing the
  merging of adjacent elements.
- Fixed a case where paragraphs were allowed inside paragraphs (which
  was never the idea).


`1.3`_ (2017-09-22)
====================

- Fixed a case where tags with content between them were erroneously merged.
- Added a ``tox.ini`` file for running style checks and tests.
- Replaced ``REPLACEMENTS`` and ``element_filters`` with the more
  general ``element_preprocessors`` and ``element_postprocessors``
  settings.
- Removed the restriction that ``<span>`` tags are never allowed.


`1.2`_ (2017-05-25)
====================

- Fixed the erroneous removal of all whitespace between adjacent
  elements.
- Fixed a few occasions where ``<br>`` tags were erroneously removed.
- Back to beautifulsoup4 for especially broken HTML respectively HTML
  with Emojis on macOS.
- Used a ``<div>`` instead of ``<anything>`` to wrap the document (since
  beautifulsoup4 does not like custom tags too much)


`1.1`_ (2017-05-02)
====================

- Added ``html_sanitizer.django.get_sanitizer`` to provide an official
  way of configuring HTML sanitizers using Django settings.


`1.0`_ (2017-05-02)
====================

- Initial public release.


.. _feincms-cleanse: https://pypi.python.org/pypi/feincms-cleanse/
.. _html-sanitizer: https://pypi.python.org/pypi/html-sanitizer/

.. _1.0: https://github.com/matthiask/html-sanitizer/commit/4a995538f
.. _1.1: https://github.com/matthiask/html-sanitizer/compare/1.0...1.1
.. _1.2: https://github.com/matthiask/html-sanitizer/compare/1.1...1.2
.. _1.3: https://github.com/matthiask/html-sanitizer/compare/1.2...1.3
.. _1.4: https://github.com/matthiask/html-sanitizer/compare/1.3...1.4
.. _1.5: https://github.com/matthiask/html-sanitizer/compare/1.4...1.5
.. _1.6: https://github.com/matthiask/html-sanitizer/compare/1.5...1.6
.. _Next version: https://github.com/matthiask/html-sanitizer/compare/1.6...master
