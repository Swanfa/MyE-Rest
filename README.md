# My E-Rest

Este proyecto permite realizar pedidos desde una interfaz web, conectada a un servidor Node.js con base de datos SQLite. Los pedidos se guardan y luego se exportan automáticamente a un fichero `.json` sincronizado con OneDrive, para ser utilizados por la cocina.

### Presentación
<img width="250" height="273" alt="qr_presentacion" src="https://github.com/user-attachments/assets/3f0c3395-fd87-4e87-a642-d01f31c36388" />

## ⚙️ Requisitos previos

Para poder utilizar parte de la aplicación web, se necesitan realizar varios pasos previos

- Tener instalado:
  - **Node.js** (versión 16 o superior recomendada)
    - Puedes descargarlo desde  [https://nodejs.org/es]
  - **npm** (incluido con Node.js)

- Comprobar instalación ejecutando en terminal:
  node --version
  npm --version


## 🗃️ Base de datos

La base de datos `database.db` (SQLite) contiene tres tablas principales:

- `Pedidos`: ID, número de mesa, hora, estado (Pendiente, Completado, etc.)
- `Platos`: ID, nombre del plato, tipo (Primero, Segundo, Postre, Bebida)
- `PlatosPedidos`: representa los platos individuales dentro de cada pedido, con posibles modificaciones (sin cebolla, extra salsa, etc.)

## 📤 Exportación automática a JSON

Cada vez que se realiza un pedido, se actualiza automáticamente el fichero:

``` comandas.json ```

Que se ubica en un Sharepoint (OneDrive), el cual está conectado la cocina.

Debido a que para acceder a la interfaz de cocina, se necesita un acceso explícito, permisos y una cuenta de la Comunidad de Madrid o Microsoft 365,

Se ha optado por **crear un fichero de pruebas** llamado ``comandasDePruebas.json``. Ubicado dentro del directorio de Backend.
Una vez realizado el pedido, las comandas se reflejarán de manera automática ahí, y se podrá comprobar el funcionamiento del programa.


## 🚀 Pasos para ejecutar el proyecto

1. Abre la consola y accede al directorio del backend:
   
   cd /ruta/a/tu/proyecto/Backend

2. Instala las dependencias ejecutando:
   npm install

3. Inicia el servidor ejecutando:
   node server.js

   **Si todo ha ido bien, la consola lanzará el siguiente mensaje: `Servidor iniciado en http://localhost:3000`**

4. Abre el fichero `Cliente/index.html` en el navegador para usar la interfaz de cliente.

5. Realiza un pedido.

6. Comprueba en el fichero `comandasDePruebas.json` que se ha concretado el pedido, revisando la hora, la mesa, los platos y el número de comanda.

## 🧪 Prueba rápida

1. En la web del cliente, selecciona una mesa y añade platos al carrito
2. Personaliza un plato
3. Finaliza el pedido
4. Verifica que el fichero `comandasDePruebas.json` se actualizó con el nuevo pedido.
