# Linda

Proyecto de programación distribuida en Java que implementa un espacio de tuplas tipo Linda. El sistema permite que varios clientes se conecten a un servidor y realicen operaciones sobre tuplas, como insertar, eliminar y leer datos.

## Requisitos

- Java Development Kit (JDK) 11 o superior.
- Varias terminales o máquinas dentro de la misma red si se quiere probar la distribución.

## Estructura principal

- `MainServidor`: punto de entrada para iniciar el servidor Linda o uno de los servidores de tuplas.
- `MainCliente`: punto de entrada para iniciar un cliente.
- `ServidorLinda`: servidor principal que acepta conexiones de clientes.
- `Servidores`: servidores que almacenan las tuplas y la réplica.
- `BaseDeDatos`: gestión de las tuplas almacenadas.

## Configuración de red

La dirección del servidor está definida en `src/linda/Conexion.java` mediante la constante `HOST`. Actualmente apunta a `172.16.4.35`. Cámbiala por la dirección IP del equipo donde se ejecute `MainServidor`.

El servidor Linda utiliza el puerto `1234`. Los servidores de tuplas utilizan los puertos `4321`, `5678`, `9101` y `6587` para la réplica.

## Compilar

Desde la raíz del proyecto:

```bash
javac -d bin src/module-info.java src/linda/*.java
```

La carpeta `bin/` contiene archivos generados y está excluida del repositorio mediante `.gitignore`.

## Ejecutar

Primero, inicia el servidor:

```bash
java -cp bin linda.MainServidor
```

Cuando lo solicite, elige una opción válida: `linda`, `tuplas1`, `tuplas2`, `tuplas3` o `replica`.

En otra terminal, inicia el cliente:

```bash
java -cp bin linda.MainCliente
```

El cliente mostrará las operaciones disponibles: `PostNote`, `RemoveNote`, `ReadNote` y salir.

## Estado del proyecto

Proyecto académico desarrollado para la asignatura de Programación de Servicios y Procesos.
