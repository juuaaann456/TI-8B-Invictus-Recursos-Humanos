## Colección: contactos

| Campo              | Tipo       | Obligatorio | Valores posibles | Relación | Descripción                                         |
|--------------------|------------|-------------|------------------|----------|-----------------------------------------------------|
| _id                | ObjectId   | Sí          | -                | -        | Identificador único del documento                  |
| nombre_completo    | String     | Sí          | -                | -        | Nombre completo de la persona                      |
| correo             | String     | Sí          | Formato email    | -        | Correo electrónico de contacto                     |
| celular            | String     | No          | Dígitos numéricos| -        | Número de celular del usuario                      |
| comentario         | String     | No          | -                | -        | Comentario ingresado por el usuario                |
| fecha_registro     | ISODate    | Sí          | -                | -        | Fecha y hora de registro del comentario            |
| fecha_actualizacion| ISODate    | Sí          | -                | -        | Fecha y hora de la última actualización del registro|


