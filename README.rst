|logo|
======
|pypi| |travis| |coveralls| |quality| |python2| |python3| |maintain| |website| |license|

django-latexify let’s you easily render text and math equations from your template to look like LaTeX. The app lets you render math equations written in LaTeX on your HTML, or even just regular plain text.

It uses Katex (a fast, easy-to-use JavaScript library for TeX math rendering on the web) for rending math equations and a modification of WiTex (LaTeX like CSS) for rending plain text.


installation
------------

       pip install django-latexify

Quick start
-----------

1. Add "latexify" to your INSTALLED_APPS setting like this:

      .. code-block:: python

         INSTALLED_APPS = (
             ...
             'latexify',
             ...
         )

2. In your template, load latexify by including::

        {% load latexify %}

3. In the HTML header of your template, include::

        {% include 'latexify/stylesheets.html' %}


4. In the bottom of your HTML body, include the following to load the JS associated with latexify::

        {% include "latexify/scripts.html" %}

5. Latexify your text by including the template tag, for example

      .. code-block:: html

         {% latexify context_arg %}
         {% latexify context_arg parse_math=True %}
         {% latexify 'c = \pm\sqrt{a^2 + b^2}' math_inline=True %}
         {% latexify 'c = \pm\sqrt{a^2 + b^2}' math_block=True %}

Which will give you the following:

|example|


6. To add line breaks, add ``\newline`` to your math equation. For example:

   .. code-block:: html

      {% latexify 'x = a + b \newline a = 1 \newline b = 2' math_block=True %}



7. In your HTML, be sure to include this before the `<html>` tag.

        <!DOCTYPE html>


Contributing
------------

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

License
-----------

All parts of django-latexify are free to use and abuse under the `open-source MIT license <https://github.com/ammsa/django-latexify/blob/master/LICENSE>`_.


Change Log
-----------


**Version 0.3.2:**

- Fix issue where special characters such as ampersands (e.g. used in a latex `matrix`` environment for alignment) would be resolved to HTML elements and confuse KaTeX.
- Updated to use KaTeX 0.16.4. 

**Version 0.3:**

- Support line breaks (Add :code:`\newline` inside your math equations)
- Drop support for older Django versions
- Support Django 2.0+

**Version 0.2:**

- Support python3.


.. |logo| image:: https://raw.githubusercontent.com/AmmsA/django-latexify/master/imgs/logo.png
   :width: 100px
   :alt: django-latexify
   :target: https://github.com/ammsa/django-latexify
.. |example| image:: https://raw.githubusercontent.com/AmmsA/django-latexify/master/imgs/example.png
   :scale: 50 %
.. |travis| image:: https://travis-ci.org/AmmsA/django-latexify.svg?branch=master
   :alt: Build Status - master branch
   :target: https://travis-ci.org/AmmsA/django-latexify
.. |coveralls| image:: https://img.shields.io/coveralls/AmmsA/django-latexify/master.svg
   :target: https://coveralls.io/github/AmmsA/django-latexify
.. |pypi| image:: https://img.shields.io/pypi/v/django-latexify.svg
   :target: https://pypi.python.org/pypi/django-latexify
   :alt: Latest PyPI version
.. |license| image:: https://img.shields.io/pypi/l/django-latexify.svg?maxAge=2592000
   :target: https://github.com/ammsa/django-latexify/blob/master/LICENSE
   :alt: Software license
.. |website| image:: https://img.shields.io/website-up-down-green-red/http/shields.io.svg?maxAge=2592000
   :target: https://ammsa.github.io/django-latexify
.. |quality| image:: https://img.shields.io/codacy/grade/d8e71ce5a26248d892e96e35fdf1f7cf.svg?maxAge=2592000
   :target: https://www.codacy.com/app/ammsa7/django-latexify?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=AmmsA/django-latexify&amp;utm_campaign=Badge_Grade
.. |maintain| image:: https://img.shields.io/maintenance/yes/2023.svg
   :target: https://github.com/ammsa/django-latexify
.. |python3| image:: https://img.shields.io/badge/python3-yes-brightgreen.svg
   :target: https://github.com/ammsa/django-latexify
   :alt: Python 3 support
.. |python2| image:: https://img.shields.io/badge/python2-yes-brightgreen.svg
   :target: https://github.com/ammsa/django-latexify
   :alt: Python 2 support
