# CONFIGURACIÓN

[← Regresar a notas](../../README.md) <br>

----

## ⚙️ Instalar GO
> - [Descargar](https://go.dev/dl/) para `Microsoft Windows` e instalar con ayuda del wizard.
> - Agregar la variable de entorno `GOROOT` = `C:\dev-environment\go\go1.21.4`
> - Referenciar el binario en el `Path`: `%GOROOT%\bin`
> - Agregar la variable de entorno `GOBIN` = `C:\dev-environment\go\go1.21.4\bin`

## ⚙️ Instalar GOPLS
Gopls se instalará en la ruta `GOBIN` definida en la variable de entorno.
```shell
go install golang.org/x/tools/gopls@latest
```

## ⚙️ Limpiar la caché de módulos
```shell
go clean -modcache
```