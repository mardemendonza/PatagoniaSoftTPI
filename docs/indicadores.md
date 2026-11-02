# Indicadores y mecanismos de control
Los valores retoman las metas de la Entrega 2. Son estándares previstos, pendientes de medición sobre una implementación.

## C01 Tiempo de respuesta
Indicador: operaciones completadas en un máximo de 2 segundos / operaciones medidas × 100. Estándar: al menos 95 %. Muestra prevista: 100 operaciones habituales, cuatro usuarios simultáneos, conexión estable y base con el volumen objetivo. QA registra fecha, entorno, operación y duración; Desarrollo corrige e identifica causas si no se alcanza el estándar. Se vuelve a medir antes de liberar. Debe documentarse la distribución de operaciones para poder repetir la prueba.

## C02 Capacidad e integridad
Estándar: almacenar y consultar 500 clientes, 200 proyectos y 2.000 tareas sin pérdida de información. QA compara cantidades cargadas y recuperadas y verifica referencias Cliente Proyecto, Proyecto Tarea y Usuario Tarea. También verifica que referencias inválidas sean rechazadas. Se ejecuta en la etapa de pruebas y después de cambios relevantes en datos. Ante pérdida o referencias rotas, se bloquea la liberación y Desarrollo corrige antes de repetir.

## C03 Cumplimiento del cronograma
Indicador: diferencia en días hábiles entre la fecha real y la planificada de cada hito. Estándar final: completar las etapas en 40 días hábiles, ocho semanas. Coordinación revisa semanalmente el Gantt. Un desvío positivo exige analizar causa, redistribuir dedicación o ajustar alcance con aprobación; modificar fechas sin registrar la decisión no demuestra cumplimiento del plan original.

## C04 Pruebas satisfactorias
Indicador: casos aprobados / casos previstos × 100. Estándar: al menos 90 % de una batería mínima de 30 casos, equivalentes a 27 aprobados. Los casos no ejecutados no se cuentan como aprobados. Las funciones esenciales deben aprobar todas sus pruebas. QA conserva pasos, resultado esperado, resultado observado y evidencia. Desarrollo corrige y QA repite las pruebas afectadas.

## C05 Errores críticos pendientes
Indicador: cantidad de defectos críticos abiertos. Estándar: cero antes de implementar. Es crítico un defecto que impide una función esencial, pierde datos o habilita acceso no autorizado. Aunque se alcance el 90 % global, un error crítico bloquea la liberación. QA registra severidad y evidencia; Coordinación decide la liberación con base en los resultados y Desarrollo resuelve los defectos.

## Registro mínimo por medición
Código del control, fecha, versión o commit, ambiente y datos de prueba, responsable, resultado, desvío, acción correctiva y nueva verificación. Una tabla vacía o un protocolo no constituye evidencia de una prueba realizada.
