.. _development-utilities:

Development Utilities
=====================

This module provides various utility functions and constants for CarbonKivy, including typography helpers, system UI modifiers for Android, and device type detection.

Functions
---------

.. function:: get_font_name(typeface: str, weight_style: str) -> str

   Constructs and returns the absolute file path for a specified IBM Plex font based on the provided typeface and weight style.

   :param typeface: The font family name (e.g., ``"IBM Plex Sans"``).
   :param weight_style: The specific weight and style (e.g., ``"Regular"``, ``"BoldItalic"``).
   :return: The formatted path string to the `.ttf` font file.

.. function:: get_font_style(token: str) -> float

   Retrieves the typography style value from the predefined design system tokens.

   :param token: The font style token name.
   :return: The corresponding font style float value.

.. function:: get_spacing(token: str) -> float

   Retrieves the spacing value from the predefined design system tokens.

   :param token: The spacing token name.
   :return: The corresponding spacing float value.

.. function:: get_button_size(token: str) -> float

   Retrieves the button size dimension from the predefined design system tokens.

   :param token: The button size token name.
   :return: The corresponding button size float value.

.. function:: get_latest_time(*args) -> str

   Returns the current local time formatted as a string.

   :return: The current time in ``%I:%M:%S %p`` format (e.g., ``05:18:37 PM``).

.. function:: update_system_ui(status_bar_color: list[float] | str, navigation_bar_color: list[float] | str, icon_style: Literal["Light", "Dark"] = "Dark", pad_status: bool = True, pad_nav: bool = False) -> None

   Updates the color system of the device's status and navigation bars. 
   
   *Note: Currently supports Android only. Uses Android WindowInsetsController internally for SDK 30+ and legacy UI flags for older versions.*

   :param status_bar_color: The background color for the status bar. Can be a hex string or an RGBA tuple.
   :param navigation_bar_color: The background color for the navigation bar. Can be a hex string or an RGBA tuple.
   :param icon_style: The style of the system icons. Accepts ``"Light"`` or ``"Dark"``. Defaults to ``"Dark"``.
   :param pad_status: Whether to apply top padding to accommodate the status bar. Defaults to ``True``.
   :param pad_nav: Whether to apply bottom padding to accommodate the navigation bar. Defaults to ``False``.

.. function:: get_display_cutout_insets() -> tuple[int, int]

   Retrieves the safe insets for display cutouts (notches/punch-holes) on Android devices.

   :return: A tuple containing the top and bottom safe insets ``(top, bottom)``. Returns ``(0, 0)`` if not on Android or if no cutout is present.

Classes
-------

.. class:: _Dict

   Implements access to dictionary values via dot notation. Inherits from ``kivy.properties.DictProperty``.

Constants
---------

.. data:: DEVICE_TYPE

   The detected type of the current device. Evaluates to ``"desktop"``, ``"tablet"``, or ``"mobile"`` based on the OS platform and Kivy Window dimensions. This can be manually overridden via the ``devicetype`` system environment variable.

.. data:: DEVICE_IOS

   A boolean flag indicating whether the current platform is an Apple operating system (``True`` if iOS or macOS, ``False`` otherwise).
