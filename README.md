# asdf-elixir

Elixir plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Install

> *Elixir requires Erlang to be installed. You can use the [asdf-erlang](https://github.com/asdf-vm/asdf-erlang) plugin to install Erlang versions.*

```
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```

## Elixir Precompiled versions

Precompiled Elixir packages are built by [Bob](https://github.com/hexpm/bob/blob/master/README.md#elixir-builds) whenever
a git push is made to the elixir-lang repo.

These precompiled packages are built against every officially supported OTP version, however if you only specify the
elixir version, like `1.4.5`, by default the downloaded binaries would be those compiled against the latest OTP release
supported by that version. 
If you however, would like to use a more recent OTP you can append `-otp-${OTP_VERSION}` to the version given to asdf-elixir.

So, for example, to install Elixir 1.5.0-rc.0 and take advantage of the new features it takes from OTP-20 you would install

```shell
asdf install elixir 1.5.0-rc.0-otp-20
```

Be sure to also install the coresponding Erlang VM version with asdf-erlang, and to specify both matching versions in
your `.tool-versions` file.

## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Elixir.
