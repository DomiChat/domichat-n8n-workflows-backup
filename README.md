# DomiChat n8n Workflows - Documentación Técnica

## 📋 Resumen Ejecutivo

Este repositorio contiene los workflows de automatización de **DomiChat**, un sistema de delivery/domicilios operado vía WhatsApp en Colombia. El sistema conecta clientes que necesitan productos con domiciliarios disponibles para entregarlos, utilizando n8n como motor de automatización y agentes AI conversacionales.

### Estadísticas del Sistema

| Métrica | Valor |
|---------|-------|
| **Total de Workflows** | 18 |
| **Workflows Activos** | 3 |
| **Workflows Inactivos** | 15 (sub-workflows y utilidades) |
| **Líneas de Código** | ~15,000+ (estimado en nodos) |
| **Integraciones** | WhatsApp, Supabase, Redis, Google Gemini, Google Sheets, Telegram, GitHub |
| **Última Actualización** | 2025-11-17 |

---

## 🗂️ Estructura del Repositorio

```
domichat-n8n-workflows-backup/
├── clientes/                   # 7 workflows - Flujos de clientes
├── domiciliarios/              # 5 workflows - Flujos de domiciliarios
├── utilidades/                 # 6 workflows - Utilidades y mantenimiento
└── docs/                       # Documentación técnica
    ├── DEPENDENCIES.md         # Mapa de dependencias entre flujos
    ├── flows/                  # Documentación individual de cada flujo
    └── diagrams/               # Diagramas (futuro)
```

---

## 📚 Índice de Flujos

### 🛍️ Clientes (7 workflows)

| Nombre | Estado | Descripción |
|--------|--------|-------------|
| **0001 Flujo Principal** | ✅ Activo | Agente AI conversacional que gestiona creación de pedidos vía WhatsApp |
| **0002 Crear Pedido** | ⚪ Inactivo | Crea pedido y abre ventana de ofertas |
| **0003 Broadcast Domiciliarios** | ⚪ Inactivo | Notifica domiciliarios disponibles |
| **0004 Procesar Ventana Ofertas** | ⚪ Inactivo | Evalúa ofertas y selecciona mejor domiciliario |
| **0005 Aceptar Contraoferta** | ⚪ Inactivo | Procesa aceptación de contraoferta |
| **0006 Procesar Contraoferta** | ⚪ Inactivo | Gestiona contraoferta de domiciliario |
| **0007 Rechazar Contraoferta** | ⚪ Inactivo | Procesa rechazo de contraoferta |

### 🚚 Domiciliarios (5 workflows)

| Nombre | Estado | Descripción | Documentación |
|--------|--------|-------------|---------------|
| **0001 Flujo Principal** | ✅ Activo | Agente AI que procesa comandos (aceptar, contraofertar, entregar) | [📄 Ver docs](docs/flows/domiciliarios-0001-flujo-principal.md) |
| **0002 Aceptar Pedido** | ⚪ Inactivo | Registra aceptación de pedido | [📄 Ver docs](docs/flows/domiciliarios-0002-aceptar-pedido.md) |
| **0003 Contraofertar Pedido** | ⚪ Inactivo | Registra contraoferta con valor mayor |  |
| **0004 Validar Entrega** | ⚪ Inactivo | Valida código y marca como entregado |  |
| **0005 Cambiar Estado** | ⚪ Inactivo | Alterna Activo/Inactivo |  |

### 🛠️ Utilidades (6 workflows)

| Nombre | Estado | Descripción | Documentación |
|--------|--------|-------------|---------------|
| **0001 Backup Workflows** | ✅ Activo | Backup automático diario (3 AM) a GitHub |  |
| **0002 Control de Errores** | ✅ Activo | Error workflow global con notificaciones | [📄 Ver docs](docs/flows/utilidades-0002-control-notificacion-errores.md) |
| **0003 Deploy QA → Prod** | ⚪ Inactivo | Migra workflows entre ambientes |  |
| **0004 Borrar Memoria** | ⚪ Inactivo | Limpia sesiones Redis |  |
| **0005 Extraer Credenciales** | ⚪ Inactivo | Exporta credenciales n8n |  |
| **0006 Dashboard DomiChat** | ⚪ Inactivo | Dashboard de métricas |  |

---

## 🏗️ Arquitectura del Sistema

### Flujo Completo de un Pedido

```
1. Cliente envía WhatsApp → "quiero 1 hamburguesa de El Corral"
2. Agente AI solicita: dirección, valor ofrecido
3. Sistema crea pedido y abre ventana de 3-5 minutos
4. Domiciliarios envían aceptaciones/contraofertas
5. Sistema selecciona mejor oferta (rating + tiempo)
6. Cliente confirma → Pedido asignado
7. Domiciliario entrega y valida con código de verificación
8. Sistema marca como entregado y notifica cliente
```

### Stack Tecnológico

| Capa | Tecnología | Uso |
|------|------------|-----|
| **Orquestación** | n8n | Motor de workflows |
| **Base de Datos** | Supabase (PostgreSQL) | Almacenamiento de datos |
| **Cache/Memoria** | Redis | Sesiones conversacionales (TTL 24h) |
| **AI/LLM** | Google Gemini | Agentes conversacionales |
| **Mensajería** | WhatsApp Business API | Canal principal |
| **Logging** | Google Sheets | Registro de errores |
| **Alertas** | Telegram Bot | Notificaciones al equipo |
| **Versionado** | GitHub | Backup automático |

---

## 📖 Documentación Detallada

### Documentos Principales

- **[DEPENDENCIES.md](docs/DEPENDENCIES.md)** - Mapa completo de dependencias entre flujos
- **[Flujos Documentados](docs/flows/)** - Documentación exhaustiva de flujos individuales

### Conceptos Clave

- **Ventana de Ofertas**: Período de 3-5 minutos donde domiciliarios pueden proponer
- **Agentes AI**: Conversacional con Google Gemini, memoria en Redis
- **Código de Verificación**: Sistema de 4 dígitos para confirmar entregas
- **Sub-workflows**: Patrón de orquestación con flujo principal + sub-flujos especializados

---

## ⚙️ Configuración

### Variables de Entorno

```bash
WHATSAPP_API_VERSION=v21.0
WHATSAPP_CLIENT_PHONE_NUMBER_ID=xxxxx
WHATSAPP_DELIVERY_PHONE_NUMBER_ID=xxxxx
TZ=America/Bogota
```

### Credenciales Necesarias

- WhatsApp Business API (Clientes y Domiciliarios)
- Supabase QA
- Redis QA
- Google AI Studio QA
- Google Sheets account
- Telegram Notificaciones DomiChat

---

## 🔧 Mantenimiento

### Backup Automático

Diario a las 3:00 AM vía `0001 Utilidades Backup Workflows`

### Monitoreo de Errores

`0002 Utilidades Control de Errores` registra en Google Sheets y notifica vía Telegram

---

## 📞 Contacto

- **GitHub Issues**: [DomiChat/domichat-n8n-workflows-backup](https://github.com/DomiChat/domichat-n8n-workflows-backup/issues)
- **Telegram**: Chat ID 209571519

---

**Generado por**: Claude (Anthropic)
**Fecha**: 2025-11-17
**Workflows Analizados**: 16 de 18
