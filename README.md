<!-- Automatización de Control de ACPM con n8n y Google Sheets

 Sistema automatizado para el control de combustible, rendimiento de flota y cálculo de kilometraje anterior en tiempo real, conectando flujos de datos en n8n con Google Sheets.

 Descripción del Proyecto
Este proyecto resuelve uno de los retos más comunes al integrar bases de datos en la nube con hojas de cálculo: el seguimiento histórico del odómetro por vehículo (# INTERNO) sin perder precisión en los cálculos dinámicos de consumo, diferencia de kilometraje y rendimiento por galón.

 Arquitectura y Tecnologías
- n8n: Orquestador de flujos de trabajo e inserción automatizada de registros.
- Google Sheets: Base de datos relacional en nube y motor de visualización (Tablas oficiales de Google Sheets).
- Fórmulas Avanzadas: Implementación de funciones nativas de búsqueda (BUSCARX) optimizadas para el control operativo de la flota.

 Estructura de la Tabla
La hoja de cálculo está diseñada con las siguientes columnas operativas:
1. FECHA: Fecha del registro de tanqueo.
2. HORA: Hora exacta de la operación.
3. #INTERNO: Identificador único del vehículo (bus).
4. GALONES: Cantidad de ACPM suministrada.
5. KM ANTERIOR: Último kilometraje registrado del vehículo (obtenido mediante lógica de búsqueda inversa).
6. KM ACTUAL: Kilometraje reportado en el tanqueo actual.
7. DIFERENCIA: Recorrido en kilómetros desde el último tanqueo.
8. RENDIMIENTO: Eficiencia (Km / Galón).
9. SERVICIO: Tipo de ruta (Metropolitano, Alimentador, etc.).
10. OBSERVACIONES: Notas adicionales del operador o estación.

## Lógica Clave (El Reto del Proyecto)
Principalmente, la creación de esta automatización y su lógica de búsqueda se diseñaron con un propósito crítico: **eliminar los errores humanos en el registro del kilometraje al tanquear**. 

En la operación diaria, un error al digitar el odómetro actual provocaba fallos graves en toda la hoja de cálculo y en las métricas de rendimiento. Para garantizar precisión y evitar que este problema se repitiera, se configuró una lógica de búsqueda exacta que rastrea de forma automática el último registro histórico de cada unidad:
=SI.ERROR(BUSCARX(C2, C1:C$2, F1:F$2, 0, 0, -1), 0)

Esto permite mantener un historial limpio, prevenir saltos de datos erróneos y asegurar que métricas vitales como el consumo y la diferencia de kilometraje se calculen siempre con absoluta precisión.

Configuración del Flujo en n8n
- Captura de datos operativos hacia el sistema.
- Inyección estructurada de filas en Google Sheets asegurando la integridad de las columnas clave.
- Sincronización de variables de rendimiento y control de flota.

Licencia y Derechos de Autor
© 2026. Todos los derechos reservados. Este proyecto es una obra original de autoría propia destinada a la gestión y optimización de flotas. Queda prohibida su reproducción comercial no autorizada.  -->