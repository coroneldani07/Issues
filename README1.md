# Diagrama de clases

```mermaid
class Producto {
    - nombre : String
    - precioBase : double
    + Producto(nombre : String, precioBase : double)
    + getPrecioBase() : double
}

class CalculadoraIVA {
    - IVA : double = 0.21
    + calcularPrecioFinal(precio : double) : double
}

class Main {
    + main(args : String[]) : void
}

class Scanner <<External>>

Main ..> Producto : crea
Main ..> CalculadoraIVA : usa
Main ..> Scanner : lee datos

@enduml
