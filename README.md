# Maude Mode for XEmacs

This is version 0.2 of an XEmacs major mode for the Maude language. 
It provides syntax-highlighting, calling Maude in a buffer, 
commenting/uncommenting regions, and auto-indentation.

New in version 0.2 is syntax highlighting in the buffer
that is running Maude and a different handling of calls to Maude:
C-c C-m calls Maude,
C-c C-f calls Full-Maude and
C-c C-c copies the current buffer to Maude.


At the time of writing, this mode did *not* work with GNU Emacs since
GNU Emacs didn't support nongreedy quantifiers in regular expressions. (It might now.)

To install: Once you have untared maude-mode.tar.gz in your
home directory you will find all the files in ~/MaudeMode/ .
Now just add the following lines to your ~/.emacs:

```lisp
;; ------------------- Maude mode

(setq load-path (cons "~/MaudeMode" load-path))
(setq auto-mode-alist (cons '("\\.maude" . maude-mode) auto-mode-alist))
(defvar maude-cmd "~/Maude/maude-linux/bin/maude.linux"
"Defines the command line to call the Maude engine")

(require 'maude-mode)

;; -------------------


Adapt the maude-cmd to your environment.    

Just load a Maude file in XEmacs. Syntax highlighting should be 
automatic, if not, turn it on under 
Options->Syntax Highlighting->In this Buffer .

To change colors, see  
Options->Customize->Faces->Font Lock Faces .

You can comment/uncomment regions using C-c c / C-c u .
To run Maude press C-c C-m . To load the current buffer, 
press C-c C-c. This will also save your file. 


