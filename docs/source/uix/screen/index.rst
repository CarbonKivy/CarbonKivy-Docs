.. _screen:

Screen
======

.. rst-class:: lead

    The :class:`~carbonkivy.uix.screen.screen.CScreen` class inherits from :class:`~kivy.uix.screenmanager.Screen` and extends its functionality by introducing additional properties.

For instance, let's see an example of how :class:`~carbonkivy.uix.screen.screen.CScreen` enhances control of `background color` compared to standard one.


.. tab-set::

    .. tab-item:: CarbonKivy

            .. code-block:: kv

                CScreen:
                    bg_color: app.background_hover

    .. tab-item:: Kivy

            .. code-block:: kv

                Screen:
                    canvas.before:
                        Color:
                            rgba: app.background_hover
                        SmoothRectangle:
                            pos: self.pos
                            size: self.size

API
---

.. automodule:: carbonkivy.uix.screen.screen
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
