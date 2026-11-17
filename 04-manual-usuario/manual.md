# 📖 Manual de Usuario — AutoMaster


## 1. Navegación Pública y Catálogo
1. **Página de Inicio (`PaginaInicio.jsx`):** Al ingresar a la plataforma, el usuario visualiza el banner principal (`fondo-automaster.webp`), accesos directos a categorías y vehículos destacados.
   ![Página de Inicio](" <img width="947" height="473" alt="Captura de pantalla 2026-11-17 120750" src="https://github.com/user-attachments/assets/c117e37b-dc78-4a88-9993-48eb497b5b57" />
")
2. **Catálogo y Filtros (`PaginaCatalogo.jsx` / `PaginaCategorias.jsx`):** Desde la barra superior (`Encabezado.jsx`), el usuario puede navegar por todo el inventario o filtrar por categoría (`PaginaDetalleCategoria.jsx`) y revisar promociones en **Ofertas** (`PaginaOfertas.jsx`).
   ![Catálogo de Vehículos](" <img width="955" height="471" alt="Captura de pantalla 2026-11-17 121107" src="https://github.com/user-attachments/assets/879f91b6-ad22-4e00-b734-9211664e033e" />
")
3. **Detalle del Vehículo (`PaginaDetalleVehiculo.jsx`):** Al hacer clic en cualquier tarjeta (`TarjetaVehiculo.jsx`), se despliega la ficha completa del vehículo con su precio, categoría y botón para añadir al carrito.
("<img width="947" height="468" alt="Captura de pantalla 2026-11-17 121150" src="https://github.com/user-attachments/assets/965a5c5a-d49d-477b-8248-bb376f10ff41" />
")
---

## 2. Flujo de Compra
1. **Carrito de Compras (`PaginaCarrito.jsx`):** Permite revisar los vehículos seleccionados, ajustar cantidades o eliminar ítems antes de proceder al pago.
   ![Carrito de Compras](<img width="950" height="467" alt="Captura de pantalla 2026-11-17 121333" src="https://github.com/user-attachments/assets/fcaff252-68b1-44d4-ab82-47c17e7ea8c5" />
)
2. **Finalizar Compra (`PaginaFinalizarCompra.jsx`):** El cliente completa los datos requeridos para procesar la orden.
3. **Resultado de la Operación (`PaginaResultadoCompra.jsx`):** El sistema confirma el estado de la compra mediante `MensajeEstado.jsx`.

---

## 3. Gestión de Cuenta
* En la sección **Cuenta** (`PaginasCuenta.jsx`), los usuarios pueden iniciar sesión con su correo y contraseña o crear una cuenta nueva.
(<img width="952" height="473" alt="Captura de pantalla 2026-11-17 121419" src="https://github.com/user-attachments/assets/5b1aa4d4-a278-4ff9-a172-71019b5510f7" />
)
---

## 4. Panel de Administración
1. **Acceso al Módulo (`ModuloAdministrativo.jsx` / `PanelAdministracion.jsx`):** Disponible para usuarios con rol administrador.
   ![Panel Administrativo](<img width="957" height="471" alt="Captura de pantalla 2026-11-17 121455" src="https://github.com/user-attachments/assets/000f395a-4cef-4946-a72b-1ad0c219ae18" />
)
2. **Gestión de Inventario (`InventarioVehiculos.jsx`):** Permite agregar nuevos vehículos al catálogo, editar precios/datos de unidades existentes o eliminar registros.
(<img width="957" height="471" alt="Captura de pantalla 2026-11-17 121455" src="https://github.com/user-attachments/assets/e15fa85d-80b7-45b7-9cc1-49cbd993885e" />
)
