# RetailPro - Sistema de Gestión y Análisis de Ventas

**RetailPro** es una solución de base de datos relacional diseñada para centralizar las operaciones comerciales, analizar el rendimiento de las ventas, identificar el comportamiento de los clientes y optimizar los modelos de datos internos de la compañía.

---

## 🛠️ Herramientas Utilizadas

*   **Motor de Base de Datos:** [Microsoft SQL Server](https://microsoft.com) (T-SQL) administrado mediante [SQL Server Management Studio (SSMS)](https://microsoft.com).
*   **Base de Datos del Proyecto:** `Ventas_Tech_DB`
*   **Enfoque de Análisis:** SQL Avanzado, consultas de exclusión y consolidación de reportes comerciales.

---

## 📁 Estructura del Repositorio

*   `📂 /scripts`: Carpeta contenedora de todos los archivos SQL organizados de manera secuencial.
    *   `01_schema.sql`: Creación de la base de datos `Ventas_Tech_DB` y sus tablas.
    *   `02_seeds.sql`: Carga de datos iniciales.
    *   `03_analytics_queries.sql`: Consultas analíticas y reportes de negocio.
*   `📄 README.md`: Documentación técnica del proyecto (este archivo).

---

## 🧠 Reglas de Negocio Clave

Para comprender la lógica de los reportes analíticos incluidos en `/scripts`, un analista nuevo debe tener en cuenta los siguientes criterios corporativos implantados en las consultas:

1.  **Consolidación de Canales de Venta (`UNION ALL`):** Las ventas se unifican bajo una regla temporal estricta:
    *   **Canal Presencial:** Registros correspondientes a los **días 1 al 10** de cada mes.
    *   **Canal Online:** Registros de los **días posteriores al 10** de cada mes.
2.  **Identificación de Inactividad y Stock Estancado:** Las consultas analíticas utilizan estructuras `LEFT JOIN` con filtros `IS NULL` aplicados específicamente para extraer de forma inmediata:
    *   **Clientes inactivos:** Usuarios registrados que nunca han efectuado una compra (orientado a campañas de marketing directo).
    *   **Stock estancado:** Productos del catálogo sin ventas asociadas.

---

## 🚀 Guía de Ejecución para Nuevos Analistas

Siga estos pasos en orden para desplegar el entorno localmente y evitar errores de compatibilidad:

### 1. Preparar el Entorno
1. Abra **SQL Server Management Studio (SSMS)** y conéctese a su instancia de servidor local.
2. Clone este repositorio o descargue la carpeta de archivos SQL.

### 2. Despliegue de la Base de Datos
Abra y ejecute secuencialmente los scripts de la carpeta `/scripts`:

1.  **Crear la estructura:** Ejecute `01_schema.sql`. Esto creará la base de datos `Ventas_Tech_DB`, sus tablas correspondientes y las relaciones de integridad.
2.  **Poblar los datos:** Ejecute `02_seeds.sql` para cargar los registros de prueba de clientes, productos y transacciones.

### 3. Ejecución de Consultas de Negocio
Abra el archivo `03_analytics_queries.sql` donde podrá correr los bloques de código analítico para auditar los canales de venta (Presencial/Online) y extraer los reportes de stock o clientes inactivos.

---

## 🤝 Contribuciones
Por favor, abra un *Issue* o envíe un *Pull Request* si desea sugerir mejoras a las consultas de optimización SQL.

## 📄 Licencia
Este proyecto está bajo la Licencia MIT.

`Mi versión editada`: 

• Cambio 1 : Especificación técnica del motor de Base de Datos: Modifiqué la sección de herramientas para detallar el uso de SQL Server (T-SQL) y la base de datos `Ventas_Tech_DB`. El texto original mencionaba generalidades de SQL; especificar el entorno exacto evita que un analista nuevo intente correr las consultas en motores incompatibles como MySQL o PostgreSQL.

• Cambio 2 : Inclusión de reglas de negocio para los Canales (`UNION ALL`): Añadí una sección explicativa sobre cómo se divide el consolidado de ventas por canal. La propuesta omitía detallar que los días 1 al 10 corresponden al canal Presencial y los días posteriores al 10 al canal Online, una regla de negocio crítica que debe quedar registrada para cualquiera que audite el código.

• Cambio 3 : Inclusión de lógica de exclusión para Clientes/Productos sin Ventas: Incorporé una breve guía explicativa sobre las consultas de exclusión (`LEFT JOIN` con filtros `IS NULL`). Esto asegura que el analista entienda de inmediato el propósito comercial del reporte, el cual sirve para identificar stock estancado y usuarios inactivos para campañas de marketing directo.
