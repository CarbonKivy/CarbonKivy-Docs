.. _toggle:

Toggle
======

.. rst-class:: lead
    A toggle is used to quickly switch between two possible states. They are commonly used for “on/off” switches.

Overview
--------

.. figure:: /_static/images/toggle/toggle-overview.png
    :class: centered

Toggle is a control that is used to quickly switch between two possible states. Toggles are only used for these binary actions that occur immediately after the user “flips the switch”. They are commonly used for “on/off” switches.

Live demo
---------

.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Default

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-toggle--default&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>

        .. code-block:: kv

            CToggle:

Size
----
There are two available size tokens for a toggle:

- **Small**
- **Large**

Use the :class:`~carbonkivy.uix.toggle.toggle.CToggle.role` property to define the token for the toggle size.

.. code-block:: kv

    CToggle:
        role: "Small"

Example
-------

.. code-block:: python

    import os
    import sys

    from kivy.resources import resource_add_path

    sys.path.insert(0, os.path.dirname(__file__))
    resource_add_path(os.path.dirname(__file__))

    from kivy.clock import Clock
    from kivy.core.window import Window

    def set_softinput(*args) -> None:
        Window.keyboard_anim_args = {"d": 0.2, "t": "in_out_expo"}
        Window.softinput_mode = "below_target"


    Window.on_restore(Clock.schedule_once(set_softinput, 0.1))

    appkv = """
    CScreen:

        CToggle:
            pos_hint: {"center_x": 0.5, "center_y": 0.5}
    """

    from kivy.lang import Builder

    from carbonkivy.app import CarbonApp
    from carbonkivy.uix.screen import CScreen


    class myapp(CarbonApp):
        def __init__(self, *args, **kwargs):
            super(myapp, self).__init__(*args, **kwargs)

        def build(self) -> CScreen:
            screen = Builder.load_string(appkv)
            return screen


    if __name__ == "__main__":
        myapp().run()

API
---

.. automodule:: carbonkivy.uix.toggle.toggle
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
