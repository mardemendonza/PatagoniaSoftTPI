# Alta y planificación de un proyecto
## Propósito y límites
Se modela el alta y la planificación de un proyecto, desde que Comercial recibe una solicitud hasta que queda registrado un plan con cliente, requerimientos, tareas, responsables y fechas. Es un tramo del proceso general de gestión de proyectos; la ejecución técnica, las pruebas y el cierre quedan fuera de este diagrama.

El módulo centraliza los registros y valida datos. Las decisiones de viabilidad, prioridades y asignación del trabajo corresponden a las personas. El modelo representa el proceso propuesto con el módulo disponible; no implica que la aplicación ya esté implementada.

## Participantes y responsabilidades
El pool Cliente representa al participante externo como caja negra: no se describe su organización interna. El pool PatagoniaSoft contiene tres lanes: Comercial, Analista y Coordinación, y Sistema. Desarrollo y Calidad participan en etapas posteriores; no se agregan actividades suyas a este tramo solo para completar el organigrama.

## Recorrido principal
1. Comercial recibe la solicitud del cliente y registra sus datos y necesidades mediante el módulo.
2. El sistema valida los datos, identifica al cliente existente o crea el registro cuando corresponde y evita altas duplicadas.
3. Si los datos están completos, Coordinación define alcance y requerimientos y evalúa viabilidad con criterios humanos.
4. Si el proyecto es viable, Coordinación registra tareas, responsables activos y fechas consistentes.
5. El sistema guarda el plan, vincula los datos y deja el proyecto planificado y las tareas pendientes.

## Excepciones
Si los datos están incompletos, Comercial solicita una aclaración al cliente y espera su respuesta antes de corregir el registro. No se presupone una respuesta inmediata. Si Coordinación determina que el proyecto no es viable, Comercial comunica la decisión y el proceso termina sin crear un proyecto comprometido. Antes de completar la actividad de planificación se corrigen fechas o responsables inválidos; el sistema impide confirmar datos que incumplen las reglas de HU02.

## Notación y lectura
Los eventos marcan inicio y final. Las actividades usan rectángulos con esquinas redondeadas; las compuertas exclusivas muestran una X y seleccionan una sola salida. El flujo de secuencia es continuo dentro de PatagoniaSoft y puede cruzar lanes. El flujo de mensaje es discontinuo entre Cliente y PatagoniaSoft; nunca se utiliza como secuencia entre roles internos. Los iconos de persona, engranaje y sobre distinguen tareas de usuario, servicio, envío y recepción; esos tipos están definidos también en el archivo BPMN editable.

La lane Sistema representa el comportamiento automatizado dentro del proceso organizacional, como solicita la consigna. No se modela como una empresa externa.

## Relación con el modelo de datos
HU01 utiliza Cliente. HU02 relaciona Proyecto con Cliente, Requerimiento con Proyecto, Tarea con Proyecto y Usuario con Tarea. HU03 consulta esas relaciones para construir información de seguimiento.

## Ajustes para la integración final
El campo rol de Usuario debe admitir perfiles de Comercial y Gerencia además de los técnicos. Los roles del sistema expresan permisos y no crean nuevos niveles del organigrama. El campo completada de Tarea debe derivarse de estado o mantenerse sincronizado para evitar contradicciones. Un cliente puede existir con cero proyectos; cuando se crea un proyecto, debe vincularse con exactamente un cliente.

## Referencia de notación
Object Management Group. Business Process Model and Notation, versión 2.0.2. https://www.omg.org/spec/BPMN/2.0.2/PDF
