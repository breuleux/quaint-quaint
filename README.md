
# quaint-quaint

Interactive Quaint textboxes in Quaint documents.

`quaint-quaint` will automatically start a Quaint interpreter
listening to changes to one or more textareas and running in a
separate Worker. For each marked `textarea`, an output `div` is
created and will be updated automatically with the result of the
compilation of the current contents.

`quaint-quaint` does not define a stylesheet, but it should not be
very complicated to style. See below for the generated HTML.


## Install

    npm install quaint-quaint -g


## Sample use

```quaint
Edit this:

&&
  Quaint is __awesome!
  # One
  # Two
  # Three

Ten-lines-high uninitialized editor:

10 &&
```

The generated code will look like this:

```html
<div class="quaint-interactive">
  <div class="quaint-input">
    <textarea rows="10">
      Quaint is __awesome
    </textarea>
  </div>
  <div class="quaint-output">
    Quaint is <strong>awesome</strong>
  </div>
</div>
```

`quaint-quaint` does not contribute any stylesheet, so you will need
to style the above yourself.


## Rules

### `nrows && body`

Creates an interactive Quaint editor initialized with `body`, and with
`nrows` rows of text. If `nrows` is unspecified, then the number of
lines in `body` will be used (line wrapping is not taken into
account).


## Options

### `preCompute`

(default: true)

If `true`, Quaint will pre-compute the result of every interactive
editor. That's kind of slow, so you can flip that off if needed, while
developing.
