# DEFER, PANIC, RECOVER

[← Regresar a notas](../../README.md) <br>

---

## Defer
La sentencia `defer` se utiliza para posponer la ejecución de una función hasta que la función que la contiene haya finalizado. 
Puede usarse en tareas de liberación de recursos, como cerrar archivos o conexiones de red.

---

## Panic
La sentencia `panic` se utiliza para detener inmediatamente la ejecución normal del programa y generar una excepción.
Puede ser utilizada para indicar errores graves o condiciones inesperadas.

---

## Recover
La función `recover` se utiliza en combinación con defer para manejar y recuperarse de una situación de pánico (`panic`).
Permite capturar la excepción generada por `panic` y tomar medidas para controlar el flujo del programa.