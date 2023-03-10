# Getting started

**Installation**:
- Installation with pip:
    ```sh
    $ pip install colorer
    ```

- Installation with git:
    ```sh
    $ git clone https://github.com/ALhorm/colorer.git
    $ cd colorer
    $ python setup.py install
    ```

# Usage

<b>Colorer</b> uses <i>ANSI Escape Sequences</i> for line coloring and supports both color schemes (16 and 256 colors). The description of the text style is set in the line where your text is written. It is important to note that more than one coloring cannot be used for one line. Let's take a look at an example:

```py
from colorer import string

text = string("(( style=bold, fore=green, back=purple )) This is test text", True)

print(text)
```

In this example, the colorer will make the text <b>bold</b>, the text itself will be <b>green</b>, and the background <b>purple</b>. Also, the second parameter, which in this example is set to <b>True</b>, is responsible for removing extra spaces in the text. If it is equal to <b>False</b>, the spaces between the text and the description of the style of this text will be remained, and if the parameter is equal to <b>True</b>, the spaces will be removed. In this case, the entire line will be changed. But you can also color only part of the string:

```py
from colorer import string

text = string("This (( style=italic, fore=yellow, back=none )) is test (( end )) text", True)

print(text)
```

In this example, only part of the text will be colored, namely "<b>is test</b>". The text style will be italic, the text color will be <b>yellow</b>, and the <b>background will remain standard</b>, the word <b>none</b> is responsible for this, which is also available for the fore parameter. And if you want to leave the text style as default, you should set the style parameter to <b>normal</b>. All possible parameter values are shown below:

```py
style = [
  "normal", # standard text
  "bold", # bold text
  "light", # thin text
  "italic", # italic text
  "underlined", # text with underscore
  "blink" # blink text
]

fore = [
  "black",
  "red",
  "green",
  "yellow",
  "blue",
  "purple",
  "cyan",
  "white",
  "none",
  "1-256" # color in numbers, from 1 to 256 (inclusive)
]

back = "same values as fore"
```

As you already understood, the value of the fore and back parameters can be set in <b>numbers</b> (<b>from 1 to 256</b>). It is important to note that only one parameter, either fore or back, can be set in numbers. Moreover, only the parameter to which you set the value in numbers will work.

```py
from colorer import string

text = string("This (( style=underlined, fore=none, back=187 )) is test text", True)

print(text)
```

In this example, we will change the "<b>is test text</b>" part of the string. Namely, we will change the style to <b>underlined</b>, and the background to color <b>187 of the 256 color scheme</b>. This entire scheme is shown below:

<img src="https://raw.githubusercontent.com/ALhorm/colorer/master/img/colors.jpg" alt="256 color scheme">

It is also worth noting that it is not necessary to write text styles, as shown in the example. If you write like this:

```py
text = string("This ((STylE = NORMAL, FORE=none, BaCK=85)) is test ((eNd)) text", True)
```

then nothing will change. But I recommend that you write beautifully, as shown in the previous examples.

# Thank you

Thank you for using the <b>colorer</b> library!
