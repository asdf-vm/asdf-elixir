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

## Check compatibility between elixir and erlang:

https://hexdocs.pm/elixir/master/compatibility-and-deprecations.html#compatibility-between-elixir-and-erlang-otp

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

> **Note**: You do not need to have Erlang installed to install a precompiled version of Elixir installed, but you will need to have it available at runtime, otherwise your Elixir commands will fail. Even though it's possible to install Elixir first, it's recommended to install Erlang first.

## Compiling from a Git reference or from source

### Using the CLI

You can download and compile a specific commit reference from the [Elixir GitHub repository](https://github.com/elixir-lang/elixir/commits/main) by running: `asdf install elixir ref:<commit reference>`. You can then set the local/global version to your new version by running:

```
asdf local elixir ref:<commit reference>
# Or
asdf global elixir ref:<commit reference>
```

You can also [compile Elixir from source](https://github.com/elixir-lang/elixir/tree/master#compiling-from-source) without using `asdf` (for example, so that you can use the `master` branch of elixir or a branch with your own modifications), then use it by specifying the directory path:

```
# After Elixir already installed into /path/to/elixir
asdf local elixir path:/path/to/elixir
# Or
asdf global elixir path:/path/to/elixir
```


### .tool-versions file

You can specify the version to install with a line like so in your `.tool-versions` file:

```
elixir ref:<commit reference>
```

Or if you've already compiled Elixir from source in a specific directory:

```
elixir path:/path/to/elixir
```

Note that the path specified must be an absolute path to the Elixir installation's root directory (e.g. the directory containing the `bin` directory).

## Elixir escripts support

This plugin supports elixir escripts, adding them to your path just like any other elixir binary.
Whenever you install a new escript with `mix escript.install` you need to `asdf reshim elixir` in order
to create shims for it.


## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Elixir.

## Helpful Articles:

https://www.cogini.com/blog/using-asdf-with-elixir-and-phoenix/
