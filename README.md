# cmake-format.el

Format your CMake scripts from inside emacs, using the python command line tool [`cmake-format`](https://github.com/cheshirekow/cmake_format).

## Installation

- Install the [`cmake-format`](https://github.com/cheshirekow/cmake_format) command line program. You can use pip:
```sh
$ pip install --user cmake-format
```
- Put `cmake-format.el` in your `load-path`.

## Configuration

Make sure that either cmake-format can be found in your `$PATH` or explicitly
set `cmake-format-command`. After `cmake-format` is loaded you can invoke
`cmake-format-buffer` to format the current buffer. To do it everytime you save
your buffer the minor mode `cmake-format-mode`.

### Example configuration

```elisp
(defun my-cmake-mode-hook ()
  (cmake-format-mode 1))

(use-package cmake-format
  :init
  ;; optional: enable automatic formatting on save
  (add-hook 'cmake-mode-hook #'my-cmake-mode-hook)
  :config
  ;; optional:
  (setq cmake-format-command "/path/to/cmake-format"
        cmake-format-args '("list" "of" "flags")))
```
