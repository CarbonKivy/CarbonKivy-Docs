.. _screenmanager:

Screen Manager
==============

.. rst-class:: lead

    The :class:`~carbonkivy.uix.screenmanager.screenmanager.CScreenManager` class inherits from :class:`~kivy.uix.screenmanager.ScreenManager` and extends its functionality by introducing additional properties.

For instance, let's see an example of how :class:`~carbonkivy.uix.screenmanager.screenmanager.CScreenManager` enhances control of `background color` compared to standard one.


.. tab-set::

    .. tab-item:: CarbonKivy

            .. code-block:: kv

                CScreenManager:
                    bg_color: app.background_hover

    .. tab-item:: Kivy

            .. code-block:: kv

                ScreenManager:
                    canvas.before:
                        Color:
                            rgba: app.background_hover
                        SmoothRectangle:
                            pos: self.pos
                            size: self.size

API
---

.. automodule:: carbonkivy.uix.screenmanager.screenmanager
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
