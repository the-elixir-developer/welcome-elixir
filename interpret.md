<img width="1043" alt="image" src="https://github.com/user-attachments/assets/b1049f82-c167-4d63-b7d2-85890b016093">

# Code Interpretation

One the most useful skills as software developers is the ability to read code, but this involves a lot of things to do: understand the syntax, the ability to process the instructions and understand how the code is going to work. 

> I recommend you The Brain's Programmer book to learn more about the cognitive processes involved in coding https://www.manning.com/books/the-programmers-brain

## Reading Elixir Code

The following snippet is an elixir function from a module:

````elixir`
defmodule PipelineExample do
  def process_numbers(numbers) do
    numbers
    |> Enum.filter(fn x -> rem(x, 2) == 0 end) # Step 1: Remove odd numbers
    |> Enum.map(&(&1 * 2))                     # Step 2: Double each even number
    |> Enum.sum()                              # Step 3: Sum the results
  end
end
```

You can:
- Try this code in your iex.
- Read how to use this code, for execution you'll need to call `PipelineExample.process_numbers(12300)`.
- Can you understand what this code is doing?
- Being confused is part of the journey.
- `Enum` is an elixir important module, you can read the documentation here: https://hexdocs.pm/elixir/1.12/Enum.html (or in the iex you have the docs available).

<img width="1046" alt="image" src="https://github.com/user-attachments/assets/4d0caf70-ebcd-4209-91c3-9ebd8c95b1d2">

Next example:

```elixir
defmodule BasicPipeline do
  def transform_number(number) do
    number
    |> add_five()         # Step 1: Add 5
    |> double()           # Step 2: Double the result
    |> to_string()        # Step 3: Convert to string
  end

  defp add_five(n), do: n + 5
  defp double(n), do: n * 2
  defp to_string(n), do: Integer.to_string(n)
end
```

```elixir
defmodule StringPipeline do
  def transform_string(str) do
    str
    |> trim_string()      # Step 1: Trim whitespace
    |> upcase_string()    # Step 2: Convert to uppercase
    |> add_exclamation()  # Step 3: Add an exclamation mark
  end

  defp trim_string(s), do: String.trim(s)
  defp upcase_string(s), do: String.upcase(s)
  defp add_exclamation(s), do: s <> "!"
end
```

```elixir
defmodule ListPipeline do
  def transform_list(numbers) do
    numbers
    |> remove_negatives()  # Step 1: Remove negative numbers
    |> square_numbers()    # Step 2: Square each number
    |> filter_evens()      # Step 3: Keep only even numbers
  end

  defp remove_negatives(list), do: Enum.filter(list, &(&1 >= 0))
  defp square_numbers(list), do: Enum.map(list, &(&1 * &1))
  defp filter_evens(list), do: Enum.filter(list, &(rem(&1, 2) == 0))
end
```
