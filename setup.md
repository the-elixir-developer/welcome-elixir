![Ilustración_sin_título](https://github.com/user-attachments/assets/bf5d09b5-d56c-44ba-8706-28618c2d6a1f)

# Setup Elixir and Firsts steps
## Content 

**I. Introduction**
- [Introduction to Elixir](https://github.com/the-elixir-developer/welcome-elixir)
- `1` Setup Erlang and Elixir
- `2` iEX & scripting
  - iEX
  - Hello world
  - Run scripts
- `3` Modules and functions
  - Modules
  - Public and private functions
  
--- 

# 1. Introduction

## 1 Setup

To be able to run your code you must need:
1. Erlang and the BEAM Virtual Machine
2. Elixir installation.

Both considerations are in the [official documentation](https://elixir-lang.org/install.html). This official guide depending on your OS is fine for the beginning. 

## Version Manager ASDF

I strongly recommend use this for install different versions of Elixir and Erlang for *nix OS (you can install many tools).

- Please install [ASDF]([https://github.com/asdf-vm/asdf](https://asdf-vm.com/guide/getting-started.html)) locally.
- After this you'll need to add the plugins to install Erlang and Elixir:
```
asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```
- You can list all the versions available to install: `asdf list all erlang` or ` asdf list all elixir`.
- Now you can be able to install Erlang and Elixir (install Erlang before Elixir).
```
asdf install erlang 26.2.1
asdf install elixir 1.16.0-otp-26
```
- As you can have many versions installed you can set a version locally or globally with `asdf global elixir 1.16.0-otp-26`. (Use this if you install more than 1)

## 2 iEX & Scripting

`iEX`
1. Elixir allow us to have a REPL, it comes from Erlang `erl`, so we have the `iex` interactive shell to run our code.
2. In your command line after install elixir you can type `iex`.
3. Print your first Hello World: `IO.puts("Hello World from the Elixir Workshop for beginners")`.

`Scripting`
1. To run code using Elixir, you need to create a file `hello_world.exs`.
2. In this file please save this line: `IO.puts("Hello World - Script Mode")`.
3. To run this code just type: `elixir hello_world.exs`.

## 3 Modules and Functions

1. Create a new file `cake_factory.exs`.
2. Inside this create a new module called `CakeFactory`.
3. Please write a function `create_cake/0` that prints a message.

`cake_factory.exs`
```elixir
defmodule CakeFactory do

  def create_cake() do
    IO.puts "Cake Factory creates a new cake!"
  end

end
```

4. Open an `iex` session. Charge your script: `c "cake_factory.exs"`.
5. Run your function: `CakeFactory.create_cake()`.

