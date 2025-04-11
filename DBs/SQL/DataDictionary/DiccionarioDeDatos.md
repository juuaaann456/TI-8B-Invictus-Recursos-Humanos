# Gymin - Data Dictionary

📅 *Generado el 2025-04-10*

## Índice alfabético

- [tbb_areas](#tbb_areas)
- [tbb_colaboradores](#tbb_colaboradores)
- [tbb_horarios](#tbb_horarios)
- [tbd_quejas_sugerencias](#tbd_quejas_sugerencias)

---

## tbb_areas

**Descripción:** Clasificación o agrupación que organiza elementos relacionados dentro del sistema según características compartidas.  
**Tipo naturaleza:** Conceptual  
**Tipo nivel dependencia:** Débil

| Column name        | DataType     | PK   | NN   | UQ   | BIN  | UN   | ZF   | AI   | Default | Comment |
|--------------------|--------------|------|------|------|------|------|------|------|---------|---------|
| ID                 | INT          | ✅   | ✅   |      |      |      |      | ✅   |         | Identificador único auto-incremental para cada registro. |
| Nombre             | VARCHAR(80)  |      |      |      |      |      |      |      | NULL    | Nombre del área (máx. 80 caracteres). |
| Descripcion        | TEXT         |      |      |      |      |      |      |      | NULL    | Descripción detallada del área. |
| Sucursal_ID        | INT          |      |      |      |      |      |      |      | NULL    | Identificador de la sucursal asociada. |
| Estatus            | TINYINT      |      |      |      |      |      |      |      | NULL    | Estado actual del área (0-255). |
| Fecha_Registro     | DATETIME     |      |      |      |      |      |      |      | NULL    | Fecha de registro del área. |
| Fecha_Actualizacion| DATETIME     |      |      |      |      |      |      |      | NULL    | Fecha de la última actualización. |

---

## tbb_colaboradores

**Descripción:** Persona que trabaja en el gimnasio en algún rol (instructor, recepcionista, etc.).  
**Tipo naturaleza:** Mixta  
**Tipo nivel dependencia:** Fuerte  
**Tipo clasificación:** Entidad

| Column name | DataType     | PK   | NN   | UQ   | BIN  | UN   | ZF   | AI   | Default | Comment |
|-------------|--------------|------|------|------|------|------|------|------|---------|---------|
| ID          | INT          | ✅   | ✅   |      |      |      |      | ✅   |         | Identificador único auto-incremental. |
| Nombre      | VARCHAR(80)  |      |      |      |      |      |      |      | NULL    | Nombre del colaborador. |
| Rol         | VARCHAR(50)  |      |      |      |      |      |      |      | NULL    | Rol del colaborador (Instructor, etc.). |
| Email       | VARCHAR(100) |      |      |      |      |      |      |      | NULL    | Correo electrónico. |
| Telefono    | VARCHAR(20)  |      |      |      |      |      |      |      | NULL    | Número telefónico de contacto. |

---

## tbb_horarios

**Descripción:** Información sobre horarios asignados a colaboradores y actividades.  
**Tipo naturaleza:** Temporal  
**Tipo nivel dependencia:** Fuerte  
**Tipo clasificación:** Entidad

| Column name  | DataType    | PK   | NN   | UQ   | BIN  | UN   | ZF   | AI   | Default | Comment |
|--------------|-------------|------|------|------|------|------|------|------|---------|---------|
| ID           | INT         | ✅   | ✅   |      |      |      |      | ✅   |         | Identificador único. |
| Colaborador_ID | INT       |      |      |      |      |      |      |      | NULL    | ID del colaborador. |
| Dia          | VARCHAR(10) |      |      |      |      |      |      |      | NULL    | Día de la semana. |
| Hora_Inicio  | TIME        |      |      |      |      |      |      |      | NULL    | Hora de inicio. |
| Hora_Fin     | TIME        |      |      |      |      |      |      |      | NULL    | Hora de fin. |

---

## tbd_quejas_sugerencias

**Descripción:** Quejas y sugerencias realizadas por usuarios del gimnasio.  
**Tipo naturaleza:** Mixta  
**Tipo nivel dependencia:** Débil

| Column name     | DataType    | PK   | NN   | UQ   | BIN  | UN   | ZF   | AI   | Default | Comment |
|------------------|-------------|------|------|------|------|------|------|------|---------|---------|
| ID               | INT         | ✅   | ✅   |      |      |      |      | ✅   |         | Identificador único. |
| Tipo             | VARCHAR(50) |      |      |      |      |      |      |      | NULL    | Tipo de queja o sugerencia. |
| Descripcion      | TEXT        |      |      |      |      |      |      |      | NULL    | Detalles de la queja o sugerencia. |
| Fecha_Registro   | DATETIME    |      |      |      |      |      |      |      | NULL    | Fecha en que fue registrada. |
