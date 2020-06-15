# gitlog_combine

**Bash tool mixing (SEO: merging, combining, concatenating+sorting, ...) the git log of several repositories on the CLI.**

## Why?

After an half an hour search for such a tool I didn't find much (see Alternatives below)

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
4 weeks ago 4a498 pokemoncore: change README
3 weeks ago 9f201 pokemonclient: add GET /nbPokemons
3 weeks ago 42424 pokemonserver: add GET /nbPokemons
2 minutes ago 1a9a42 pokemoncore: fix #42
```

You may also want to show the last 2 entries per repo:

`gitlog_combine -m 2 pokemon*`

```
pokemoncore   4 weeks ago   change README
              2 minutes ago fix #42
pokemonclient 7 months ago  version 1.1
              3 weeks ago   add GET /nbPokemons
pokemonserver 6 months ago  version 1.1
              3 weeks ago   add GET /nbPokemons
```

The second version with `-m` will show different colors, for instance 2 minutes will be bright red, while old entries will be dark gray. 

## Usage

* `gitlog_combine pokemon*` :: By default, shows the 15 most recent entries.
* `gitlog_combine pok* --days=5` :: In the last 5 days (TODO)
* `gitlog_combine * -n 5` :: The 5 most recent entries globally
* `gitlog_combine * -m 2` :: The last 2 entries for each repo, colored based on recentness
* `gitlog_combine * -m 2 --long` :: The last 2 entries for each repo, not truncating commit msg to 60 chars
* `gitlog_combine * --all` :: Output everything, from first to last
* `gitlog_combine * --all | tac` :: Output everything, from last to first
* `gitlog_combine pok*  /path/to/some/other/repo  /yet/another/one` :: This also works

When using a wildcard, files will not be considered, directories not having a direct `.git/` child will not be considered.

## Restrictions

* If you use option `-n`, make sure to put a space between it and the next digit, e.g. `-n 5`. 
* For now, it just works on current branches. So work on other branches will not be shown.

This is public domain. Feel free to modify it.

# Alternatives 

Didn't find much, which is why I wrote this pure bash script that just works simpler.

* [gitlogg](https://daattali.com/shiny/visualize-git-commits-time/), it is not in pure bash but requires node and babeljs, plus it merges logs in a json file.
* [gist from gka](https://gist.github.com/gka/393f5ab2b95e927d305eb6e14767180e), to show logs on a png using R
