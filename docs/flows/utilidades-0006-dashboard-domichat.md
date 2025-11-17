# 0006 Utilidades Dashboard DomiChat

## INFORMACIÓN GENERAL

| Campo | Valor |
|-------|-------|
| **Nombre** | 0006 Utilidades Dashboard DomiChat |
| **Estado** | ⚪ Inactivo |
| **Trigger** | Webhook / Manual |
| **Análisis** | Parcial (archivo muy grande - análisis completo no disponible) |

---

## PROPÓSITO

Dashboard de **métricas y monitoreo** del sistema DomiChat.

### Funcionalidades Esperadas
1. Visualización de KPIs del sistema
2. Estadísticas de pedidos
3. Métricas de domiciliarios
4. Performance del sistema

---

## MÉTRICAS PROBABLES

### Pedidos
- Total de pedidos por estado
- Pedidos por día/semana/mes
- Tasa de completación
- Tiempo promedio de entrega
- Valor promedio de pedidos

### Domiciliarios
- Domiciliarios activos vs inactivos
- Calificación promedio
- Pedidos completados por domiciliario
- Earnings por domiciliario

### Clientes
- Nuevos clientes por período
- Clientes recurrentes
- Satisfacción del cliente

### Sistema
- Workflows activos
- Errores por día
- Tiempo de respuesta promedio

---

## TECNOLOGÍA

**Probable Stack**:
- Queries a Supabase para datos
- Agregaciones y cálculos
- Generación de HTML/Dashboard
- Posible integración con Google Sheets

---

## RECOMENDACIONES

### Para Análisis Completo
1. Leer archivo en fragmentos
2. Analizar nodos por secciones
3. Documentar queries principales
4. Identificar visualizaciones

### Alternativas
- Migrar a herramienta especializada (Looker Studio, Metabase)
- Crear dashboard en Supabase directamente
- API endpoints para datos + Frontend separado

---

**Documentado por**: Claude (Anthropic)
**Fecha**: 2025-11-17
**Estado**: Análisis parcial - Archivo demasiado grande para análisis completo
**Nota**: Se requiere análisis fragmentado para documentación completa
