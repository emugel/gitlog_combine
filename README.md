# gitlog_combine

**Bash tool mixing (merging, combining, concatenating, ...) the git log of several repositories on the CLI.**

## Why?

Suppose you have a `~/code` directory containing those repos:

```
uninteresting_stuffs/
pokemoncore/
pokemonserver/
pokemonclient/
```

You would use this tool to check the recent git logs of those 3 pokemon folders:

`gitlog_combine pokemon*`

```
<TODO> show the output
```

## Usage

* `gitlog_combine pokemon*` :: By default, shows the 15 most recent entries.
* `gitlog_combine pok* --days=5` :: In the last 5 days.
* `gitlog_combine * -n 5` :: The 5 most recent entries.
* `gitlog_combine * --all` :: Output everything, from first to last
* `gitlog_combine * --all | tac` :: Output everything, from last to first

For now, it just works on current branches.
Only direct descendant directories containing a .git/ folder will be considered, unless you add them like this: `gitlog_combine pok* /path/to/some/other/repo /yet/another/one`.


