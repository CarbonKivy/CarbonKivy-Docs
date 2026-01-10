.. _datepicker:

Date picker
-----------

.. rst-class:: lead

    Date and time pickers allow users to select a single instance or range of dates and times.

Overview
--------

.. figure:: /_static/images/datepicker/datepicker.png
    :class: centered
    :alt: Carbon Design Date Picker Overview

    Carbon Design Date Picker Overview

Date pickers allow users to select past, present, or future dates. The kind of date you are requesting from the user will determine which date picker (simple or calendar) is best to use.

Live demo
---------

.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Single with Calendar

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-datepicker--single-with-calendar&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>

        .. code-block:: python

            ...

            from carbonkivy.app import CarbonApp
            from carbonkivy.uix.datepicker import CDatePicker


            class CustomDatePicker(CDatePicker):

                def __init__(self, **kwargs) -> None:
                    super(CustomDatePicker, self).__init__(**kwargs)

                def on_selected_date(self, instance, value) -> None:
                    self.visibility = False


            class MyApp(CarbonApp):

                def __init__(self, *args, **kwargs) -> None:
                    super(MyApp, self).__init__(*args, **kwargs)
                    self.datepicker = CustomDatePicker()

            kvlang = """
            CScreen:

                CStackLayout:
                    size_hint: [1, 1]
                    padding: dp(16)

                    CBoxLayout:
                        adaptive: [False, True]
                        orientation: "vertical"
                        padding: [0, dp(32)]

                        CTextInputLayout:
                            id: datepicker_input

                            CTextInput:
                                id: datepicker_textinput
                                readonly: True
                                text: app.datepicker.selected_date.strftime("%d/%m/%y") if app.datepicker.selected_date else ""
                                hint_text: "mm/dd/yy"

                            CTextInputTrailingIconButton:
                                icon: "calendar"
                                line_color_focus: app.transparent
                                on_press:
                                    app.datepicker.master = datepicker_textinput
                                    app.datepicker.visibility = True

            <CustomDatePicker>:
                shadow_color: [0, 0, 0, 0.2]
            """

            ...

Example
-------

.. seealso::

    `Carbon Design Date Picker <https://github.com/CarbonKivy/CarbonKivy/tree/master/examples/DatePicker>`_

API
---

.. automodule:: carbonkivy.uix.datepicker.datepicker
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
