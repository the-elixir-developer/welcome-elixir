# Welcome Elixir

> Guieline to unleash your developer's journey using Elixir. 🎇

![](./assets/slide-005.png)

Pequeña guía introductoria en español sobre Elixir. Si este contenido es útil para ti, considera dejar una ⭐️ para saberlo.

## 1. Erlang como lenguaje de programación

- Elixir pertenece a la familia de los lenguajes de la máquina virtual de Erlang BEAM.
- Erlang es un lenguaje de programación de la familia de `pure message passing`.
- Fue un lenguaje construído en el laboratorio de CS de Ericsson en los años 80's.
- La idea inicial era construir una implementación de prolog con `message passing`.
- Erlang nace como una solución para crear sistemas de telecomunicaciones.
- Fue creado por Joe Armstrong, Robert Virding y Mike Williams.

![](./assets/slide-006.png)

## 2. Erlang para sistemas de telecomunicaciones

![](./assets/slide-007.png)

![](./assets/slide-008.png)

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

![](./assets/slide-009.png)

## 3. Procesos en la BEAM

Los `procesos` son un concepto central en la elaboración de sistemas en la BEAM, es la unidad principal de trabajo con el que puedes diseñar soluciones que hagan uso de todas las capacidades de Erlang.

![](./assets/slide-010.png)

![](./assets/slide-011.png)

![](./assets/slide-012.png)

![](./assets/slide-013.png)

![](./assets/slide-014.png)

Si quieres conocer más de procesos puedes leer este blog post: [Understanding processes for elixir developers | ESL Blog](https://www.erlang-solutions.com/blog/understanding-processes-for-elixir-developers/)

## 4. Elixir como lenguaje de la BEAM

Sobre los conceptos anteriores está construído Elixir, un lenguaje de propósito general que hereda todas las ventajas de la BEAM, sin embargo Elixir debe considerarse como un lenguaje por aparte, ya que al ser de propósito general y funcional te facilita ciertos caminos para aprenderlo y comenzar a construir aplicaciones con él.

![](./assets/slide-015.png)

## 5. Nociones Básicas de Elixir

A diferencia de la Orientación a Objetos, Elixir maneja módulos que contienen funciones que ejecutan la lógica de programación.

![](./assets/slide-016.png)

```elixir
defmodule Engine.CustomerContext do # Definición de un módulo
  alias Engine.Customer
  alias Engine.Repo

  def create_customer(attrs) do # Función pública
    %Customer{}
    |> Customer.changeset(attrs)
    |> validate_changeset()
    |> Repo.insert()
  end

  defp validate_changeset(changeset) do # Función privada, solo accesible dentro de este módulo
    #...
  end

end
```

Una vez que construyes tus módulos, puedes invocarlos entre ellos, de igual forma las dependencias externas son módulos que invocas directamente en tu proyecto. De forma muy sencilla así se ve la interacción entre unos cuantos módulos:

![](./assets/slide-017.png)

Si bien Elixir es un lenguaje funcional, cabe destacar la importancia de pensar en transformación de datos, es decir, pensar en `input` como entrada de información que por medio de una función se transformará en un `output`.

![](./assets/slide-018.png)

## 6. Sistemas en Elixir

Aunque Erlang y la BEAM son tecnologías muy poderosas, Elixir es un lenguaje que te facilita hacer cualquier tarea cotidiana, no necesitas usar concurrencia y distribución desde el inicio, ya que es una opción que te habilita el mismo ecosistema si así lo necesitas. Por lo que Elixir es una gran opción incluso para developers novatos que estén buscando un buen lenguaje de programación.

![](./assets/slide-019.png)

## 7. Sistemas en Erlang

La gran noticia es que todas las capacidades de la BEAM están disponibles en Elixir, esto quiere decir que en un momento dado puedes comenzar a diseñar componentes que aprovechen estas características, para ello será necesario diseñar en procesos, para lo cuál será necesario aprender cómo funcionan los diseños de OTP que te facilitarán mucho este paso.

![](./assets/slide-020.png)

## 8. Sistemas en la BEAM

Con Elixir es posible crear una aplicación sin pensar en nada de concurrencia y distribución, estos features son una opción que puedes implementar en cierto momento dado, ya que son capacidades que te otorga la máquina virtual de Erlang.

![](./assets/slide-021.png)

## 9. El ecosistema de Elixir

- [Phoenix Framework](https://www.phoenixframework.org/)
- [Ecto Db](https://hexdocs.pm/ecto/Ecto.html)
- [Nx](https://github.com/elixir-nx/)
- [Nerves](https://nerves-project.org/)
- [Native LiveViews](https://native.live/)

![](./assets/slide-022.png)

## 10. Una app en elixir.

![](./assets/slide-023.png)

## 11. Phoenix Live views

En el 2019 se anunció LiveViews como un nuevo componente para crear features en el front-end usando solamente Elixir y dejándo de lado Javascript. Este proyecto funciona a traves de websockets, cada cliente se conecta a un socket, y por medio de este es como se va actualizando la vista en el navegador. 

![](./assets/slide-024.png)

Este es un buen ejemplo de cómo hacer uso de procesos y OTP para diseñar componentes, ya que detrás de cada conexión por socket, hay un proceso de Erlang que se encarga de administrarlo. 

![](./assets/slide-025.png)

## 12. Productividad con Elixir

![](./assets/slide-026.png)

## 13. ¿Por donde comenzar?

Si deseas comenzar a estudiar Elixir como lenguaje de programación te recomiendo mucho comenzar por lo básico, es decir, por entender el lenguaje como tal, adoptar el estilo de la programación funcional y sentirte cómodo para resolver ejercicios de lógica, aprender Unit Testing te ayudará muchísimo. Una vez que tengas confianza en el lenguaje puedes seguir al uso de Phoenix Framework, conexión a base de datos y despliegue. Con esto cubrirás buena parte para realizar aplicaciones completas, pero te llevará un tiempo. Luego puedes extenderte al estudio de Erlang, procesos y OTP, que en mi opinión es algo más complejo.

**Elixir Básico**
- [Elixir in Action](https://www.manning.com/books/elixir-in-action-second-edition)
- [Programming Elixir by Dave Thomas](https://pragprog.com/titles/elixir16/programming-elixir-1-6/)
- [Programmer Passport Elixir by Bruce Tate](https://pragprog.com/titles/passelixir/programmer-passport-elixir/)
- [Elixir Introducción para Alquimistas por Manuel Rubio](https://altenwald.com/es/book/elixir)
- [Adopting Elixir](https://pragprog.com/titles/tvmelixir/adopting-elixir/)

**Frameworks**
- [Programming Phoenix](https://pragprog.com/titles/phoenix14/programming-phoenix-1-4/)
- [Programming Ecto](https://pragprog.com/titles/wmecto/programming-ecto/)
- [Testing Elixir](https://pragprog.com/titles/lmelixir/testing-elixir/)

**Erlang, la BEAM y OTP**
- [Designing Elixir systems with OTP](https://pragprog.com/titles/jgotp/designing-elixir-systems-with-otp/)
- [Concurrent Data processing in Elixir](https://pragprog.com/titles/sgdpelixir/concurrent-data-processing-in-elixir/)
- [Erlang/OTP Un Mundo Concurrente](https://altenwald.com/es/book/erlang-i)
- [Introducing Erlang](https://www.oreilly.com/library/view/introducing-erlang/9781449331757/)
- [Learn You Some Erlang for great good!](https://learnyousomeerlang.com/)

**Ejercicios y otros sitios de apoyo**
- [Exercism Elixir](https://exercism.org/tracks/elixir)
- [Elixir School](https://elixirschool.com/es/)

**Gleam Lang**
- [Docs](https://gleam.run/)
- [Tour](https://tour.gleam.run/)

**Blog Posts by Carlo Gilmar**
- [Learning IoT with Elixir](https://medium.com/@carlogilmar/learning-iot-first-steps-with-elixir-310c4ad4ab15)
- [Phoenix Live Views](https://medium.com/@carlogilmar/phoenix-live-view-what-is-it-a218b2a5fcaa)

## 14. Próximos eventos y más información

![image](https://github.com/the-beam-developer/welcome-elixir/assets/17634377/a7f55678-5c8a-4d67-a1bf-eac44bce97b4)

`Conferencias`
- [Code BEAM America](https://codebeamamerica.com/)
- [Elixir Conf EU Lisbon](https://www.elixirconf.eu/)
- [Elixir Conf US](https://2023.elixirconf.com/)

`Erlang Solutions`
- [Certificación Elixir y Erlang ESL](https://www.erlang-solutions.com/landings/landing-certification-2/)
- [Code Sync YouTube](https://www.youtube.com/@CodeSync)
- [Blog ESL](https://www.erlang-solutions.com/blog/)

  
