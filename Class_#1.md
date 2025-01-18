# Gestión de Bases de Datos Clase 1: Introducción a Bases de Datos

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
CREATE DATABASE coursedb;
```
```sql
CREATE DATABASE testonedb;
```

### Eliminar una Base de Datos
El objetivo de este comando es eliminar una base de datos existente.
```sql
DROP DATABASE testonedb;
```

### Crear una Tabla
Este comando crea una tabla llamada students con campos para almacenar información personal y académica de los estudiantes. Los campos incluyen identificador único, nombre, identificación, edad, correo electrónico, estatura y fecha de nacimiento.

```sql
CREATE TABLE students (
	id_student INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(50) NOT NULL,
	id_card VARCHAR(10) UNIQUE NOT NULL,
	age INT NOT NULL,
	email VARCHAR(60) UNIQUE NOT NULL,
	height DECIMAL NOT NULL,
	birth_date DATE
);
```

```sql
CREATE TABLE test_one (
    id INT AUTO_INCREMENT PRIMARY KEY,
    description VARCHAR(100) NOT NULL
);
```

### Cambiar el Nombre de la Tabla
Para cambiar el nombre de la tabla test_one, utiliza el comando RENAME TABLE:
```sql
RENAME TABLE test_one TO test_two;
```

### Agregar una Nueva Columna
Para agregar una nueva columna, por ejemplo, created_at de tipo DATETIME, utiliza el comando ALTER TABLE:
```sql
ALTER TABLE test_two
ADD created_at DATETIME;
```
### Editar una Columna
Para modificar la columna description, por ejemplo, aumentando su longitud a 200 caracteres, usa:
```sql
ALTER TABLE test_two
MODIFY description VARCHAR(200) NOT NULL;
```
### Eliminar una Columna
Para eliminar una columna, como created_at, utiliza el siguiente comando:
```sql
ALTER TABLE test_two
DROP COLUMN created_at;
```

### Insertar Datos en una Tabla
El propósito de este comando es agregar registros a la tabla students con información específica sobre cada estudiante.
```sql
INSERT INTO test_two (description) 
VALUES ('Sample description');
```

### Eliminar tabla
El propósito de este comando es eliminar la tabla test_two, utiliza el comando DROP TABLE:
```sql
DROP TABLE test_two;
```
Nota: Da error ya que existe un registro, debe estar la tabla limpia de registros para poder eliminarla

### Eliminar registro
Para eliminar el registro que se insertó en la tabla test_two, utiliza el comando DELETE con una condición que identifique el registro único. Por ejemplo:
```sql
DELETE FROM test_two 
WHERE description = 'Sample description';
```

```sql
INSERT INTO students (name, id_card, age, email, height, birth_date)
VALUES
	('Pepita', '12456643', 27, 'pepis12@gmail.com', 1.50, '2000-01-05'),
	('Juanito', '12455643', 25, 'juan312@gmail.com', 1.70, '1993-01-10'),
	('Pepito', '133356643', 22, 'pep2@gmail.com', 1.90, '1996-01-10');

```

Nota: Es importante asegurarse de que los valores insertados en el campo height cumplan con el formato especificado (DECIMAL(4,2)) para evitar problemas de truncamiento.

Solución para el Error de Truncamiento
Si al insertar datos en la tabla ocurre un error de truncamiento en el campo height, se puede solucionar modificando la definición de la columna para especificar correctamente el formato decimal.

```sql
ALTER TABLE students 
MODIFY height DECIMAL(4,2) NOT NULL;
```


