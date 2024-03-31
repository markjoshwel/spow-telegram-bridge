# surplus on wheels: telegram bridge

Telegram bridge for
[surplus on wheels (s+ow)](https://github.com/markjoshwel/surplus#on-termux-surplus-on-wheels).

s+ow bridges are defined in a file named `$HOME/.s+ow-bridges`. each command in the file is
ran, and comma-seperated target chat IDs are passed using stdin.

this bridge recognises targets prefixed with `tg:`.

```text
tg:<chat id>,...
```

to use the Telegram bridge:

1. install [surplus](https://github.com/markjoshwel/surplus), and [surplus on wheels](https://github.com/markjoshwel/surplus-on-wheels)

2. install git if not installed:

   ```text
   pkg install git
   ```

3. install spow-telegram-bridge:

   ```text
   pipx install git+https://github.com/markjoshwel/spow-telegram-bridge
   ```

4. add the following to your `$HOME/.s+ow-bridges` file:

   ```text
   SPOW_TELEGRAM_API_HASH="" SPOW_TELEGRAM_API_ID="" s+ow-telegram-bridge
   ```

   fill in SPOW_TELEGRAM_API_HASH and SPOW_TELEGRAM_API_ID accordingly.
   see the [Telethon docs](https://docs.telethon.dev/en/stable/basic/signing-in.html) for
   more information.

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
- `--delete-last`  
  deletes last location message to prevent clutter

## licence

the s+ow Telegram bridge is free and unencumbered software released into the public
domain. for more information, please refer to the [UNLICENCE](/UNLICENCE),
<https://unlicense.org>, or the python module docstring.
