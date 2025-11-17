# Índice de Documentación - DomiChat n8n Workflows

## 📊 Resumen General

**Total de workflows**: 18
**Workflows documentados**: 18 (100%)
**Última actualización**: 2025-11-17

---

## 🗂️ Estructura de Documentación

### 📱 Clientes (7 workflows)

| # | Nombre | ID | Estado | Documentación |
|---|--------|-----|--------|---------------|
| 1 | Flujo Principal | vZz3KSWmbZa2xPyx | ✅ Activo | [📄 Ver docs](clientes-0001-flujo-principal.md) |
| 2 | Crear Pedido | Mdl3DHroFQwCDQKf | ⚪ Inactivo | [📄 Ver docs](clientes-0002-crear-pedido.md) |
| 3 | Broadcast Domiciliarios | Qt35dLh0xdcGB6jT | ⚪ Inactivo | [📄 Ver docs](clientes-0003-broadcast-domiciliarios.md) |
| 4 | Procesar Ventana Ofertas | J7IDbKTkclpin309 | ⚪ Inactivo | [📄 Ver docs](clientes-0004-procesar-ventana-ofertas.md) |
| 5 | Aceptar Contraoferta | zmw8Cn9ZXgya8m1g | ⚪ Inactivo | [📄 Ver docs](clientes-0005-aceptar-contraoferta.md) |
| 6 | Procesar Contraoferta | 9b32I1Ehoz1UhyEA | ⚪ Inactivo | [📄 Ver docs](clientes-0006-procesar-contraoferta.md) |
| 7 | Rechazar Contraoferta | Dz6rZbVpMY2fGNI5 | ⚪ Inactivo | [📄 Ver docs](clientes-0007-rechazar-contraoferta.md) |

### 🚚 Domiciliarios (5 workflows)

| # | Nombre | ID | Estado | Documentación |
|---|--------|-----|--------|---------------|
| 1 | Flujo Principal | MKNuC0q1F3Sh6K6Q | ✅ Activo | [📄 Ver docs](domiciliarios-0001-flujo-principal.md) |
| 2 | Aceptar Pedido | ZlGuD4CfbuDS4EMR | ⚪ Inactivo | [📄 Ver docs](domiciliarios-0002-aceptar-pedido.md) |
| 3 | Contraofertar Pedido | HzK6mbnjJfsRlNyW | ⚪ Inactivo | [📄 Ver docs](domiciliarios-0003-contraofertar-pedido.md) |
| 4 | Validar Entrega | qERWYLB6k0hZ7k4s | ⚪ Inactivo | [📄 Ver docs](domiciliarios-0004-validar-entrega.md) |
| 5 | Cambiar Estado | 3qKyLhg7cDGi1Ijs | ⚪ Inactivo | [📄 Ver docs](domiciliarios-0005-cambiar-estado.md) |

### 🛠️ Utilidades (6 workflows)

| # | Nombre | ID | Estado | Documentación |
|---|--------|-----|--------|---------------|
| 1 | Backup Workflows | (TBD) | ✅ Activo | [📄 Ver docs](utilidades-0001-backup-workflows.md) |
| 2 | Control de Errores | tCJVhMSfqtz6Lsv2 | ✅ Activo | [📄 Ver docs](utilidades-0002-control-notificacion-errores.md) |
| 3 | Deploy QA → Prod | (TBD) | ⚪ Inactivo | [📄 Ver docs](utilidades-0003-deploy-qa-to-production.md) |
| 4 | Borrar Memoria | CY132083QPsn1AYm | ⚪ Inactivo | [📄 Ver docs](utilidades-0004-borrar-memoria-agente.md) |
| 5 | Extraer Credenciales | txbu5tXSsbm0OFqL | ⚪ Inactivo | [📄 Ver docs](utilidades-0005-extraer-credenciales.md) |
| 6 | Dashboard DomiChat | (TBD) | ⚪ Inactivo | [📄 Ver docs](utilidades-0006-dashboard-domichat.md) |

---

## 📖 Documentos Principales

- **[README.md](../../README.md)** - Índice general del repositorio
- **[DEPENDENCIES.md](../DEPENDENCIES.md)** - Mapa de dependencias entre flujos
- **[TECHNICAL_SUMMARY.md](../TECHNICAL_SUMMARY.md)** - Análisis técnico consolidado
- **[INDEX.html](../INDEX.html)** - Documentación interactiva HTML

---

## 🎯 Nivel de Detalle

### Documentación Exhaustiva (★★★★★)
- Clientes: Flujo Principal
- Domiciliarios: Flujo Principal
- Utilidades: Control de Errores

### Documentación Completa (★★★★)
- Domiciliarios: Aceptar Pedido, Contraofertar, Validar Entrega
- Clientes: Crear Pedido, Broadcast, Procesar Ventana

### Documentación Estándar (★★★)
- Resto de workflows

---

## 🔍 Búsqueda Rápida

### Por Función

**Gestión de Pedidos**:
- [Clientes: Crear Pedido](clientes-0002-crear-pedido.md)
- [Domiciliarios: Aceptar Pedido](domiciliarios-0002-aceptar-pedido.md)
- [Clientes: Procesar Ventana Ofertas](clientes-0004-procesar-ventana-ofertas.md)

**Contraofertas**:
- [Domiciliarios: Contraofertar](domiciliarios-0003-contraofertar-pedido.md)
- [Clientes: Procesar Contraoferta](clientes-0006-procesar-contraoferta.md)
- [Clientes: Aceptar Contraoferta](clientes-0005-aceptar-contraoferta.md)
- [Clientes: Rechazar Contraoferta](clientes-0007-rechazar-contraoferta.md)

**Entregas**:
- [Domiciliarios: Validar Entrega](domiciliarios-0004-validar-entrega.md)

**Utilidades**:
- [Control de Errores](utilidades-0002-control-notificacion-errores.md)
- [Backup](utilidades-0001-backup-workflows.md)
- [Deploy](utilidades-0003-deploy-qa-to-production.md)

### Por Integración

**Supabase**: Todos los flujos de clientes y domiciliarios
**Redis**: Flujos principales (clientes y domiciliarios)
**WhatsApp**: Flujos principales + notificaciones
**Google Gemini**: Flujos principales (agentes AI)
**Google Sheets**: Control de errores
**Telegram**: Control de errores
**GitHub**: Backup de workflows

---

**Generado**: 2025-11-17
**Versión**: 1.0
