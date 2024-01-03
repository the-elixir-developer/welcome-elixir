# 2. Erlang, the BEAM, and the COP

`Erlang and the BEAM`

- Elixir pertenece a la familia de los lenguajes de la máquina virtual de Erlang BEAM.
- Erlang es un lenguaje de programación de la familia de `pure message passing`.
- Fue un lenguaje construído en el laboratorio de CS de Ericsson en los años 80's.
- La idea inicial era construir una implementación de prolog con `message passing`.
- Erlang nace como una solución para crear sistemas de telecomunicaciones.
- Fue creado por Joe Armstrong, Robert Virding y Mike Williams.

`Erlang para sistemas de telecomunicaciones`

`Propiedades de un sistema de telecomunicaciones`
- `Concurrency` El sistema debe ser capaz de procesar un alto número de actividades concurrentes.
- `Soft real-time` Las acciones se deben ser procesadas en un punto en el tiempo.
- `Distributed` Los sistemas deben ser distribuídos.
- `Hardware interaction` El sistema usará control de hardware.
- `Large software systems` Los sistemas de software son grandes.
- `Complex functionality` Gran complejidad en las funcionalidades.
- `Continuous operation` Los sistemas deben continuar en operación por muchos años.
- `Quality requirements` Confiabilidad y calidad en los requerimientos de software.
- `Fault tolerance` Tolerancia a fallos.

`Erlang Philosophy`

1. Tasks
2. Perform
3. Errors

Cada `task` corresponde a un número de metas a cumplir. El software se diseña en una jerarquía de `tasks` que el sistema debe cumplir. Cada `task` guarda un nivel de complejidad, cuando ocurre un `error` en su ejecución, se tratará de corregir, en caso de que no se pueda corregir, se dejará de lado y se continuará con la siguiente `task`.

Consideraciones:

- Pensar en `tasks` implica un nivel fuerte de encapsulación.
- La tolerancia a fallos implica aislar los errores.
- Si al tratar de ejecutar los `tasks` ocurre un error, este no deberá propagarse a otras partes del sistema.

`Concurrency Oriented Programming COP`

- El mundo real es concurrente.
- La norma es la programación secuencial, la prorgamación concurrente es evitada.
- No hay mucho soporte de programación concurrente.
- La concurrencia es parte de tu lenguaje de programación y no del SO.
- La concurrencia se refiere a eventos ocurriendo simultáneamente.

`COP in practice`

- Un proceso es un conjunto de tareas a ejecutar.
- Todo es un proceso.
- Cada proceso es aislado de otros. No comparte memoria con ningún otro proceso.
- Los procesos pueden interactuar entre sí por medio de `message passing`.

