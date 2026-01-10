.. _themes:

Themes
======

.. rst-class:: lead

    Themes are used to customize component styles to fit the specific aesthetic of a brand or product.

Overview
--------

A theme is a collection of design tokens that define the visual style of components. These tokens include colors, typography, spacing, and other stylistic elements that can be applied consistently across a user interface.

The class :class:`carbonkivy.theme.theme.CarbonTheme` provides the necessary functionality to switch between different themes and apply the corresponding styles to components.


Available Themes
~~~~~~~~~~~~~~~~

Use the property :class:`carbonkivy.theme.theme.CarbonTheme.theme` to set or get the current theme. Changing the theme will automatically update the styles of all components that are using the theme.

- White
- Gray10
- Gray90
- Gray100

.. tab-set::

    .. tab-item:: White

        .. figure:: /_static/images/themes/color-overview-themes-white.png
            :alt: White
            :class: centered

    .. tab-item:: Gray10

            Under active development

        .. figure:: /_static/images/themes/color-overview-themes-gray10.png
            :alt: Gray10
            :class: centered

    .. tab-item:: Gray90

            Under active development

        .. figure:: /_static/images/themes/color-overview-themes-gray90.png
            :alt: Gray90
            :class: centered

    .. tab-item:: Gray100

        .. figure:: /_static/images/themes/color-overview-themes-gray100.png
            :alt: Gray100
            :class: centered

Disabling `defaults`
--------------------

By default, the theme sets the :class:`kivy.core.window.Window` background color to match the selected theme. If you want to manage the window background color yourself, you can disable this behavior by setting the :class:`carbonkivy.theme.theme.CarbonTheme.defaults` property to `False`.

Example
-------

By default your app inherits from :class:`carbonkivy.theme.theme.CarbonTheme` and uses the default `White` theme. To change the theme globally, you can set the theme property in your main app class like this:

.. code-block:: python

    ...

    from carbonkivy.app import CarbonApp

    class MyApp(CarbonApp):

        def __init__(self, *args, **kwargs) -> None:
            self.theme = "Gray100"  # Set the desired theme here so it loads before build
            super(MyApp, self).__init__(*args, **kwargs)

    ...

API
---

.. automodule:: carbonkivy.theme.theme
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
