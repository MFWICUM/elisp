#+meta: C-c C-v C-b
#+start using gdb.
#+C-h m "Babel"

* LEXICONSEX [ ]
** /SPECIAL-FORMS/ 
   - Note taken on [2023-01-04 Wed 23:11] \\
     Common Lisp note: Here are some comparisons of special forms in GNU
          Emacs Lisp and Common Lisp.  ‘setq’, ‘if’, and ‘catch’ are special
          forms in both Emacs Lisp and Common Lisp.  ‘save-excursion’ is a
          special form in Emacs Lisp, but doesn’t exist in Common Lisp.
          ‘throw’ is a special form in Common Lisp (because it must be able
          to throw multiple values), but it is a function in Emacs Lisp
          (which doesn’t have multiple values).
   - Note taken on [2023-01-04 Wed 22:42] \\
     10.2.7 Special Forms
     --------------------
     
     A “special form” is a primitive function specially marked so that its
     arguments are not all evaluated.  Most special forms define control
     structures or perform variable bindings—things which functions cannot
     do.
     
        Each special form has its own rules for which arguments are evaluated
     and which are used without evaluation.  Whether a particular argument is
     evaluated may depend on the results of evaluating other arguments.
     
        If an expression’s first symbol is that of a special form, the
     expression should follow the rules of that special form; otherwise,
     Emacs’s behavior is not well-defined (though it will not crash).  For
     example, ‘((lambda (x) x . 3) 4)’ contains a subexpression that begins
     with ‘lambda’ but is not a well-formed ‘lambda’ expression, so Emacs may
     signal an error, or may return 3 or 4 or ‘nil’, or may behave in other
     ways.
     
      -- Function: special-form-p object
          This predicate tests whether its argument is a special form, and
          returns ‘t’ if so, ‘nil’ otherwise.
     
        Here is a list, in alphabetical order, of all of the special forms in
        Emacs Lisp with a reference to where each is described.
     
#+begin_src elisp 'SIGNATURE_LIST OF ALL SPECIAL-FORMS' 
(save-current-buffer
(save-restriction
(unwind-protect
(save-excursion
(condition-case
(setq-default
(interactive
(function
(defconst
(lambda
(defvar SYMBOL &optional INITVALUE DOCSTRING)
(quote
(catch
(while
(progn
(prog2
(prog1
(cond 
(setq
(and
(let*
(let
(or
(if
#+end_src

#+begin_src elisp 'defvar-examples'
(defvar ...

(defvar ... ;V2

(defvar ... ;V3
#+end_src

#+begin_src elisp 'random-examples'
(random ...

(random ... ;V2

(random ... ;V3
#+end_src

#+begin_src elisp 'random-examples'
(random ...

(random ... ;V2

(random ... ;V3
#+end_src

** /NOT-A-SPECIAL-FORM/

** /RANDOM-FORM/




* PROGRAMS [ ]
** HELLO-GOYIM [ BRUNCH ]
#+name: hello-goyim [ V1 ]
#+begin_src elisp :exports both 
(princ "hello goyim")
#+end_src

#+name: hello-goyim [ V2 ]
#+begin_src elisp :exports both 
;; defun "a" = "goyim" & princ a = "goyim" 
(defun a "Goyim" (princ "Goyim"))
#+end_src

