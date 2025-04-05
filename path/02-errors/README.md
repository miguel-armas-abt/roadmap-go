# MANEJO DE ERRORES

[← Regresar a notas](../../README.md) <br>

---

A diferencia de Java, en lugar de lanzar y atrapar excepciones mediante un try-catch, 
los errores en GO se manejan mediante el retorno de un valor de error explícito y se utilizan estructuras de control como `if` y `return` para gestionar los casos de error de manera más controlada.

En GO, el valor de retorno `nil` es válido para los tipos de error y <u>se utiliza para indicar que no hubo errores en la ejecución de la función</u>.

---

## Interface Error
La interfaz `error` es la interface predeterminada para representar errores. Esta interfaz comprende de un método con la siguiente firma:

```go
Error() string
```

Por ejemplo:

```go
package main

import (
    "fmt"
    "errors"
)

type CustomError struct {
    Code    int
    Message string
}

// Implementa la interfaz error
func (error CustomError) Error() string {
    return fmt.Sprintf("Error %d: %s", error.Code, error.Message)
}

func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, CustomError{Code: 1, Message: "Cannot divide by zero"}
    }
    return a / b, nil
}
```