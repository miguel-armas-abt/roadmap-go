# GO

[← Regresar a notas](../../README.md) <br>

---

[1. Convenciones](#1-convenciones) <br>
[2. Go mod](#2-go-mod) <br>
[3. Go main](#3-go-main) <br>
[4. Slice](#4-slice) <br>
[5. Interface](#5-interface) <br>
[5. Paso por valor](#6-paso-por-valor) <br>
[5. Operador puntero &](#7-operador-puntero-) <br>
[5. Operador desreferenciar *](#8-operador-desreferenciar-) <br>

---

- Es un lenguaje que hereda su core de C++, con sintaxis mejorada.
- Fue pensado para aprovechar los últimos avances en multiprocesadores y paralelismo.
- Es un lenguaje compilado que genera archivos .exe portables a cualquier SO.

---

## 1. Convenciones

- Las funciones pueden devolver más de un valor.
- Solo existe la instrucción `for` para las iteraciones (no existe `while`).
- <u>No es un lenguaje orientado a objetos</u>. Resuelve la POO con estructuras, funciones e interfaces.
- El scope de variables y funciones se determina con nombres en mayúsculas y minúsculas.
- Cuando las variables no se inicializan, su valor por default no es nulo, sino el valor mínimo de ese tipo de dato.
- Durante la asignación con `:=`, se asume que las variables de la izquierda no han sido creadas previamente.
- El return sin ningún argumento se usa en métodos que no retornan nada, y sirve para salir del método.
- Se pueden desarrollar tanto instrucciones síncronas como asíncronas.

---

## 2. Go mod
Archivo que permite gestionar las dependencias.

> ### ▶️ Crear un nuevo proyecto
> ```shell
> go mod init
> ```

---

## 3. Go main
Archivo principal.

> ### ▶️ Ejecutar archivo principal
> ```shell
> go run main.go
> ```

> ### ▶️ Compilar y generar el .exe
> ```shell
> go build main.go
> ```

---

## 4. Slice
Estructura de datos para almacenar secuencias de elementos.

---

## 5. Interface
GO <u>infiere automáticamente qué clases implementan de una interfaz</u> en función de la firma de sus métodos.

---

## 6. Paso por valor

En GO, no hay "paso por referencia" o "paso por variable" como en Java. GO utiliza un modelo de paso de argumentos conocido como "paso por valor".

Cuando se pasa una variable a una función en GO, se realiza una copia de su valor y se pasa a la función. 
Esto significa que cualquier modificación realizada dentro de la función no afectará a la variable original en el ámbito desde el cual se llamó a la función.

Sin embargo, hay una excepción a esta regla cuando se trata de tipos de datos de referencia, como los slices y los mapas.
Estos tipos de datos se pasan por valor, pero contienen referencias internas a los datos subyacentes.
Esto significa que si modificas los datos dentro de un slice o un mapa dentro de una función, los cambios se reflejarán en la variable original.

---

## 7. Operador puntero &

Este operador se utiliza para obtener la dirección de memoria de una variable.
En GO, esto se llama “puntero”. Un puntero es la variable que almacena la dirección de memoria de otra variable.
Usamos punteros para acceder y manipular directamente los datos a los que apuntan.
Generalmente, <u>se utilizan cuando queremos pasar una variable a una función y queremos modificar el valor original de la variable</u> dentro de la función en lugar de una copia.

## 8. Operador desreferenciar *

Este operador se utiliza para acceder al valor almacenado en la dirección de memoria apuntada por el puntero. Esto se conoce como “desreferenciar”.
Cuando declaramos una variable puntero con el operador &, podemos usar el operador * para acceder al valor almacenado en esa dirección de memoria.

```go
func main() {
    var x int // Variable normal
    var ptr *int // Declaración de un puntero a un entero
    x = 42
    ptr = &x // Asignamos la dirección de memoria de "x" al puntero "ptr"

    fmt.Println("Valor de x:", x) // Valor de x: 42
    fmt.Println("Valor apuntado por el puntero:", *ptr) // Valor apuntado por el puntero: 42

    *ptr = 10 // Modificamos el valor de "x" a través del puntero
    fmt.Println("Nuevo valor de x:", x) // Nuevo valor de x: 10
}
```


