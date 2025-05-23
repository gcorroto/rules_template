Para integrar el rules_template en un proyecto existente y garantizar que funcione correctamente, sigue estos pasos:

1. Configura la estructura del directorio
Asegúrate de que la estructura del directorio de tu proyecto coincida con la recomendada en el rules_template. Si ya tienes una estructura existente, adapta las carpetas y archivos para que se alineen con las siguientes:

````
project_root/
├── docs/
│   ├── literature/
│   ├── architecture.md
│   ├── technical.md
│   └── product_requirement_docs.md
├── tasks/
│   ├── rfc/
│   ├── active_context.md
│   ├── tasks_plan.md
├── src/
├── test/
├── utils/
├── config/
├── data/
```

2. Coloca los archivos de reglas
Copia los archivos de reglas del rules_template en las ubicaciones correspondientes dentro de tu proyecto:

Para Cursor:

Coloca los archivos en rules.
Asegúrate de incluir los archivos rules.mdc, plan.mdc, implement.mdc, debug.mdc, memory.mdc, y directory-structure.mdc.

3. Configura los enlaces simbólicos
Si tu sistema operativo lo permite, crea enlaces simbólicos para evitar duplicación de archivos. Por ejemplo:

```
ln -s .cursor/rules/memory.mdc
ln -s .cursor/rules/plan.mdc

````

Esto asegura que cualquier cambio en un archivo se refleje automáticamente en todos los sistemas.

4. Carga las reglas bajo demanda
Configura tu entorno para cargar solo las reglas necesarias según el modo. Por ejemplo:

En Cursor, utiliza la configuración avanzada para cargar reglas específicas del modo.
1. Actualiza la documentación
Asegúrate de que los archivos de documentación (architecture.md, technical.md, product_requirement_docs.md, etc.) estén actualizados con la información de tu proyecto. Si ya tienes documentación existente, combínala con los archivos del rules_template.

1. Configura los modos personalizados
Sigue las instrucciones del rules_template para configurar los modos personalizados en Cursor. Por ejemplo:

Modo Chat:
Instrucciones personalizadas: "Solicita aclaraciones y seguimientos profundos tanto como sea posible..."
Modo Write:
Instrucciones personalizadas: "Crear y editar archivos y directorios..."
Modo MCP:
Instrucciones personalizadas: "Ejecute servidores MCP conectados..."
1. Integra el banco de memoria
Asegúrate de que el banco de memoria común esté configurado para mantener el contexto entre los asistentes de IA. Esto incluye:

Actualizar memory.mdc con información relevante del proyecto.
Usar active_context.md para capturar el estado actual del desarrollo.
8. Prueba la configuración
Realiza pruebas para asegurarte de que las reglas y modos funcionan correctamente en tu proyecto. Por ejemplo:

Ejecuta tareas en Cursor y verifica que las reglas se carguen correctamente.
1. Documenta el proceso
Actualiza el archivo tasks_plan.md con los pasos realizados para integrar el rules_template en tu proyecto. Esto servirá como referencia para futuros desarrolladores.
