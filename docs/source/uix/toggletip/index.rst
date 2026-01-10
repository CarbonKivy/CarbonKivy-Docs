.. _toggletip:

Toggletip
==========

.. rst-class:: lead

    Toggletips display and hide additional information upon the click of a UI trigger element. Toggletips can contain interactive elements.

Overview
--------

.. figure:: /_static/images/toggletip/carbondesigntoggletip.png
    :class: centered
    :alt: Carbon Design Toggletip Overview

    Carbon Design Toggletip Overview

Toggletips reveal supplemental content when a user clicks a button and remains actively open until a user dismisses it. A toggletip is comprised of a UI trigger and toggletip content (based on the popover component). Toggletips can include a wide variety of information and interactive elements as long as accessibility requirements are maintained, including focus order and ensuring all functionality is operable through a keyboard interface.

*Only vertical variant of CToggletip is available.*

Live demo
---------

Live demo
---------

.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Default

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-toggletip--default&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>

        .. code-block:: python

            ...

            from kivy.metrics import dp
            from kivy.properties import StringProperty
            from carbonkivy.behaviors import TooltipBehavior
            from carbonkivy.uix.link import CLink
            from carbonkivy.uix.tooltip import CToggletip


            class MyToggletip(CToggletip):

                text = StringProperty()


            class ToggletipLink(CLink, TooltipBehavior):

                def __init__(self, **kwargs) -> None:
                    super().__init__(**kwargs)
                    self.tooltip = MyToggletip(
                        text="Occasionally, services are updated in a specified time window to ensure no down time for customers."
                        width=dp(288),
                        margin=dp(2),
                        pointer="Upward"
                    )

            kvlang = """
            CScreen:
                ToggletipLink:
                    pos_hint: {"center_x": 0.5, "center_y": 0.5}

                    CLinkText:
                        text: "Toggletip Label"

                    CLinkIcon:
                        icon: "help"

            <MyToggletip>:
                CLabel:
                    text: root.text
                    color: app.text_inverse

                CButtonPrimary:
                    text: "View more"
                    role: "Large Productive"
            """

            ...

Usage
-----

For embedding a toggletip to any widget, the widget needs to inherit from the :class:`~carbonkivy.behaviors.tooltip_behavior.TooltipBehavior` class and then define a toggletip widget inheriting from :class:`~carbonkivy.uix.toggletip.toggletip.CTooltip` class.

Use the :class:`~carbonkivy.behaviors.tooltip_behavior.TooltipBehavior.tooltip` property to define the widget to be displayed as a toggletip.

.. note::

    On DESKTOP platforms, the toggletip will appear if hovered over the widget, by default.
    For this the widget should be an instance of the class :class:`~carbonkivy.behaviors.hover_behavior.HoverBehavior`.

.. code-block:: python

    ...

    from carbonkivy.behaviors import TooltipBehavior
    from carbonkivy.uix.toggletip import CToggletip

    from carbonkivy.uix.button import CButtonPrimary


    class MyToggletip(CToggletip):

        text = StringProperty()


    class ToggletipButton(CButtonPrimary, TooltipBehavior):

        def __init__(self, **kwargs) -> None:
            super().__init__(**kwargs)
            self.tooltip = MyToggletip(text="This is a Toggletip.")

    kvlang = """
    CScreen:
        ToggletipButton:
            text: "Drag Me!"
            icon: "add--large"
            pos: [30, 30]

    <MyToggletip>:
        CLabel:
            text: root.text
            color: app.text_inverse
    """

    ...

Example
-------

.. code-block:: python

    from kivy.clock import Clock
    from kivy.core.window import Window
    from kivy.properties import StringProperty


    def set_softinput(*args) -> None:
        Window.keyboard_anim_args = {"d": 0.2, "t": "in_out_expo"}
        Window.softinput_mode = "below_target"


    Window.on_restore(Clock.schedule_once(set_softinput, 0.1))

    appkv = """
    CScreen:

        ToggletipButton:
            text: "Drag Me"
            icon: "add--large"
            pos: [dp(30), dp(30)]

    <MToggletip>:
        CLabel:
            text: root.text
            color: app.text_inverse
        
        CButtonPrimary:
            text: "View more"
            role: "Large Productive"
    """

    from kivy.input.providers.mouse import MouseMotionEvent
    from kivy.lang import Builder
    from kivy.metrics import dp
    from kivy.properties import StringProperty

    from carbonkivy.app import CarbonApp
    from carbonkivy.behaviors import ElevationBehavior, TooltipBehavior
    from carbonkivy.uix.button import CButtonPrimary
    from carbonkivy.uix.screen import CScreen
    from carbonkivy.uix.toggletip import CToggletip


    class MToggletip(CToggletip):

        text = StringProperty()


    class ToggletipButton(CButtonPrimary, ElevationBehavior, TooltipBehavior):

        def __init__(self, **kwargs) -> None:
            super().__init__(**kwargs)
            self.tooltip = MToggletip(
                text="This is a large Toggletip text.",
                width=dp(288),
                margin=dp(2),
                pointer="Upward",
            )

        def on_touch_move(self, touch: MouseMotionEvent, *args) -> bool | None:
            self.center_x, self.center_y = touch.pos
            return super().on_touch_move(touch)

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

.. automodule:: carbonkivy.uix.toggletip.toggletip
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
