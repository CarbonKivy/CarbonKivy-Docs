.. _modal:

Modal
=====

.. rst-class:: lead

    Modals focus the user’s attention exclusively on one task or piece of information by using a window that is displayed on top of the page content.

Overview
--------

.. figure:: /_static/images/modal/carbondesignmodal.png
    :alt: Carbon Design Modal
    :class: centered

    Carbon Design Modal Overview

Modals are a type of dialog because it is a conversation between the user and the system. Use a modal to present critical information or request user input that’s needed to complete a user’s workflow. Modals interrupt a user’s workflow for short and non-frequent tasks, such as editing or management tasks. When the modal is open, the user is blocked from the on-page content and can’t return to their previous workflow until the modal task is completed or the user dismisses the modal. While effective when used correctly, modals should be used sparingly to limit disrupting the user. Therefore, if a user needs to repeatably perform a task, consider making the task completable on the main page.

Live demo
---------

.. note::

    This live demo contains only a preview of functionality and styles available for this component. Actual widgets may not show the exact same behavior but similar to expected.

.. tab-set::

    .. tab-item:: Default

        .. raw:: html

            <iframe title="Component demo" class="StorybookDemo-module--iframe--dc8d2" src="https://react.carbondesignsystem.com/iframe.html?id=components-modal--default&globals=theme:white" frameborder="no" sandbox="allow-forms allow-scripts allow-same-origin"></iframe>


        .. tab-set::

            .. tab-item:: Python

                .. code-block:: python

                    ...

                    from carbonkivy.app import CarbonApp
                    from carbonkivy.uix.modal import CModal


                    class DomainModal(CModal):
                        pass


                    class MyApp(CarbonApp) -> None:

                        def __init__(self, *args, **kwargs) -> None:
                            super(MyApp, self).__init__(*args, **kwargs)
                            self.modal = DomainModal()

                    ...

            .. tab-item:: Kvlang

                .. code-block:: kv

                    <DomainModal>:
                        CModalLayout:

                            CModalHeader:
                                CModalHeaderLabel:
                                    text: "Account resources"
                                CModalHeaderTitle:
                                    text: "Add a custom domain"

                            CModalBody:
                                CModalBodyContent:
                                    text: "Custom domains direct requests for your apps in this Cloud Foundry organization to a URL that you own. A custom domain can be a shared domain, a shared subdomain, or a shared domain and host."
                                
                                CBoxLayout:
                                    adaptive: [False, True]
                                    padding: [0, dp(64)]

                                    CTextInputLayout:
                                        CTextInput:
                                            hint_text: "e.g. bluemix.net"
                                        CTextInputLabel:
                                            text: "Domain name"

                            CModalFooter:
                                CGridLayout:
                                    cols: 2
                                    adaptive: [False, True]
                                    spacing: dp(1)

                                    CButtonSecondary:
                                        text: "Cancel"
                                        role: "Extra Large"
                                        size_hint_x: 1

                                    CButtonPrimary:
                                        text: "Add"
                                        role: "Extra Large"
                                        size_hint_x: 1

                        CModalCloseButton:

Example
-------

.. seealso::

    `Carbon Design Modal Example <https://github.com/CarbonKivy/CarbonKivy/tree/master/examples/Modal>`_

API
---

.. automodule:: carbonkivy.uix.modal.modal
    :members:
    :undoc-members:
    :show-inheritance:
    :no-index:
