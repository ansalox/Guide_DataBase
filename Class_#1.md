
# Temas a explicar

* Que es una base de datos
* Porque son importantes en el sector
* Que es SQL y NoSQL
* Diferencias entre SQL y NoSQL
* Que son tablas filas columnas registros y querys en SQL
* Que son colecciones documentos en NoSQL y como se realacionan colecciones entre si

  # Guía Completa: Introducción a Bases de Datos

## ¿Qué es una Base de Datos?

Una **base de datos** es un conjunto organizado de información o datos, que se almacena electrónicamente en un sistema de computadora. Se diseñan para facilitar el acceso, la gestión y la actualización de grandes cantidades de información.

### Ejemplo sencillo:
Imagina una **agenda telefónica** donde cada página representa una lista de contactos. Cada contacto tiene su nombre, número y dirección. Una base de datos lleva esta idea al mundo digital, permitiendo buscar, añadir o modificar datos rápidamente.

### Tipos de bases de datos:
1. **Bases de datos relacionales**: Organizan los datos en tablas relacionadas (ejemplo: MySQL, PostgreSQL).
2. **Bases de datos NoSQL**: Permiten almacenar datos de forma más flexible, sin una estructura fija (ejemplo: MongoDB, Firebase).

---

## ¿Por qué son Importantes las Bases de Datos en el Sector?

Hoy en día, las bases de datos son fundamentales porque **vivimos en una era de datos**. Desde aplicaciones móviles hasta grandes empresas, casi todas las herramientas tecnológicas dependen de bases de datos.

### Razones clave de su importancia:
1. **Gestión eficiente**:
   - Almacenan grandes volúmenes de datos sin perder orden.
   - Optimizan el acceso a la información.
2. **Toma de decisiones**:
   - Las empresas analizan los datos para entender tendencias y mejorar estrategias.
3. **Automatización**:
   - Los sistemas modernos utilizan bases de datos para reducir tareas manuales.
4. **Personalización**:
   - Ejemplo: Una plataforma como Netflix usa bases de datos para recomendarte películas basadas en tus preferencias.

### Ejemplo real:
En una tienda en línea, la base de datos:
- **Gestiona**: Inventarios, clientes y pedidos.
- **Conecta**: Carritos de compra con las cuentas de los clientes.
- **Optimiza**: El seguimiento de envíos en tiempo real.

---

## ¿Qué es SQL y NoSQL?

Cuando hablamos de bases de datos, nos referimos a **dos enfoques principales para gestionarlas**: **SQL** y **NoSQL**.

### SQL (Structured Query Language)

Es un lenguaje estándar para interactuar con **bases de datos relacionales**. Estas bases de datos organizan la información en **tablas** con filas y columnas, como una hoja de cálculo.

#### Características principales:
- Los datos están organizados en **estructuras fijas** llamadas tablas.
- Usa comandos estándar como `SELECT`, `INSERT`, `UPDATE`, y `DELETE`.
- Excelente para **transacciones complejas** y datos estructurados.

#### Ejemplo práctico:
Una empresa usa SQL para almacenar información sobre empleados:
```sql
SELECT nombre, puesto FROM empleados WHERE salario > 3000;
```

#### NoSQL (Not Only SQL)
Las bases de datos NoSQL ofrecen un enfoque más flexible, ideal para datos no estructurados o semiestructurados.

Características principales:
- No requieren un esquema fijo, lo que las hace ideales para datos en constante cambio.
- Usan estructuras como documentos JSON, pares clave-valor o grafos.
- Están diseñadas para manejar grandes cantidades de datos distribuidos.
- 
Ejemplo práctico:
En una red social, los datos de un usuario pueden estar en formato JSON:

```sql
{
  "nombre": "Juan",
  "edad": 25,
  "amigos": ["Ana", "Luis", "Pedro"]
}
```
Este enfoque permite almacenar datos relacionados sin depender de tablas rígidas.

## Diferencias entre SQL y NoSQL

Aquí tienes una tabla detallada en formato Markdown para comparar SQL y NoSQL:

| **Aspecto**              | **SQL**                                    | **NoSQL**                               |
|---------------------------|--------------------------------------------|-----------------------------------------|
| **Modelo de datos**       | Tablas relacionales                        | Documentos, grafos, clave-valor, etc.   |
| **Estructura**            | Esquemas rígidos                          | Flexible y sin esquema fijo             |
| **Transacciones**         | Excelente manejo de transacciones complejas | Limitadas en algunos sistemas           |
| **Escalabilidad**         | Vertical (mejorando hardware)             | Horizontal (añadiendo más servidores)   |
| **Velocidad**             | Ideal para datos estructurados            | Mejor para Big Data o datos dinámicos   |
| **Consultas**             | Lenguaje SQL estándar                     | Lenguajes específicos de cada sistema   |
| **Casos de uso**          | Bancos, contabilidad, CRM                 | Redes sociales, análisis en tiempo real |
| **Ejemplo de sistemas**   | MySQL, PostgreSQL, Oracle                 | MongoDB, Cassandra, Firebase            |

---

## Conceptos Clave en SQL: Tablas, Filas, Columnas, Registros y Queries

| **Concepto**       | **Definición**                                                                                  | **Ejemplo**                                                                                       |
|---------------------|------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Tabla**           | Estructura donde se almacenan los datos en filas y columnas.                                   | Tabla `usuarios`: <br> \| ID \| Nombre \| Edad \| <br> \|----\|--------\|-----\|                  |
| **Columna**         | Representa un atributo o característica de los datos.                                          | En la tabla `usuarios`, las columnas serían "ID", "Nombre" y "Edad".                             |
| **Fila o Registro** | Conjunto de datos relacionados dentro de una tabla.                                             | En la tabla `usuarios`, una fila sería: `1, Juan, 25`.                                            |
| **Query**           | Instrucción SQL para consultar, insertar, actualizar o eliminar datos en una tabla.            | Ejemplo de consulta: <br> `SELECT * FROM usuarios WHERE edad > 18;`                              |
| **Clave Primaria**  | Identificador único de una fila dentro de una tabla.                                           | En la tabla `usuarios`, la columna `ID` podría ser la clave primaria.                            |
| **Relación**        | Conexión entre dos o más tablas mediante claves foráneas.                                      | Tabla `usuarios` y tabla `pedidos` conectadas por una columna `id_usuario` común.                |

Ambas tablas en formato Markdown son compatibles para ser copiadas directamente en un archivo `.md` como parte de tu contenido.







```sql
CREATE DATABASE cursodb
```


```sql
CREATE TABLE estudiantes (
	id_estudiante INT AUTO_INCREMENT PRIMARY KEY,
	nombre VARCHAR(50) NOT NULL,
	cedula VARCHAR(10) UNIQUE NOT NULL,
	edad INT NOT NULL,
	correo VARCHAR(60) UNIQUE NOT NULL,
	estatura DECIMAL NOT NULL,
	fecha_nacimiento DATE
)
```

```sql
CREATE TABLE estudiantes (
	id_estudiante INT AUTO_INCREMENT PRIMARY KEY,
	nombre VARCHAR(50) NOT NULL,
	cedula VARCHAR(10) UNIQUE NOT NULL,
	edad INT NOT NULL,
	correo VARCHAR(60) UNIQUE NOT NULL,
	estatura DECIMAL NOT NULL,
	fecha_nacimiento DATE
	)
```

```sql
INSERT INTO estudiantes (nombre, cedula, edad, correo, estatura, fecha_nacimiento )
	VALUES
	('Pepita', '12456643', 27, 'pepis12@gmail.com', 1.50, '2000-01-05'),
	('Juanito', '12455643', 25, 'juan312@gmail.com', 1.70, '1993-01-10'),
	('Pepito', '133356643', 22, 'Pep2@gmail.com', 1.90, '1996-01-10')
```
