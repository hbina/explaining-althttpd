+++
title = "BAT: Better cat"
date = 2021-07-10
+++

## Introduction

`bat` is `cat`-like utility.
See its [Github repository](https://github.com/sharkdp/bat).
This is some features of `bat` that I use.

### Prettier cat

By default, `bat` will include some fluff with it which doesn't look as good when you copy and paste them directly. As can be seen below,

```shell
coreutils on  hbina-tr-return-err-when-extra-args [$!?] is 📦 v0.0.6 via 🦀 v1.53.0
❯ bat file.txt
───────┬────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: file.txt
───────┼────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ esgesg
───────┴────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

You can fix this by adding `--plain`.

```shell
coreutils on  hbina-tr-return-err-when-extra-args [$!?] is 📦 v0.0.6 via 🦀 v1.53.0
❯ bat --plain file.txt
esgesg
```

So why is it better? Because it supports syntax highlighting :) but I can't really show it here either.

### Print specific lines of text in file

I am sure you can do this with `cat --number` and `grep` for specific line or whatever. But this is a lot simpler,

```shell
coreutils on  hbina-tr-return-err-when-extra-args [$!?] is 📦 v0.0.6 via 🦀 v1.53.0
❯ bat --plain --line-range 363:369 src/uu/tr/src/tr.rs
        .arg(
            Arg::with_name(options::SETS)
                .multiple(true)
                .takes_value(true)
                .min_values(1)
                .max_values(2),
        )
```
