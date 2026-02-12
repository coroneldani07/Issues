# Diagrama de clases

sequenceDiagram
    autonumber
    actor Usuario
    participant M as Main
    participant S as Scanner
    participant P as Producto
    participant C as CalculadoraIVA

    Usuario->>M: Ejecuta el programa
    M->>S: new Scanner(System.in)
    
    M->>Usuario: "Nombre del producto: "
    Usuario-->>M: "Camiseta"
    
    M->>Usuario: "Precio base: "
    Usuario-->>M: 20.0
    
    M->>P: new Producto("Camiseta", 20.0)
    activate P
    P-->>M: instancia creada
    deactivate P
    
    M->>C: calcularPrecioFinal(20.0)
    activate C
    Note over C: Aplica IVA (21%)
    C-->>M: 24.2
    deactivate C
    
    M->>Usuario: Imprime "Total con IVA: 24.2"
