## HU01 Registrar clientes sin duplicaciones

Como integrante del Área Comercial, quiero registrar y consultar los datos de un cliente, para reutilizar información confiable al crear sus proyectos.

Prioridad alta. Entidad principal Cliente. Dependencia ninguna.

Criterios de aceptación

1. Dado un usuario comercial habilitado, cuando registra razón social, CUIT y correo válido, el sistema crea un id\_cliente único y confirma el alta.
2. Si falta un campo obligatorio o el correo tiene formato inválido, se informa el motivo y no se confirma el alta.
3. Si el CUIT normalizado ya existe, se ofrece consultar el cliente existente y no se crea un duplicado. El CUIT se almacena como String; no se usa para cálculos.
4. La búsqueda por razón social o CUIT permite recuperar el registro y vincularlo a un proyecto.

La unicidad del CUIT y los campos obligatorios se agregan como reglas de validación de la primera versión. No se afirma validación frente a organismos externos.

## HU02 Planificar proyectos y asignar tareas

Como Analista y Coordinación, quiero crear un proyecto vinculado a un cliente y asignar requerimientos y tareas a responsables habilitados, para organizar el trabajo con alcance y fechas definidos.

Prioridad alta. Entidades Proyecto, Cliente, Requerimiento, Tarea y Usuario. Depende de HU01 y de usuarios habilitados.

Criterios de aceptación

1. Todo proyecto tiene id\_cliente existente, nombre, descripción, fecha de inicio y fecha de entrega; la entrega no puede ser anterior al inicio.
2. Cada tarea se vincula a un proyecto y a un responsable activo; su fecha límite queda dentro del período del proyecto. Una excepción requiere ajustar y aprobar el plan antes de guardar.
3. Los requerimientos se registran con su prioridad y condición de aprobado. Un requerimiento no aprobado no se considera parte comprometida del alcance.
4. Al guardar, el proyecto queda planificado y las tareas pendientes. Una clave foránea inexistente impide confirmar la operación y produce un aviso comprensible.

La decisión sobre viabilidad y prioridades corresponde a Coordinación. El sistema verifica reglas de datos; no decide automáticamente si la empresa debe aceptar un proyecto.

## HU03 Consultar avances y detectar atrasos

Como responsable de Gerencia General, quiero consultar el estado y el avance de los proyectos, para identificar atrasos y decidir prioridades con información actualizada.

Prioridad alta. Entidades Proyecto, Tarea y Usuario. Depende de HU02 y de la actualización de tareas por el equipo.

Criterios de aceptación

1. El tablero permite consultar proyectos por estado y visualizar fechas y cantidades de tareas.
2. El avance se calcula como tareas finalizadas dividido por tareas del proyecto, multiplicado por 100. Si no hay tareas se muestra Sin tareas, evitando una división por cero. Se aclara que esta medida no pondera el esfuerzo de cada tarea.
3. Una tarea vencida tiene fecha límite anterior a la fecha de consulta y no está finalizada; se distingue de una tarea cuyo vencimiento es hoy.
4. Al actualizar una tarea, el tablero refleja los datos guardados. El sistema mantiene consistente completada con estado: solo es True cuando estado es finalizada.
5. Un usuario no habilitado no accede a información del tablero. Gerencia tiene consulta; Desarrollo actualiza sus tareas; Coordinación planifica; Comercial administra clientes. Los permisos se especifican sin equipararlos con autoridad jerárquica.

## Cómo registrar las historias en el tablero

Crear un Issue por historia y copiar su título, formulación y criterios. Agregarlo al Project. Dividir el trabajo académico en subtareas verificables: especificación, modelado, definición de pruebas y revisión.

Si no se implementó el software, no marcar la historia funcional como Listo por haber escrito su documentación. Puede permanecer Por Hacer o En Progreso y tener subtareas documentales terminadas. El tablero debe declarar su alcance y reflejar lo efectivamente realizado.

## Definición de Listo

Para una tarea documental: archivo incorporado, coherencia revisada, criterios verificables y evidencia del cambio. Para una historia implementada: funcionalidad disponible, pruebas aprobadas y revisión concluida. No confundir ambas definiciones.

