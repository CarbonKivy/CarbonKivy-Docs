.. _checkbox:

Checkbox
========

.. rst-class:: lead

    Checkboxes are used when there are multiple items to select in a list. Users can select zero, one, or any number of items.

Overview
--------
.. figure:: /_static/images/checkbox/checkbox.png
    :alt: Carbon Design Checkbox
    :class: centered

    Carbon Design Checkbox Overview

Checkboxes are used for multiple choices, not for mutually exclusive choices. Each checkbox works independently from other checkboxes in the list, therefore checking an additional box does not affect any other selections.

Live demo
---------

.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Multiple Checkbox

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-checkbox--default&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>

        .. code-block:: kv

            CBoxLayout:
                adaptive: [True, True]
                padding: dp(16)
                spacing: dp(8)
                orientation: "vertical"

                CLabel:
                    text: "Group label"
                    style: "label_01"
                    color: app.text_secondary

                CBoxLayout:
                    adaptive: [True, True]
                    spacing: dp(8)

                    CCheckbox:
                        line_width: dp(0.5)

                    CLabel:
                        size_hint: None, None
                        size: self.texture_size
                        text_size: None, self.texture_size[1]
                        text: "Checkbox label"
                        pos_hint: {"center_y": 0.5}
                
                CBoxLayout:
                    adaptive: [True, True]
                    spacing: dp(8)

                    CCheckbox:
                        line_width: dp(0.5)

                    CLabel:
                        size_hint: None, None
                        size: self.texture_size
                        text_size: None, self.texture_size[1]
                        text: "Checkbox label"
                        pos_hint: {"center_y": 0.5}

                CLabel:
                    text: "Helper text goes here"
                    style: "label_01"
                    color: app.text_secondary

Example
-------

.. seealso::

    `Checkbox eample <https://github.com/CarbonKivy/CarbonKivy/tree/master/examples/Checkbox>`_

API
---

.. automodule:: carbonkivy.uix.checkbox.checkbox
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
