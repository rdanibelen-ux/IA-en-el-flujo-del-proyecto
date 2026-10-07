# IA-en-el-flujo-del-proyecto
# Proyecto RetailPro

Este repositorio contiene los scripts de bases de datos y las consultas analíticas para la plataforma RetailPro. El objetivo de este proyecto es analizar el rendimiento de las ventas, identificar el comportamiento de los clientes y optimizar los modelos de datos internos.

## Herramientas utilizadas
* SQL
* Bases de datos relacionales
* Análisis de datos

## Estructura del repositorio
* `/scripts`: Carpeta que contiene todos los archivos SQL.
* `README.md`: Documentación del proyecto.

## Cómo ejecutar los scripts
1. Abra su herramienta de gestión de bases de datos.
2. Conéctese a su servidor.
3. Cree una nueva base de datos.
4. Copie y pegue el contenido de los scripts.
5. Ejecute las consultas para ver los resultados.

## Contribuciones
Por favor, abra un problema o envíe una solicitud de extracción si desea sugerir mejoras a las consultas de optimización SQL.

## Licencia
Este proyecto está bajo la Licencia MIT.

`Mi versión editada`: 

• Cambio 1 : Especificación técnica del motor de Base de Datos: Modifiqué la sección de herramientas para detallar el uso de SQL Server (T-SQL) y la base de datos Ventas_Tech_DB. El texto original mencionaba generalidades de SQL; especificar el entorno exacto evita que un analista nuevo intente correr las consultas en motores incompatibles como MySQL o PostgreSQL.

• Cambio 2 : Inclusión de reglas de negocio para los Canales (`UNION ALL`): Añadí una sección explicativa sobre cómo se divide el consolidado de ventas por canal. La propuesta omitía detallar que los días 1 al 10 corresponden al canal Presencial y los días posteriores al 10 al canal Online, una regla de negocio crítica que debe quedar registrada para cualquiera que audite el código.

• Cambio 3 : Creación del Diccionario de Datos para Clientes/Productos sin Ventas: Incorporé una breve guía explicativa sobre las consultas de exclusión (`LEFT JOIN` con filtros `IS NULL`). Esto asegura que el analista entienda de inmediato que el reporte sirve para identificar stock estancado y usuarios inactivos para campañas de marketing directas.
