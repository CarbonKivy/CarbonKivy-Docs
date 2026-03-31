.. _radio:

Radio button
============

.. rst-class:: lead

    Use radio buttons when you have a group of mutually exclusive choices and only one selection from the group is allowed.

Overview
--------

.. figure:: /_static/images/radio/radio-overview.png
    :class: centered

Radio buttons are used for mutually exclusive choices, not for multiple choices. Only one radio button can be selected at a time. When a user chooses a new item, the previous choice is automatically deselected.

Live demo
---------


.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Default

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-radiobutton--default&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>

        .. code-block:: kv

            CScreen:

                CRadioGroupLayout:
                    pos_hint: {"center_x": 0.5, "center_y": 0.5}

                    CRadioGroupLabel:
                        text: "Radio button group"

                    CRadioGroupHelperText:
                        text: "Helper text"

                    CRadioGroup:
                        id: group_master
                        pos_hint: {"center_x": 0.5, "center_y": 0.5}
                        size_hint_x: None
                        width: dp(256)

                        CRadioItem:

                            CRadioButton:
                                pos_hint: {"center_y": 0.5}
                                group_master: group_master

                            CRadioButtonLabel:
                                text: "Radio button label"
                                pos_hint: {"center_y": 0.5}

                        CRadioItem:

                            CRadioButton:
                                pos_hint: {"center_y": 0.5}
                                group_master: group_master

                            CRadioButtonLabel:
                                text: "Radio button label"
                                pos_hint: {"center_y": 0.5}

                        CRadioItem:

                            CRadioButton:
                                pos_hint: {"center_y": 0.5}
                                group_master: group_master

                            CRadioButtonLabel:
                                text: "Radio button label"
                                pos_hint: {"center_y": 0.5}

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

    from webview import WebView, prewarm_webview


    def set_softinput(*args) -> None:
        Window.keyboard_anim_args = {"d": 0.2, "t": "in_out_expo"}
        Window.softinput_mode = "below_target"


    Window.on_restore(Clock.schedule_once(set_softinput, 0.1))

    appkv = """
    CScreen:

        CRadioGroupLayout:
            pos_hint: {"center_x": 0.5, "center_y": 0.5}

            CRadioGroupLabel:
                text: "Radio button group"

            CRadioGroupHelperText:
                text: "Helper text"

            CRadioGroup:
                id: group_master
                pos_hint: {"center_x": 0.5, "center_y": 0.5}
                size_hint_x: None
                width: dp(256)

                CRadioItem:

                    CRadioButton:
                        pos_hint: {"center_y": 0.5}
                        group_master: group_master

                    CRadioButtonLabel:
                        text: "Radio button label"
                        pos_hint: {"center_y": 0.5}

                CRadioItem:

                    CRadioButton:
                        pos_hint: {"center_y": 0.5}
                        group_master: group_master

                    CRadioButtonLabel:
                        text: "Radio button label"
                        pos_hint: {"center_y": 0.5}

                CRadioItem:

                    CRadioButton:
                        pos_hint: {"center_y": 0.5}
                        group_master: group_master

                    CRadioButtonLabel:
                        text: "Radio button label"
                        pos_hint: {"center_y": 0.5}
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

.. automodule:: carbonkivy.uix.radio.radio
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
