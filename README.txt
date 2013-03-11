Thorsten Jolitz


Table of Contents
_________________

1 outxxtra.el --- Org-style outline navigation and structure editing
.. 1.1 Copyright
.. 1.2 Licence
.. 1.3 Credits
.. 1.4 Commentary
.. 1.5 Emacs Version
.. 1.6 Installation
.. 1.7 ChangeLog
.. 1.8 Bugs and Shortcomings


1 outxxtra.el --- Org-style outline navigation and structure editing
====================================================================

1.1 Copyright
~~~~~~~~~~~~~

  Copyright (C) 2013 Thorsten Jolitz

  Author(s): Thorsten Jolitz, Per Abrahamsen
  Maintainer: Thorsten Jolitz  <tjolitz AT gmail DOT com>
  Version: 0.9
  Created: 11th February 2013
  Keywords: occur, outlines, navigation


1.2 Licence
~~~~~~~~~~~

  This file is NOT (yet) part of GNU Emacs.

  This program is free software; you can redistribute it and/or modify
  it under the terms of the GNU General Public License as published by
  the Free Software Foundation, either version 3 of the License, or (at
  your option) any later version.

  This program is distributed in the hope that it will be useful, but
  WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
  General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with this program. If not, see [http://www.gnu.org/licenses/].


1.3 Credits
~~~~~~~~~~~

  This library is based on, or rather an extension of, Per Abrahamsen's
  'out-xtra.el' ([http://tinyurl.com/aql9p97]), and may replace it many
  cases. Some new ideas were taken from Fabrice Niessen's '.emacs'
  ([http://www.mygooglest.com/fni/dot-emacs.html#sec-2]).


1.4 Commentary
~~~~~~~~~~~~~~

  [This file is OBSOLETE and has been merged into `outshine.el'. If you
  are interested in 'outline-magic', `out-xtra' and `outxxtra', use
  `outshine' instead - it merges all the mentioned libraries]

  This library provides (almost) the same nice extra features for
  outline minor mode like Per Abrahamsen's 'out-xtra':

  - Change default minor mode key prefix to `C-c'.
  - Complete keybindings and menu support.
  - Add command to show top level headers.
  - Add command to hide all other entries than the one containing point.

  `outxxtra' follows a different idea than `out-xtra': it consists of
  generic functionality that that calculates the adequate outline-regexp
  and outline-level for the active major-mode, rather than defining
  several blocks of major-mode specific functionality.

  New features of `outxxtra' are:

  1. Generic functionality that should work whereever `comment-region'
     and  `uncomment-region' work.

  2. Fontification of headlines (copied from Fabrice Niessen's
     '.emacs')

  It is highly recommended to use `outxxtra' together with
  `outline-magic' for the Org-style `outline-cycle' command.


1.5 Emacs Version
~~~~~~~~~~~~~~~~~

  `outxxtra.el' works with [GNU Emacs 24.2.1 (x86_64-unknown-linux-gnu,
  GTK+ Version 3.6.4) of 2013-01-20 on eric]. No attempts of testing
  with older versions or other types of Emacs have be made (yet).


1.6 Installation
~~~~~~~~~~~~~~~~

  Insert

  #+begin_src emacs-lisp
   (require 'outxxtra)
  #+end_src

  in your .emacs file to install. If you want a different prefix key,
  insert first

  #+begin_src emacs-lisp
   (defvar outline-minor-mode-prefix "\C-c")
  #+end_src

  or whatever. The prefix can only be changed before outline (minor)
  mode is loaded.


1.7 ChangeLog
~~~~~~~~~~~~~

   date             author(s)        version 
  -------------------------------------------------
   2013-02-11 Mo   Thorsten Jolitz      0.9 


1.8 Bugs and Shortcomings
~~~~~~~~~~~~~~~~~~~~~~~~~

  `outxxtra' uses a fixed format `outline-regexp' (and `outline-level'),
  the one produced when applying `comment-region' on an Org-mode style
  headline in the active programming-language major-mode (e.g. ';; **
  Entry' in an Emacs Lisp buffer, or '## ** Entry' in an PicoLisp
  buffer).

  This could be made more flexible (and customizable), albeit at the
  price that `outorg.el' would not work anymore with `outxxtra'. And -
  these Org-style headers look good, why change them?
