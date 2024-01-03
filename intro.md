# 3. Elixir Programming

> Elixir is a dynamic, functional language for building scalable and maintainable applications.

1. Ejecución de código
2. Módulos y funciones
3. Código de Elixir

### 1. Ejecución de código

1. Una vez que instalaste elixir, normalmente puedes hacer uso de scripts o bien usar la REPL para probar código.
2. Crea un archivo `hello.exs`, y dentro de él escribe `IO.puts "Hello from my first elixir script"`.
3. En tu terminal ejecuta la REPL con el comando `iex`, este te abrirá una terminal interactiva en donde podrás ejecutar código de Elixir.

### 2. Módulos y funciones

El código en elixir se divide en módulos, que normalmente son escritos por archivos, es decir, 1 módulo por archivo. Cada módulo puede contener funciones públicas (que puedes usadas en otros módulos) o bien funciones privadas (solo pueden ejecutarse en el mismo módulo).

```elixir
# This is a module
defmodule MyModule do

  # This is a function
  def hello_world() do
    IO.puts "Hello world"
  end

end

# Run the previous code as a script
MyModule.hello_world()
```

1. Copia el código anterior y crea un nuevo archivo llamado `script.exs`.
2. Corre el script de la siguient forma `elixir script.exs`.
3. Borra la última línea del archivo y guardalo así.
4. Abre una repl `iex`.
5. Dentro de la repl carga tu script: `c "script.exs"`.
6. Ejecuta tu función desde la repl: `MyModule.hello_world()`

Estas son dos formas de ejecutar código de Elixir usando scripts, REPL o una combinación de ambos.

### 3. Código de Elixir

Elixir es un lenguaje de propósito general, al ser construído en la BEAM VM hereda todas las características de Erlang, sin embargo es un lenguaje que debe ser considerado como un lenguaje único. El gran esfuerzo de Elixir es ser un lenguaje de programación para tu día a día, que en su uso más básico puedes realizar lo mismo que en otros lenguajes.

¿Podrías ejecutar, leer, y entender el siguiente módulo escrito en Elixir?

``` elixir
defmodule Engine do

  def process_cake() do
    empty_cake =
      %{
        description: "Mi primer pastel",
        shake: false,
        bake: false
      }

    empty_cake
    |> step_1()
    |> step_2()
    |> step_3()
    |> step_4()
    |> step_5()
  end

  def step_1(cake) do
    Map.put(cake, :eggs, 2)
  end

  def step_2(cake) do
    Map.put(cake, :fluor, 1)
  end

  def step_3(cake) do
    Map.put(cake, :butter, 1)
  end

  def step_4(cake) do
    Map.put(cake, :shake, true)
  end

  def step_5(cake) do
    Map.put(cake, :bake, true)
  end
end
```





