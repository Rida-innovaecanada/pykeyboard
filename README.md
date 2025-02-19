<div align="center">
<p align="center">
<img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/logo.png" alt="pykeyboard">
</p>

![PyPI](https://img.shields.io/pypi/v/pykeyboard)
[![Downloads](https://pepy.tech/badge/pykeyboard)](https://pepy.tech/project/pykeyboard)
![GitHub](https://img.shields.io/github/license/pystorage/pykeyboard)

</div>

# Pykeyboard

- [<b>What's new?</b>](#whats-new)
- [<b>Installation</b>](#installation)
- [<b>Documentation</b>](#documentation)
  - [<b>Inline Keyboard</b>](#inline-keyboard)
    - [Inline Keyboard add buttons](#inline-keyboard-add-buttons)
    - [Inline Keyboard row buttons](#inline-keyboard-row-buttons)
    - [<b>Pagination inline keyboard</b>](#pagination-inline-keyboard)
      - [Pagination 3 pages](#pagination-3-pages)
      - [Pagination 5 pages](#pagination-5-pages)
      - [Pagination 9 pages](#pagination-9-pages)
      - [Pagination 100 pages](#pagination-100-pages)
      - [Pagination 150 pages and buttons](#pagination-150-pages-and-buttons)
  - [<b>Reply Keyboard</b>](#reply-keyboard)
    - [Reply Keyboard add buttons](#reply-keyboard-add-buttons)
    - [Reply Keyboard row buttons](#reply-keyboard-row-buttons)

# What's new?

- Added a new method to <b>InlineKeyboard</b> for working with <ins>pagination</ins>. The <b>InlinePaginationKeyboard</b> class will be removed in a future version.

# Installation

```shell
pip install pykeyboard
```

# Documentation

## Inline Keyboard

```python
from pykeyboard import InlineKeyboard
```

##### Parameters:

- row_width (integer, default 3)

### Inline Keyboard add buttons

#### Code

```python
from pykeyboard import InlineKeyboard
from pyrogram.types import InlineKeyboardButton


keyboard = InlineKeyboard(row_width=3)
keyboard.add(
    InlineKeyboardButton('1', 'inline_keyboard#1'),
    InlineKeyboardButton('2', 'inline_keyboard#2'),
    InlineKeyboardButton('3', 'inline_keyboard#3'),
    InlineKeyboardButton('4', 'inline_keyboard#4'),
    InlineKeyboardButton('5', 'inline_keyboard#5'),
    InlineKeyboardButton('6', 'inline_keyboard#6'),
    InlineKeyboardButton('7', 'inline_keyboard#7')
)
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/add_inline_button.png" alt="add_inline_button"></p>

### Inline Keyboard row buttons

#### Code

```python
from pykeyboard import InlineKeyboard
from pyrogram.types import InlineKeyboardButton


keyboard = InlineKeyboard()
keyboard.row(InlineKeyboardButton('1', 'inline_keyboard#1'))
keyboard.row(
    InlineKeyboardButton('2', 'inline_keyboard#2'),
    InlineKeyboardButton('3', 'inline_keyboard#3')
)
keyboard.row(InlineKeyboardButton('4', 'inline_keyboard#4'))
keyboard.row(
    InlineKeyboardButton('5', 'inline_keyboard#5'),
    InlineKeyboardButton('6', 'inline_keyboard#6')
)
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/row_inline_button.png" alt="row_inline_button"></p>

### Pagination inline keyboard

```python
from pykeyboard import InlineKeyboard
```

#### Parameters:

- count_pages (integer)
- current_page (integer)
- callback_pattern (string) - use of the `{number}` pattern is <ins>required</ins>

#### Pagination 3 pages

#### Code

```python
from pykeyboard import InlineKeyboard

keyboard = InlineKeyboard()
keyboard.paginate(3, 3, 'pagination_keyboard#{number}')
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/pagination_keyboard_3.png" alt="pagination_keyboard_3"></p>

#### Pagination 5 pages

#### Code

```python
from pykeyboard import InlineKeyboard

keyboard = InlineKeyboard()
keyboard.paginate(5, 3, 'pagination_keyboard#{number}')
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/pagination_keyboard_5.png" alt="pagination_keyboard_5"></p>

#### Pagination 9 pages

#### Code

```python
from pykeyboard import InlineKeyboard

keyboard = InlineKeyboard()
keyboard.paginate(9, 5, 'pagination_keyboard#{number}')
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/pagination_keyboard_9.png" alt="pagination_keyboard_9"></p>

#### Pagination 100 pages

#### Code

```python
from pykeyboard import InlineKeyboard

keyboard = InlineKeyboard()
keyboard.paginate(100, 100, 'pagination_keyboard#{number}')
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/pagination_keyboard_100.png" alt="pagination_keyboard_100"></p>

#### Pagination 150 pages and buttons

#### Code

```python
from pykeyboard import InlineKeyboard
from pyrogram.types import InlineKeyboardButton

keyboard = InlineKeyboard()
keyboard.paginate(150, 123, 'pagination_keyboard#{number}')
keyboard.row(
    InlineKeyboardButton('Back', 'pagination_keyboard#back'),
    InlineKeyboardButton('Close', 'pagination_keyboard#close')
)
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/pagination_keyboard_150.png" alt="pagination_keyboard_150"></p>

## Reply Keyboard

```python
from pykeyboard import ReplyKeyboard
```

#### Parameters:

- resize_keyboard (bool, optional)
- one_time_keyboard (bool, optional)
- selective (bool, optional)
- row_width (integer, default 3)

### Reply Keyboard add buttons

#### Code

```python
from pykeyboard import ReplyKeyboard
from pyrogram.types import KeyboardButton


keyboard = ReplyKeyboard(row_width=3)
keyboard.add(
    KeyboardButton('1', 'reply_keyboard#1'),
    KeyboardButton('2', 'reply_keyboard#2'),
    KeyboardButton('3', 'reply_keyboard#3'),
    KeyboardButton('4', 'reply_keyboard#4'),
    KeyboardButton('5', 'reply_keyboard#5'),
)
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/add_reply_button.png" alt="add_reply_button"></p>

### Reply Keyboard row buttons

#### Code

```python
from pykeyboard import ReplyKeyboard
from pyrogram.types import KeyboardButton


keyboard = ReplyKeyboard()
keyboard.row(KeyboardButton('1', 'reply_keyboard#1'))
keyboard.row(
    KeyboardButton('2', 'reply_keyboard#2'),
    KeyboardButton('3', 'reply_keyboard#3')
)
keyboard.row(KeyboardButton('4', 'reply_keyboard#4'))
keyboard.row(KeyboardButton('5', 'reply_keyboard#5'))
```

#### Result

<p><img src="https://raw.githubusercontent.com/pystorage/pykeyboard/master/docs/source/images/row_reply_button.png" alt="row_reply_button"></p>
