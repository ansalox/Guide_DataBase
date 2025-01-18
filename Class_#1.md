# Guía Completa: Introducción a Bases de Datos

## ¿Qué es una Base de Datos?

Una **base de datos** es un conjunto organizado de información o datos que se almacena electrónicamente en un sistema de computadoras. Las bases de datos están diseñadas para facilitar el almacenamiento, la recuperación y la gestión eficiente de datos.

### Ejemplo Sencillo:
Imagina una **agenda telefónica**, donde cada página contiene una lista de contactos. Cada contacto tiene su nombre, número de teléfono y dirección. Una base de datos lleva esta idea al mundo digital, permitiendo buscar, agregar o modificar datos de manera rápida y eficiente.

### Tipos de Bases de Datos:
1. **Bases de datos relacionales**: Organizan la información en tablas estructuradas con filas y columnas (ejemplo: MySQL, PostgreSQL).
2. **Bases de datos NoSQL**: Permiten un almacenamiento más flexible, ideal para datos no estructurados o semiestructurados (ejemplo: MongoDB, Firebase).

---

## ¿Por qué son Importantes las Bases de Datos en el Sector?

Hoy en día, las bases de datos son fundamentales en casi todas las industrias, ya que **vivimos en la era de los datos**. Desde aplicaciones móviles hasta grandes corporaciones, las bases de datos juegan un papel esencial en el manejo de la información.

### Razones Clave de su Importancia:
1. **Gestión eficiente**:
   - Permiten almacenar grandes volúmenes de datos manteniendo el orden.
   - Facilitan el acceso rápido y preciso a la información.
2. **Toma de decisiones**:
   - Las empresas analizan los datos para identificar patrones, optimizar estrategias y tomar decisiones informadas.
3. **Automatización**:
   - Los sistemas modernos dependen de bases de datos para reducir tareas manuales.
4. **Personalización**:
   - Por ejemplo, plataformas como Netflix usan bases de datos para ofrecer recomendaciones personalizadas basadas en tus preferencias.

### Ejemplo Real:
En una tienda en línea, la base de datos:
- **Gestiona**: Inventarios, clientes y pedidos.
- **Conecta**: Carritos de compra con las cuentas de los clientes.
- **Optimiza**: El seguimiento de envíos en tiempo real.

---

## ¿Qué es SQL y NoSQL?

Cuando hablamos de bases de datos, existen **dos enfoques principales para gestionarlas**: **SQL** y **NoSQL**.

### SQL (Structured Query Language)

Es un lenguaje estándar utilizado para interactuar con **bases de datos relacionales**. Estas bases organizan la información en **tablas** con filas y columnas, como una hoja de cálculo.

#### Características Principales:
- Los datos están organizados en **estructuras fijas** llamadas tablas.
- Utiliza comandos estándar como `SELECT`, `INSERT`, `UPDATE` y `DELETE`.
- Es excelente para **transacciones complejas** y datos estructurados.

---

### NoSQL (Not Only SQL)

Las bases de datos NoSQL ofrecen un enfoque más flexible, ideal para datos **no estructurados** o **semiestructurados**.

#### Características Principales:
- No requieren un esquema fijo, lo que las hace ideales para datos que cambian con frecuencia.
- Utilizan estructuras como documentos JSON, pares clave-valor o grafos.
- Son ideales para manejar grandes cantidades de datos distribuidos.

---

## Diferencias entre SQL y NoSQL

| **Aspecto**              | **SQL**                                    | **NoSQL**                               |
|---------------------------|--------------------------------------------|-----------------------------------------|
| **Modelo de datos**       | Tablas relacionales                        | Documentos, grafos, clave-valor, etc.   |
| **Estructura**            | Esquemas rígidos                          | Flexible y sin esquema fijo             |
| **Transacciones**         | Excelente manejo de transacciones complejas | Limitadas en algunos sistemas           |
| **Escalabilidad**         | Vertical (mejor hardware)                 | Horizontal (más servidores)             |
| **Velocidad**             | Ideal para datos estructurados            | Mejor para Big Data o datos dinámicos   |
| **Consultas**             | Lenguaje SQL estándar                     | Lenguajes específicos de cada sistema   |
| **Casos de uso**          | Bancos, contabilidad, CRM                 | Redes sociales, análisis en tiempo real |
| **Ejemplo de sistemas**   | MySQL, PostgreSQL, Oracle                 | MongoDB, Cassandra, Firebase            |

---

## Conceptos Clave en SQL: Tablas, Filas, Columnas, Registros y Queries

| **Concepto**       | **Definición**                                                                                  | **Ejemplo**                                                                                       |
|---------------------|------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Tabla**           | Estructura donde se almacenan los datos en filas y columnas.                                   | Tabla `users`: <br> \| ID \| Name \| Age \| <br> \|----\|--------\|-----\|                       |
| **Columna**         | Representa un atributo o característica de los datos.                                          | En la tabla `users`, las columnas serían "ID", "Name" y "Age".                                   |
| **Fila o Registro** | Conjunto de datos relacionados dentro de una tabla.                                            | En la tabla `users`, una fila sería: `1, John, 25`.                                              |
| **Query**           | Instrucción SQL para consultar, insertar, actualizar o eliminar datos en una tabla.            | Ejemplo de consulta: <br> `SELECT * FROM users WHERE age > 18;`                                  |
| **Clave Primaria**  | Identificador único de una fila dentro de una tabla.                                           | En la tabla `users`, la columna `ID` podría ser la clave primaria.                              |
| **Relación**        | Conexión entre dos o más tablas mediante claves foráneas.                                      | Tabla `users` y tabla `orders` conectadas por una columna `user_id` común.                      |

---

## Práctica en SQL

### Crear una Base de Datos
El objetivo de este comando es crear una nueva base de datos para almacenar información de manera organizada.
```sql
CREATE DATABASE cursodb;


```sql
CREATE DATABASE cursodb
```

(explica chatgpt aqui cimpleto el objetivo de crear la tabla)

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

(explica chatgpt aqui cimpleto el objetivo de isnertar datos)

```sql
INSERT INTO estudiantes (nombre, cedula, edad, correo, estatura, fecha_nacimiento )
	VALUES
	('Pepita', '12456643', 27, 'pepis12@gmail.com', 1.50, '2000-01-05'),
	('Juanito', '12455643', 25, 'juan312@gmail.com', 1.70, '1993-01-10'),
	('Pepito', '133356643', 22, 'Pep2@gmail.com', 1.90, '1996-01-10')
```

NOTA SE PRESENTA MENSAJE DE DATOS TRUNCADOS Y HACE APROXIMACIONES DEBID A QUE NO SE INDICO EN DECIMAL EL ALCANCE Y LOS DIGITOS

(explica chatgpt aqui cimpleto el objetivo de editar tabla la tabla)
SOLUCION
```sql
ALTER TABLE estudiantes 
MODIFY estatura DECIMAL(4,2) NOT NULL;
```


