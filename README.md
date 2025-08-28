
## Mode-line maker

mode-line-maker is a package to ease the creation of mode-line,
header-line or tab-line. It allows to define the precise alignment
of the mode-line (on left and right) and splits the mode-line into
left and right parts, with automatic truncation (when there is too
much information to display).

## Usage

```emacs-lisp
(require 'mode-line-maker)
(setq mode-line-format (mode-line-maker '("%b")
                                        '("%3c:%3l")))
```
