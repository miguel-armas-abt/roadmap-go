# CONFIGURACIÓN

[← Regresar a notas](../../README.md) <br>

----

## ⚙️ Instalar go
> - [Descargar](https://go.dev/dl/) para `Microsoft Windows` e instalar con ayuda del wizard.
> - Agregar la variable de entorno `GOROOT` = `C:\dev-environment\go\go1.21.4`
> - Referenciar el binario en el `Path`: `%GOROOT%\bin`
> - Agregar la variable de entorno `GOBIN` = `C:\dev-environment\go\go1.21.4\bin`

## ⚙️ Instalar gopls, goimports, staticcheck, gofumpt & delve
Se instalarán en la ruta `GOBIN` definida en la variable de entorno.
```shell
go install golang.org/x/tools/gopls@latest
go install golang.org/x/tools/cmd/goimports@latest
go install mvdan.cc/gofumpt@latest
go install -v github.com/go-delve/delve/cmd/dlv@latest
```

## ⚙️ Limpiar la caché de módulos
```shell
go clean -modcache
```

## ⚙️ Deshabilitar proxy
```shell
go env -w GOPROXY=direct
```