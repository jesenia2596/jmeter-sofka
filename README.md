# 🚀 Prueba de Carga - Login API (JMeter)

Este proyecto contiene la configuración y ejecución de pruebas de carga sobre un endpoint de autenticación, utilizando **Apache JMeter**.

---

## 📌 Objetivo

Validar el comportamiento, rendimiento y estabilidad del endpoint de login bajo carga concurrente, asegurando que cumpla con los siguientes criterios:

- ✅ Throughput esperado: **20 TPS (Transactions Per Second)**
- ✅ Tiempo de respuesta máximo: **1.5 segundos**
- ✅ Tasa de error permitida: **< 3%**

---

## 🧰 Tecnologías utilizadas

- 🧪 Apache JMeter 5.6.3  
- ☕ Java 8 o superior  
- 📊 Generación de reportes HTML (JMeter Dashboard)

---

## 📂 Estructura del proyecto
```
jmeter-sofka/
├── Prueba login softka.jmx     # Script principal de JMeter
├── users.csv                  # Datos de usuarios para pruebas
├── InformeResultadosPruebalogin.docx
├── InformeResultados_Punto 2.docx
└── README.txt
```

---

## ⚙️ Configuración del escenario

- 🔗 Endpoint: https://fakestoreapi.com/auth/login
- 📩 Método: POST
- 👥 Datos de entrada: archivo users.csv
- 🔄 Tipo de prueba: carga concurrente
- 🎯 Objetivo: simular múltiples usuarios autenticándose simultáneamente

---

## 🛠️ Instalación

### En Mac (usando Homebrew)

brew install jmeter

Verificar instalación:

jmeter -v

---

## ▶️ Ejecución de la prueba (GUI)

1. Abrir JMeter:
   jmeter

2. Abrir el archivo:
   Prueba login softka.jmx

3. Ejecutar la prueba:
   Click en Run

---

## 💻 Ejecución por consola (recomendada)

jmeter -n \
  -t "Prueba login softka.jmx" \
  -l results.jtl \
  -e -o report/

---

## 📈 Métricas evaluadas

- Tiempo de respuesta (Response Time)
- Throughput (TPS)
- Tasa de errores
- Percentiles (P90, P95, P99)
- Usuarios concurrentes

---

## 📑 Evidencia

El proyecto incluye reportes de resultados:

- InformeResultadosPruebalogin.docx
- InformeResultados_Punto 2.docx

---

## ⚠️ Recomendaciones

- Ejecutar en modo no GUI para resultados más reales  
- Evitar correr pruebas en máquinas con alta carga  
- Ajustar el CSV (users.csv) para pruebas más robustas  
- Monitorear CPU, memoria y red durante la ejecución  

---

## 🧠 Posibles mejoras

- Integración con CI/CD (ej: Jenkins, GitLab)
- Pruebas distribuidas
- Uso de datasets más grandes
- Validaciones dinámicas de respuesta
- Integración con herramientas como Grafana/Prometheus

---

## 👨‍💻 Autor

Proyecto realizado como ejercicio de pruebas de carga para evaluación técnica.
