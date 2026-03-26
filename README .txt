# Prueba de Carga - JMeter

## Requisitos
- Apache JMeter 5.6.3
- Java 8 o superior

## Instalación (Mac)
brew install jmeter

## Ejecución
1. Abrir JMeter:
   jmeter

2. Abrir archivo:
   Prueba login softka.jmx

3. Ejecutar prueba (botón ▶)

## Ejecución por consola (opcional)
jmeter -n -t Prueba login softka.jmx -l results.jtl -e -o report/

## Archivos incluidos
- Script JMeter (.jmx)
- users.csv
- results.jtl
- report/

## Escenario
- Endpoint: https://fakestoreapi.com/auth/login
- Método: POST
- Usuarios desde CSV
- Throughput objetivo: 20 TPS
- Tiempo máximo: 1.5 segundos
- Error permitido: <3%
