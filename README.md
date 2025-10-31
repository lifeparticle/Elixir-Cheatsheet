# Elixir-Cheatsheet

## Install


```bash
brew install erlang elixir

erl -version
elixir --version
```


## ElixirLS: Elixir support and debugger


https://marketplace.visualstudio.com/items?itemName=JakeBecker.elixir-ls

## Create a Mix project


```bash
mix new app
mix help
```

```ex
defmodule App do
  def hello(name) do
    "Hello, #{name}!"
  end
end

IO.puts App.hello("World")
```

```bash
elixir lib/app.ex 
Hello, World!
```

## Interactive shell

```bash
iex
Erlang/OTP 28 [erts-16.1.1] [source] [64-bit] [smp:10:10] [ds:10:10:10] [async-threads:1] [jit] [dtrace]

Interactive Elixir (1.19.1) - press Ctrl+C to exit (type h() ENTER for help)
iex(1)> c "app/lib/app.ex"
Hello, World!
[App]
```

```bash
iex app/lib/app.ex
Hello, World!
[App]
```


```bash
cd app
iex -S mix
Erlang/OTP 28 [erts-16.1.1] [source] [64-bit] [smp:10:10] [ds:10:10:10] [async-threads:1] [jit] [dtrace]

Compiling 1 file (.ex)
Hello, World!
Generated app app
Interactive Elixir (1.19.1) - press Ctrl+C to exit (type h() ENTER for help)

App.hello("Test")
"Hello, Test!"
```

### Reload

```ex
defmodule App do
  def hello(name) do
    "Hi, #{name}!"
  end
end

IO.puts App.hello("World")
```

```bash
r App
    warning: redefining module App (current version loaded from _build/dev/lib/app/ebin/Elixir.App.beam)
    │
  1 │ defmodule App do
    │ ~~~~~~~~~~~~~~~~
    │
    └─ lib/app.ex:1: App (module)

Hello, World!
{:reloaded, [App]}
iex(4)> App.hello("Test")
"Hello, Test!"
```
