
# Conclusiones de la Prueba de Carga

## Resumen General

Durante la ejecución de la prueba de carga se observó lo siguiente:

- **Throughput alcanzado**: 14.2 TPS (objetivo: 20 TPS)
- **Tasa de error**: 30.6% (muy por encima del umbral permitido del 3%)
- **Tiempo de respuesta**: Aceptable (<1500ms)

## Puntos Clave

1. **El sistema soportó hasta 14.2 TPS**, pero con una alta tasa de error (30.6%). Esto indica que la escalabilidad está limitada bajo carga.
2. **El endpoint de login** no alcanzó el throughput objetivo de 20 TPS, lo que sugiere problemas en la capacidad de manejar más usuarios simultáneos.
3. **La tasa de error elevada** sugiere que el sistema no maneja bien la concurrencia y necesita mejorar en la gestión de errores bajo carga.
4. **Caídas en el throughput** fueron observadas entre los 13-15 TPS, indicando un **punto de saturación**.

## Recomendaciones

1. **Implementar pruebas en entornos controlados** para evitar interferencias de servicios externos.
2. **Optimizar el sistema para manejar más TPS**, evaluando la infraestructura y los límites del servicio.
3. **Monitorear y mejorar la gestión de errores**, como la implementación de **retry logic** o un sistema de **rate limiting** más eficiente.

## Archivos de Resultado

- **Informe completo**: [InformeResultadosPruebaDeCarga.docx](enlace al archivo si lo tienes)
- **Resultado de pruebas**: [resultados.json](si usas formato JSON)


## Comparación de Métricas Esperadas vs. Reales

| Métrica             | Esperada      | Real        | Resultado    |
|---------------------|---------------|-------------|--------------|
| Throughput (TPS)    | 20 TPS        | 14.2 TPS    | ❌ No cumplido|
| Tiempo de respuesta | < 1500 ms     | 282 ms      | ✅ Cumplido  |
| Error rate          | < 3%          | 30.6%       | ❌ No cumplido|


## Archivo de Línea Base

El archivo de línea base con los resultados iniciales está disponible aquí: [baseline.jtl](enlace al archivo).

Solo 4 usuarios estan registrados en la pagina. los otros 126 no tiene usuario por lo tando van a dar error


Se implementa validacion de estado de la api antes de ejecutar los test, conclusiones no se implementa el teardown porque no se encuentra necesario realizar ninguna limpieza


Informe de Resultados - Prueba de Carga
Métricas obtenidas

- Throughput: 14.2 TPS
- Tiempo promedio: 282 ms
- Error: 30.60%
- Muestras: 36,020

Análisis

El sistema presenta tiempos de respuesta adecuados (<1500 ms), pero no logra alcanzar el throughput esperado de 20 TPS.

Se evidencia una alta tasa de error (30.60%), lo cual indica problemas de estabilidad bajo carga.

Se identifican respuestas HTML en lugar de JSON, lo que sugiere mecanismos de protección como rate limiting o bloqueo por Cloudflare.

Se observa un punto de degradación entre 13 y 15 TPS.

Conclusiones

El sistema no cumple con los criterios de rendimiento definidos. Aunque responde rápido, no escala correctamente bajo carga y presenta una alta tasa de errores.

Esto se atribuye a limitaciones del servicio externo utilizado para la prueba.

Recomendaciones

- Usar entornos controlados para pruebas de carga
- Implementar retry y control de tasa
- Analizar capacidad máxima del sistema


