
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

## Alignment

Mode-line alignment controls the extent of the mode-line relatively to
window, margins, fringes or text:

```
fringes-outside-margins t
   ┌───┬────────┬───────────────────────────────────────┬────────┬───┬───┐
   │                         'window alignment                           │
   └───┴────────┴───────────────────────────────────────┴────────┴───┴───┘
   ┌───┬────────┬───────────────────────────────────────┬────────┬───┐
   │                         'fringe alignment                       │
   └───┴────────┴───────────────────────────────────────┴────────┴───┘
       ┌────────┬───────────────────────────────────────┬────────┐
       │                     'margin alignment                   │
       └────────┴───────────────────────────────────────┴────────┘
                ┌───────────────────────────────────────┐
                │             'text alignment           │
                └───────────────────────────────────────┘
   ┌───┬────────┬───────────────────────────────────────┬────────┬───┬───┐
   │   │        │                                       │        │   │   │
   │ • │    •   │               Text area               │   •    │ • │ • │
   │ │ │    │   │                                       │   │    │ │ │ │ │
   └─┼─┴────┼───┴───────────────────────────────────────┴───┼────┴─┼─┴─┼─┘
     │ Left margin                                    Right margin │   │
   Left fringe                                            Right fringe │
                                                                Scroll bar

fringes-outside-margins nil
   ┌───┬────────┬───────────────────────────────────────┬────────┬───┬───┐
   │                         'window alignment                           │
   └───┴────────┴───────────────────────────────────────┴────────┴───┴───┘
   ┌────────┬───┬───────────────────────────────────────┬───┬────────┐
   │                         'margin alignment                       │
   └────────┴───┴───────────────────────────────────────┴───┴────────┘
            ┌───┬───────────────────────────────────────┬───┐
            │                'fringe alignment              │
            └───┴───────────────────────────────────────┴───┘
                ┌───────────────────────────────────────┐
                │             'text alignment           │
                └───────────────────────────────────────┘
   ┌────────┬───┬───────────────────────────────────────┬───┬────────┬───┐
   │        │   │                                       │   │        │   │
   │   •    │ • │               Text area               │ • │    •   │ • │
   │   │    │ │ │                                       │ │ │    │   │ │ │
   └───┼────┴─┼─┴───────────────────────────────────────┴─┼─┴────┼───┴─┼─┘
       │ Left fringe                                Right fringe │     │
    Left margin                                           Right margin │
                                                               Scroll bar
```
