<!--# Sistema de Automatización para la Gestión de Flota y Control de ACPM

## Resumen del proyecto

Este proyecto implementa un flujo de trabajo automatizado para la gestión integral de combustible (ACPM) y el control de flota vehicular. Desarrollado mediante **n8n** y sincronizado con **Google Sheets**, el sistema elimina los procesos de registro manual, garantiza la integridad de los datos de consumo y automatiza el cálculo de métricas de rendimiento por vehículo.

---

## 1. El Reto Operativo (Definición del Problema)

En la gestión de flotas, el ingreso manual de datos por parte de los conductores o personal operativo representa un punto crítico de fallas:

* **Error Humano en Kilometraje:** Transcripción incorrecta o inconsistente de los odómetros al momento del despacho de ACPM.
* **Corrupción de Métricas:** Lecturas erróneas de kilometraje distorsionan el cálculo de rendimiento ($km/galón$), imposibilitando la detección de anomalías o consumos atípicos.
* **Carga Administrativa:** Necesidad de auditoría manual constante para corregir inconsistencias históricas en las hojas de cálculo.

---

## 2. Arquitectura de la Solución

Para mitigar los errores operativos, se diseñó una solución desacoplada que valida y procesa la información antes de consolidar el registro definitivo:

1. **Captura y Orquestación (n8n):** Servidor local n8n ejecutado en entorno contenedorizado (Docker) encargada de recibir las peticiones, estructurar la información y aplicar reglas de validación en tiempo real.
2. **Capa de Almacenamiento y Cálculo (Google Sheets):** Hoja de cálculo centralizada que actúa como base de datos operacional.
3. **Validación Histórica de Odómetro:** Implementación de la fórmula avanzada `=SI.ERROR(BUSCARX(...))` para rastrear automáticamente el último kilometraje válido registrado de cada vehículo específico, garantizando continuidad en la secuencia histórica independientemente del orden de ingreso.

---

## 3. Impacto y Beneficios de Negocio

* **100% de Integridad de Datos:** Eliminación total de inconsistencias por saltos de kilometraje o lecturas inferiores a la última registrada.
* **Trazabilidad Automática:** Cálculo preciso del consumo real por vehículo sin requerir intervención o revisión humana.
* **Escalabilidad:** Infraestructura preparada para procesar volúmenes crecientes de despachos sin incrementar costos operativos.

---

## 4. Estructura del Repositorio

* `README.md`: Documentación técnica de la solución y lógica del sistema.
* `workflow-acpm.json`: Flujo de trabajo exportado de n8n para auditoría o despliegue en nuevos entornos (opcional).

---

## 5. Contacto y Demostración

Para coordinar una demostración en vivo del flujo en n8n o discutir detalles sobre la arquitectura implementada, puede ponerse en contacto a través de los siguientes canales:

* **LinkedIn:** [Enlace a tu perfil de LinkedIn]
* **Correo Electrónico:** tuemail@dominio.com

---

## Aviso Legal y Derechos de Autor

© 2026. Todos los derechos reservados. Queda prohibida la reproducción, distribución o modificación total o parcial de este material sin la autorización expresa y por escrito del autor. -->