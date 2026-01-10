.. _scrollview:

Scroll View
============

.. rst-class:: lead

    The :class:`~carbonkivy.uix.scrollview.scrollview.CScrollView` class inherits from :class:`~kivy.uix.scrollview.ScrollView` and extends its functionality by introducing additional properties.

For instance, let's see an example of how :class:`~carbonkivy.uix.scrollview.scrollview.CScrollView` enhances control of `background color` compared to standard one.


.. tab-set::

    .. tab-item:: CarbonKivy

            .. code-block:: kv

                CScrollView:
                    bg_color: app.background_hover

    .. tab-item:: Kivy

            .. code-block:: kv

                ScrollView:
                    canvas.before:
                        Color:
                            rgba: app.background_hover
                        SmoothRectangle:
                            pos: self.pos
                            size: self.size

API
---

.. automodule:: carbonkivy.uix.scrollview.scrollview
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
