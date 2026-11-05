# will-of-d-todo.md format

For every task only the user can do (create a key, make an account, supply a file, make a decision), write an item here instead of only mentioning it in chat. Collect these before the build starts so the build never has to stop. Check whether the file exists before creating it; if it does, continue in it and never overwrite it.

## Header to write at the top (once)

```
# Your tasks
To respond to any item, write your reply right after the "=" on that item, like: = done, token added to .env
An empty "=" means I will treat it as not yet read.
```

## Item format

```
### 1. <short task title>
What: <one clear line>
How:
  1. <step>
  2. <step>
Why: <optional, one line>
=
```

## Example

```
### 1. Create the Telegram bot token
What: Get a bot token from BotFather.
How:
  1. Open Telegram and search @BotFather
  2. Send /newbot and follow the prompts
  3. Copy the token it gives you
Why: The bot cannot connect without it.
=
```

When the user replies, read it, act on it, and mark the item handled (add "Handled:" and a short note under their line).
