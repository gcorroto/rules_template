# Guía para Plantillas de Cursor

Esta guía explica cómo crear, actualizar y usar plantillas para modos personalizados en Cursor.

## Estructura de Directorios

Las plantillas y configuraciones de Cursor se organizan de la siguiente manera:

```
.cursor/
├── config.json         # Configuración principal que define los modos
├── modes/              # Directorio que contiene plantillas para diferentes modos
│   ├── chat-mode.mdc   # Plantilla para modo Chat
│   ├── write-mode.mdc  # Plantilla para modo Write
│   └── mcp-mode.mdc    # Plantilla para modo MCP
└── rules/              # Reglas generales utilizadas por los diferentes modos
    ├── rules.mdc
    ├── memory.mdc
    ├── plan.mdc
    ├── implement.mdc
    └── ...
```

## Formato de Plantilla

Cada plantilla (archivo `.mdc`) debe seguir este formato:

```
---
description: Descripción breve del modo
globs: 
alwaysApply: false
---
---
description: Instrucciones detalladas para el modo
mode: nombre_del_modo
---
# Instrucciones para Modo [Nombre]

[Instrucciones detalladas sobre qué debe hacer el modo]

## Principios del Modo
- [Principio 1]
- [Principio 2]
- ...

## Estructura
- [Elemento de estructura 1]
- [Elemento de estructura 2]
- ...
```

## Configuración de Modos

El archivo `config.json` define qué plantillas y reglas se cargan para cada modo:

```json
{
  "version": 1,
  "modes": {
    "nombre_del_modo": {
      "template": "ruta/a/plantilla.mdc",
      "rules": [
        "ruta/a/regla1.mdc",
        "ruta/a/regla2.mdc"
      ]
    }
  },
  "defaultMode": "modo_predeterminado"
}
```

## Creación de Nuevo Modo

Para crear un nuevo modo personalizado:

1. Crea un nuevo archivo `.mdc` en el directorio `.cursor/modes/`
2. Sigue el formato de plantilla descrito arriba
3. Actualiza el archivo `.cursor/config.json` para incluir el nuevo modo
4. Especifica qué reglas deben cargarse para ese modo

## Actualización de Modos Existentes

Para actualizar un modo existente:

1. Edita el archivo `.mdc` correspondiente en `.cursor/modes/`
2. Si es necesario, actualiza las reglas asociadas en `.cursor/config.json`

## Solución de Problemas

Si las plantillas no se están aplicando correctamente:

1. Verifica que el archivo `.cursor/config.json` existe y tiene el formato correcto
2. Asegúrate de que las rutas a las plantillas y reglas son correctas
3. Comprueba que los archivos `.mdc` tienen el formato adecuado con los encabezados YAML
4. Reinicia Cursor para que los cambios surtan efecto