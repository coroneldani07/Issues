# Diagrama de clases

```mermaid

@startuml
' =====================================
' DIAGRAMA DE CLASES - Sistema de IVA
' =====================================

class Producto {
    - String nombre
    - double precioBase
    + Producto(String nombre, double precioBase)
    + double getPrecioBase()
}

class CalculadoraIVA {
    - double IVA = 0.21
    + double calcularPrecioFinal(double precio)
}

class Main {
    + void main(String[] args)
}

class Scanner <<External>>

' Relaciones
Main ..> Producto : crea instancia
Main ..> CalculadoraIVA : usa para calcular
Main ..> Scanner : usa para leer entrada

@enduml


```
