# gymin Data Dictionary

*2025-04-10*

## Alphabetic Index

- [tbb_areas](#tbb_areas)
- [tbb_colaboradores](#tbb_colaboradores)
- [tbb_horarios](#tbb_horarios)
- [tbd_quejas_sugerencias](#tbd_quejas_sugerencias)

## tbb_areas

Descripción: Clasificación o agrupación que organiza elementos relacionados dentro del sistema según características compartidas.
Tipo naturaleza: Conceptual
Tipo nivel dependencia: Débil

| Column name          | DataType      | PK  | NN  | UQ  | BIN | UN  | ZF  | AI  | Default | Comment |
|----------------------|---------------|-----|-----|-----|-----|-----|-----|-----|---------|---------|
| ID                   | INT           | ✓   | ✓   |     |     |     |     | ✓   |         | Identificador unico auto-incremental para cada registro en la tabla. \\\\\\n\\\\\\nTipo: Entero \\\\\\n\\\\\\nDominio: Numeros enteros positivos \\\\\\n\\\\\\nComposicion: 1{0-9}* |
| Nombre               | VARCHAR(80)   |     |     |     |     |     |     |     | NULL    | Nombre de la persona, almacenado en una cadena de caracteres de longitud maxima de 80 caracteres.\\nTipo: Cadena de caracteres\\nDominio: Cadena de caracteres con longitud maxima de 80 caracteres\\nComposicion: [A-Za-z0-9_ -./()]{1,80} |
| Descripcion          | TEXT          |     |     |     |     |     |     |     | NULL    | Descripcion detallada del area, almacenada en un campo de texto sin limite de longitud.\\nTipo: Texto\\nDominio: Cadena de caracteres de longitud variable\\nComposicion: [A-Za-z0-9_ -./(),nN]{1,} |
| Sucursal_ID          | INT           |     |     |     |     |     |     |     | NULL    | Identificador de la sucursal asociada con el area.\\nTipo: Entero\\nDominio: Numeros enteros positivos\\nComposicion: 1{0-9}* |
| Estatus              | TINYINT       |     |     |     |     |     |     |     | NULL    | Estado actual del area, con posibles valores numericos que representan estados especificos.\\nTipo: Entero\\nDominio: Valores enteros desde 0 hasta 255\\nComposicion: 0-255 |
| Fecha_Registro       | DATETIME      |     |     |     |     |     |     |     | NULL    | Fecha en la que se registro el area, almacenada en formato date (AAAA-MM-DD).\\nTipo: Fecha\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |
| Fecha_Actualizacion  | DATETIME      |     |     |     |     |     |     |     | NULL    | Fecha de la ultima actualizacion de la area, almacenada en formato date (AAAA-MM-DD).\\nTipo: Fecha\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |

## tbb_colaboradores

Descripcion: Persona que trabaja en el gimnasio, ya sea como instructor, recepcionista, administrador o en otro rol, y que contribuye al funcionamiento y servicios ofrecidos por el gimnasio.
Tipo naturaleza: Mixta      Tipo nivel dependencia: Fuerte      Tipo clasificacion: Entidad  

| Column name          | DataType      | PK  | NN  | UQ  | BIN | UN  | ZF  | AI  | Default | Comment |
|----------------------|---------------|-----|-----|-----|-----|-----|-----|-----|---------|---------|
| ID                   | INT           | ✓   | ✓   |     |     |     |     | ✓   |         | Identificador unico auto-incremental para cada registro en la tabla. \\\\n\\\\nTipo: Entero \\\\n\\\\nDominio: Numeros enteros positivos \\\\n\\\\nComposicion: 1{0-9}* |
| Usuario_Roles_ID     | INT           |     |     |     |     |     |     |     | NULL    | Descripción: Identificador que representa el rol asignado a un usuario dentro del sistema (por ejemplo, administrador, recepcionista, entrenador).\nTipo: Entero (Integer)\nDominio: Números enteros positivos correspondientes a roles predefinidos en el catálogo de roles\nComposición: {1–3 dígitos}\nRestricciones: Valor requerido, debe existir en la tabla de roles. No se permiten valores negativos ni nulos. |
| Horario_ID           | INT           |     |     |     |     |     |     |     | NULL    | Descripción: Horario de trabajo del colaborador dentro del gimnasio, almacenada en formato datetime (AAAA-MM-DD HH:mm:ss).\\\\nTipo: DateTime\\\\nDominio: Fecha/hora valida desde el ano 1900 hasta la fecha actual\\\\nComposicion: {4-digitos-Ano}{2-digitos-Mes}{2-digitos-Dia} {space} {2-digitos-Hora}:{2-digitos-Minutos}:{2-digitos-Segundos} (UTC) |
| Especialidad         | VARCHAR(50)   |     |     |     |     |     |     |     | NULL    | Descripción: Área de conocimiento, disciplina o tipo de actividad física que domina un colaborador dentro del gimnasio.\nTipo: Catálogo\nDominio: Texto alfabético representando una disciplina válida (ej. Yoga, CrossFit, Spinning)\nComposición: {Texto}{Espacio opcional}{Texto} (máx. 100 caracteres)\nRestricciones: Valor único, sin caracteres especiales inválidos. Puede contener letras, espacios y acentos. |
| Estatus              | TINYINT(1)    |     |     |     |     |     |     |     | NULL    | Estado actual del colaborador,almacenado como un valor binario.\\\\nTipo: Binario\\\\nDominio: Valores binarios (0 o 1)\\\\nComposicion: b\\\\\\\\'0\\\\\\\\' o b\\\\\\\\'1\\\\\\\\' |
| Fecha_Registro       | DATETIME      |     | ✓   |     |     |     |     |     |         | Fecha en la que se registro el colaborador en el sistema, almacenada en formato date (AAAA-MM-DD). \\\\\\\\n\\\\\\\\nTipo: Fecha \\\\\\\\n\\\\\\\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual \\\\\\\\n\\\\\\\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |
| Fecha_Actualizacion  | DATETIME      |     | ✓   |     |     |     |     |     |         | Fecha de la ultima actualizacion del colaborador, almacenada en formato date (AAAA-MM-DD). \\\\\\\\n\\\\\\\\nTipo: Fecha \\\\\\\\n\\\\\\\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual \\\\\\\\n\\\\\\\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |

## tbb_horarios

DESCRIPCION: Conjunto de tiempos o periodos especificos en los que se planifican y organizan actividades, citas o eventos dentro del Gym.
TIPO NATURALEZA: Conceptual
TIPO NIVEL DEPENDENCIA: Debil
TIPO CLASIFICACION: Generica

| Column name          | DataType                      | PK  | NN  | UQ  | BIN | UN  | ZF  | AI  | Default | Comment |
|----------------------|-------------------------------|-----|-----|-----|-----|-----|-----|-----|---------|---------|
| ID                   | INT                           | ✓   | ✓   |     |     |     |     | ✓   |         | Identificador unico auto-incremental para cada registro en la tabla.\\nTipo: Entero\\nDominio: Numeros enteros positivos\\nComposicion: 1{0-9}* |
| Tipo                 | ENUM('matutino', 'vespertino', 'especial') |     | ✓   |     |     |     |     |     |         | Estado actual del horario, con posibles valores numéricos que representan estados específicos.  \nTipo: Entero  \nDominio: Valores enteros desde 0 hasta 255  \nComposición: 0-255 |
| Hora_Inicio          | TIME                          |     | ✓   |     |     |     |     |     |         | Hora en la que inicia el horario, almacenada en formato time (HH:MM:SS).\\nTipo: Hora\\nDominio: Hora valida en formato de 24 horas\\nComposicion: {2-digitos-Hora}:{2-digitos-Minutos}:{2-digitos-Segundos} |
| Hora_Fin             | TIME                          |     | ✓   |     |     |     |     |     |         | Hora en la que finaliza el horario, almacenada en formato time (HH:MM:SS).\\nTipo: Hora\\nDominio: Hora valida en formato de 24 horas\\nComposicion: {2-digitos-Hora}:{2-digitos-Minutos}:{2-digitos-Segundos} |
| Fecha_Registro       | DATETIME                      |     | ✓   |     |     |     |     |     |         | Fecha y hora en la que se registro el horario, almacenada en formato datetime (AAAA-MM-DD HH:mm:ss).\\nTipo: DateTime\\nDominio: Fecha/hora valida desde el ano 1900 hasta la fecha actual\\nComposicion: {4-digitos-Ano}{2-digitos-Mes}{2-digitos-Dia} {space} {2-digitos-Hora}:{2-digitos-Minutos}:{2-digitos-Segundos} (UTC) |
| Fecha_Actualizacion  | DATETIME                      |     | ✓   |     |     |     |     |     |         | Fecha de la ultima actualizacion del horario, almacenada en formato datetime (AAAA-MM-DD HH:mm:ss).\\nTipo: DateTime\\nDominio: Fecha/hora valida desde el ano 1900 hasta la fecha actual\\nComposicion: {4-digitos-Ano}{2-digitos-Mes}{2-digitos-Dia} {space} {2-digitos-Hora}:{2-digitos-Minutos}:{2-digitos-Segundos} (UTC) |
| Estatus              | TINYINT                       |     | ✓   |     |     |     |     |     |         | Estado actual del horario, con posibles valores numericos que representan estados especificos.\\nTipo: Entero\\nDominio: Valores enteros desde 0 hasta 255\\nComposicion: 0-255 |

## tbd_quejas_sugerencias

Descripción: Comentarios, quejas o sugerencias proporcionadas por los usuarios o clientes, con el fin de mejorar los servicios, procesos o experiencias en el establecimiento.\\\\nTipo naturaleza: Mixta \\\\nTipo nivel dependencia: Moderada \\\\nTipo clasificación: Entidad

| Column name          | DataType                      | PK  | NN  | UQ  | BIN | UN  | ZF  | AI  | Default | Comment |
|----------------------|-------------------------------|-----|-----|-----|-----|-----|-----|-----|---------|---------|
| ID                   | INT                           | ✓   | ✓   |     |     |     |     | ✓   |         | Identificador unico auto-incremental para cada registro en la tabla. \\\\\\\\n\\\\\\\\nTipo: Entero \\\\\\\\n\\\\\\\\nDominio: Numeros enteros positivos \\\\\\\\n\\\\\\\\nComposicion: 1{0-9}* |
| Usuario_Roles_ID     | INT                           |     |     |     |     |     |     |     | NULL    | Descripción: Identificador que representa el rol asignado a un usuario dentro del sistema (por ejemplo, administrador, recepcionista, entrenador).\\nTipo: Entero (Integer)\\nDominio: Números enteros positivos correspondientes a roles predefinidos en el catálogo de roles\\nComposición: {1–3 dígitos}\\nRestricciones: Valor requerido, debe existir en la tabla de roles. No se permiten valores negativos ni nulos. |
| Sucursal_ID          | INT                           |     |     |     |     |     |     |     | NULL    | Identificador de la sucursal asociada con el area.\\\\nTipo: Entero\\\\nDominio: Numeros enteros positivos\\\\nComposicion: 1{0-9}* |
| Descripcion          | TEXT                          |     | ✓   |     |     |     |     |     |         | Descripcion detallada de la queja, almacenada en un campo de texto sin limite de longitud.\\\\nTipo: Texto\\\\nDominio: Cadena de caracteres de longitud variable\\\\nComposicion: [A-Za-z0-9_ -./(),nN]{1,} |
| Tipo                 | ENUM('sugerencia', 'queja', 'reclamo') |     | ✓   |     |     |     |     |     |         | Estado actual de la queja, con posibles valores numéricos que representan estados específicos. \\nTipo: ENUM \\nDominio: Valores ('sugerencia', 'queja', 'reclamo') \\nComposición: 'sugerencia' - Opinión o recomendación, 'queja' - Expresión de descontento, 'reclamo' - Solicitud formal de resolución.\n |
| Respuesta            | TEXT                          |     |     |     |     |     |     |     | NULL    | Respuesta detallada de la queja, almacenada en un campo de texto sin limite de longitud.\\\\nTipo: Texto\\\\nDominio: Cadena de caracteres de longitud variable\\\\nComposicion: [A-Za-z0-9_ -./(),nN]{1,} |
| Estatus              | ENUM('respondida', 'pendiente', 'archivada') |     | ✓   |     |     |     |     |     |         | Estado actual del elemento, con posibles valores que representan diferentes estados de procesamiento o situación. \\nTipo: ENUM \\nDominio: Valores ('pendiente', 'respondida', 'archivada') \\nComposición: 'pendiente' - Aún no se ha iniciado el proceso, 'en proceso' - En fase de revisión o solución, 'resuelto' - El problema o solicitud ha sido atendido, 'cerrado' - Caso finalizado y cerrado.\n |
| Fecha_registro       | DATETIME                      |     | ✓   |     |     |     |     |     |         | Fecha en la que se registro la queja en el sistema, almacenada en formato date (AAAA-MM-DD). \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\nTipo: Fecha \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |
| Fecha_actualizacion  | DATETIME                      |     | ✓   |     |     |     |     |     |         | Fecha de la ultima actualizacion de la qiueja, almacenada en formato date (AAAA-MM-DD). \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\\\nTipo: Fecha \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\\\nDominio: Fechas validas desde el ano 1900 hasta la fecha actual \\\\\\\\\\\\\\\\\\n\\\\\\\\\\\\\\\\nComposicion: {4-digitos-Ano}-{2-digitos-Mes}-{2-digitos-Dia} |
