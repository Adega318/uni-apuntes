# Apple
Se desarrolla desde xcode con necesidad de pago para la instalación de la aplicación.
# Android
Para el desarrollo en android se puede realizar mediante un SDK
# Fluter
Método de desarrollo genérica que solo requiere de la compilación final en la plataforma correspondiente, siendo compatible con IOs, Android, desktop y web.
## Ejecución
La ejecución de la aplicación se puede realizar de múltiples maneras, hacemos uso de emuladores.
## Concurrencia
Los threads son llamados Isolates, también tenemos funciones asíncronas (async). Las funciones asíncronas usan un modelo de concurrencia colaborativo en el que la cpu es cedida, lo que debe de ser controlado (buenas para problemas de entrada salida).
### Async
Las funciones asíncronas se ejecutan de manera concurrente y devuelven un objeto future y permiten el encadenado de las mismas.
## Widget
tenemos dos tipos de widget, estáticos que no requieren actualización y dinámicos que cambian.
## Set up 
```shell
flutterdev
```
// hot restart and hot reload