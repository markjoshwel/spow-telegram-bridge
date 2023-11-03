# surplus on wheels: telegram bridge

telegram bridge for
[surplus on wheels (s+ow)](https://github.com/markjoshwel/surplus#on-termux-surplus-on-wheels).

s+ow bridges are defined in a file named `$HOME/.s+ow-bridges`. each command in the file is
ran, and comma-seperated target chat IDs are passed using stdin.

this bridge recognises targets prefixed with `tg:`.

```text
tg:<chat id>,...
```

to use the telegram bridge:

1. install [surplus](https://github.com/markjoshwel/surplus), mdtest and surplus on wheels

2. install git if not installed:

   ```text
   pkg install git
   ```

3. install spow-telegram-bridge with pip or pipx:

   ```text
   pip install git+https://github.com/markjoshwel/spow-telegram-bridge
   ```

4. add the following to your `$HOME/.s+ow-bridges` file:

   ```text
   s+ow-telegram-bridge
   ```

usage:

- `s+ow-telegram-bridge`  
  normal usage; sends latest message to `tg:`-prefixed targets given in stdin
- `s+ow-telegram-bridge login`  
  sends latest message to `tg:`-prefixed targets given in stdin, silently
- `s+ow-telegram-bridge list`  
  lists all chats and their IDs

optional arguments:

- `--silent`  
  send message silently
- `--daily-message`  
  send as a daily message from noon that edits itself until next noon

## licence

the s+ow telegram bridge is free and unencumbered software released into the public
domain. for more information, please refer to the [UNLICENCE](/UNLICENCE),
<https://unlicense.org>, or the python module docstring.
