# will-of-d-notes.md format

Check whether the file exists before creating it. If it exists, continue in it and never overwrite it.

## Header to write at the top (once)

```
# Notes
To respond to any item, write your reply right after the "=" on that item, like: = got it, go ahead
An empty "=" means I will treat it as not yet read.
```

## Entry types

Tag each entry with one of: `[ERROR]` `[ASSUMPTION]` `[DECISION]` `[RISK]` `[UNFINISHED]` `[DISCOVERY]`

## Detail level

Default is one clear line that states the issue directly. The line must make sense alone.

```
[ASSUMPTION] Used API v2, because the v1 docs were outdated.
[ERROR] Login failed with 401, fixed by switching to the refresh-token route.
[DECISION] Chose SQLite over Postgres, because there is one user and no server.
```

Serious issues and risks get a few lines: what happened, why it matters, what was done or is needed. Add an `=` line when the user's reaction matters.

```
[RISK] Payment keys are stored in plain text in .env.
  Anyone with file access can read them. I kept it for the demo; move them to a secret manager before launch.
  =
```
