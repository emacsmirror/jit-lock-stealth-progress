##############################
JIT Font Lock Stealth Progress
##############################

This is a simple package that makes a progress variable available when using ``jit-lock-stealth``
(font locking while idle).

Available via `melpa <https://melpa.org/#/jit-lock-stealth-progress>`__.


Motivation
==========

With large files it's nice to have an indication when font locking has completed.


Usage
=====

Once enabled, progress for font locking will be displayed at the end of your mode-line (while it runs).

Stealthy Font Locking
---------------------

Emacs can be configured to compute syntax highlighting while idle.
To enable this functionality you must first set ``jit-lock-stealth-time`` to a number (in seconds).

You may set these values to something like this.

.. code-block:: elisp

   ;; Calculate fonts when idle for 1.5 seconds.
   (setq jit-lock-stealth-time 1.5)
   ;; Pause for 0.2 seconds between calculations afterwards.
   (setq jit-lock-stealth-nice 0.2)


Commands
--------

``jit-lock-stealth-progress-mode``
   Use this to toggle progress functionality.

Variables
---------

``jit-lock-stealth-progress-info``
   This is the main variable used to access the progress.
   This is a string, it's symbol can be used in ``mode-line-format``.


Customization
-------------

``jit-lock-stealth-progress-info-format``: ``"%5.1f%%"``
   Format string used to convert the progress floating point value into a string.

``jit-lock-stealth-progress-add-to-mode-line``: ``t``
   Add progress display to ``mode-line-format`` automatically.

   Users with a customized mode-line may prefer to manually include this in their ``mode-line-format``.
   This is a simple example of how ``jit-lock-stealth-progress-info`` can be manually added to your mode-line.

   .. code-block:: elisp

      (setq-default mode-line-format (append mode-line-format (list 'jit-lock-stealth-progress-info)))


Installation
============

This example shows how the package.

.. code-block:: elisp

   (use-package jit-lock-stealth-progress)
   (jit-lock-stealth-progress-mode)
