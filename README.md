# asdf-elixir

Elixir plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Install

This plugin needs `unzip` to be installed.

If you have a Debian system you can install it by typing:
`sudo apt-get install unzip`

> *Elixir requires Erlang to be installed. You can use the [asdf-erlang](https://github.com/asdf-vm/asdf-erlang) plugin to install Erlang versions.*

```
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```

## Elixir precompiled versions

Precompiled Elixir packages are built by [Bob](https://github.com/hexpm/bob/blob/master/README.md#elixir-builds) whenever
a git push or a new release is made at the elixir repo. There's also a [status page](https://bobs-list.kobrakai.de/) available with an overview of all available packages and their availability.

The precompiled packages are built against every officially supported OTP version, however if you only specify the
elixir version, like `1.4.5`, the downloaded binaries will be those compiled against the oldest OTP release
supported by that version.

If you would like to use precompiled binaries built with a more recent OTP, you can append `-otp-${OTP_MAJOR_VERSION}` to any installable version that can be given to asdf-elixir.

So, for example, to install Elixir 1.5.0 and take advantage of the new features from OTP-20 you might install version `1.5.0-otp-20`.

Be sure to also install the corresponding Erlang/OTP version with asdf-erlang, and to have both selected versions in your
`.tool-versions` file.

## Compiling from a git reference

You can compile your own elixir from a commit reference from the [elixir github repository](https://github.com/elixir-lang/elixir/commits/master).

### .tool-versions file

You can specify the version to install with a line like so in your `.tool-versions` file:

```
elixir ref-<commit reference>
```

### Using the CLI

You can install the version using: `asdf install elixir ref:<commit reference>`.

You can then set the local/global version to your new version with `asdf local elixir ref-<commit reference>` or `asdf global elixir ref-<commit reference>`.

## Elixir escripts support

This plugin supports elixir escripts adding them to your path just like any other elixir binary.
Whenever you install a new escript with `mix escript.install` you need to `asdf reshim elixir` in order
to create shims for it.


## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Elixir.
