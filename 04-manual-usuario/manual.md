# 📖 Manual de Usuario — AutoMaster

*(Nota: Guarda tus capturas de pantalla en `documentacion/04-manual-usuario/capturas/` y reemplaza los nombres de archivo según corresponda).*

---

## 1. Navegación Pública y Catálogo
1. **Página de Inicio (`PaginaInicio.jsx`):** Al ingresar a la plataforma, el usuario visualiza el banner principal (`fondo-automaster.webp`), accesos directos a categorías y vehículos destacados.
   ![Página de Inicio](./capturas/01-inicio.png)
2. **Catálogo y Filtros (`PaginaCatalogo.jsx` / `PaginaCategorias.jsx`):** Desde la barra superior (`Encabezado.jsx`), el usuario puede navegar por todo el inventario o filtrar por categoría (`PaginaDetalleCategoria.jsx`) y revisar promociones en **Ofertas** (`PaginaOfertas.jsx`).
   ![Catálogo de Vehículos](./capturas/02-catalogo.png)
3. **Detalle del Vehículo (`PaginaDetalleVehiculo.jsx`):** Al hacer clic en cualquier tarjeta (`TarjetaVehiculo.jsx`), se despliega la ficha completa del vehículo con su precio, categoría y botón para añadir al carrito.

---

## 2. Flujo de Compra
1. **Carrito de Compras (`PaginaCarrito.jsx`):** Permite revisar los vehículos seleccionados, ajustar cantidades o eliminar ítems antes de proceder al pago.
   ![Carrito de Compras](./capturas/03-carrito.png)
2. **Finalizar Compra (`PaginaFinalizarCompra.jsx`):** El cliente completa los datos requeridos para procesar la orden.
3. **Resultado de la Operación (`PaginaResultadoCompra.jsx`):** El sistema confirma el estado de la compra mediante `MensajeEstado.jsx`.

---

## 3. Gestión de Cuenta
* En la sección **Cuenta** (`PaginasCuenta.jsx`), los usuarios pueden iniciar sesión con su correo y contraseña o crear una cuenta nueva.

---

## 4. Panel de Administración
1. **Acceso al Módulo (`ModuloAdministrativo.jsx` / `PanelAdministracion.jsx`):** Disponible para usuarios con rol administrador.
   ![Panel Administrativo](./capturas/04-panel-admin.png)
2. **Gestión de Inventario (`InventarioVehiculos.jsx`):** Permite agregar nuevos vehículos al catálogo, editar precios/datos de unidades existentes o eliminar registros.
