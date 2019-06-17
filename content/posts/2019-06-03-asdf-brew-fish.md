---
title: "The One with Homebrew, Fish and asdf"
date: 2019-06-03T09:13:53+02:00
tags: 
- tools
- elixir
---

I have had to set up a version manager for Elixir, so I tried to install asdf which did not really work how I thought it would. According to https://asdf-vm.com/#/, it should be pretty straightforward, but apparently, the combination of Homebrew and Fish shell is tricky, again. So here is how it works for me (tested with 2 Macbooks with the same setup):

`brew install asdf` works fine, but then I am getting [errors](https://github.com/asdf-vm/asdf/issues/428). So this is what needed to be added to my fish config:

```
source (brew --prefix asdf)/asdf.fish
```


Completions are also not installed where the guide says, so the correct command seems to be: 

```
mkdir -p ~/.config/fish/completions; and cp /usr/local/share/fish/vendor_completions.d/asdf.fish ~/.config/fish/completions
``` 

Now `asdf version` prints out the version and some docs.

When I now try to install the necessary brew plugin dependencies, there are errors during the linking step. Apparently, I am [not supposed to install](https://github.com/jakubroztocil/httpie/issues/645) something in /usr/local, but that's where Homebrew wants to do this. Fixed by running 

```
sudo chown -R (whoami) (brew --prefix)/*
```

and then 

```
brew install \
  coreutils automake autoconf openssl \
  libyaml readline libxslt libtool unixodbc \
  unzip curl
```

Next steps: 

```
asdf plugin-add erlang
asdf plugin-add elixir
asdf install erlang 22.0
asdf install elixir 1.8.2
asdf global erlang 22.0
asdf global elixir 1.8.2
```

There are some popups asking me to install Java in order to use the javac command line tool, but so far everything seems to work without doing that. `elixir -v` prints out 

```
Erlang/OTP 22 [erts-10.4] [source] [64-bit] [smp:4:4] [ds:4:4:10] [async-threads:1] [hipe]

Elixir 1.8.2 (compiled with Erlang/OTP 20)
```

and I seem to be able to start up our latest application (which needs Elixir 1.8 because of some Ecto issues and that's why I needed to start this messy journey in the first place), yay!






