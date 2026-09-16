# Entrega Final — Ecosistema de Automatización IA Autónomo

## Nexo Digital: Pipeline de Contenidos para Redes Sociales

**Alumna:** Ximena Basualdo  
**Comisión:** AI Automation — Prof. Julián Nuñez  
**Institución:** Coderhouse  
**Fecha:** Septiembre 2026

---

## Caso de Uso

Nexo Digital es una agencia de marketing digital ficticia para pequeños negocios. El sistema automatiza la generación de borradores de contenido para redes sociales a partir de "ideas semilla", con supervisión humana antes de la publicación.

## Stack Tecnológico

| Categoría | Tecnología |
|-----------|-----------|
| Orquestador | n8n (self-hosted cloud) |
| Base de datos | Airtable — Base: TP-Pipeline de Contenidos, Tabla: Centro de Control |
| Procesamiento IA | OpenAI GPT-4o-mini (JSON mode, 500 max tokens) |
| Canal de salida | Gmail (OAuth2) |

## Flujo del Sistema

```
Trigger Horario → Leer Ideas Pendientes (Airtable) → Validar Idea Semilla
  ├─ TRUE → Generar Borrador IA (OpenAI) 
  │    ├─ OK → Guardar Borrador en Airtable → Notificar por Gmail (HITL)
  │    └─ ERROR → Registrar Error en Airtable (Estado: Rechazado)
  └─ FALSE → Marcar Sin Datos
```

## Entregables (5 criterios — 20% cada uno)

| # | Entregable | Archivo |
|---|-----------|---------|
| 1 | Diagrama de Arquitectura | `01_Diagrama_Arquitectura_NexoDigital.pdf` |
| 2 | Manual Operativo de Datos | `02_Manual_Operativo_Datos_NexoDigital.pdf` |
| 3 | Matriz de Optimización de Costos | `03_Matriz_Costos_NexoDigital.pdf` |
| 4 | Documentación de Seguridad y Resiliencia | `04_Seguridad_Resiliencia_NexoDigital.pdf` |
| 5 | Dashboard de Control | [Airtable Shared View](https://airtable.com/app8jfWqWSe6sUqeL) |

## Archivos Técnicos

- `NexoDigital_workflow_n8n.json` — JSON exportado del flujo n8n completo
- `evidencias/` — Screenshots de evidencia del flujo ejecutado

## Base de Datos (modo lectura)

[Airtable — Centro de Control](https://airtable.com/app8jfWqWSe6sUqeL)
