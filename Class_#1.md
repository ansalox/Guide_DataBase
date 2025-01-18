
```
CREATE DATABASE cursodb
```


```
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

```
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

```
INSERT INTO estudiantes (nombre, cedula, edad, correo, estatura, fecha_nacimiento )
	VALUES
	('Pepita', '12456643', 27, 'pepis12@gmail.com', 1.50, '2000-01-05'),
	('Juanito', '12455643', 25, 'juan312@gmail.com', 1.70, '1993-01-10'),
	('Pepito', '133356643', 22, 'Pep2@gmail.com', 1.90, '1996-01-10')
```
