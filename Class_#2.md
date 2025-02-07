
CLASE 2

Renombrar la Tabla students a users


```sql
RENAME TABLE students TO users;
```

```sql
ALTER TABLE users
CHANGE id_student id_user INT AUTO_INCREMENT PRIMARY KEY;
```

-- Crear la tabla areas
```sql
CREATE TABLE areas (
    id_area INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT
);
```
-- Crear la tabla courses
```sql
CREATE TABLE courses (
    id_courses INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    price DECIMAL(10,2) NOT NULL,
    credits INT NOT NULL,
    id_area INT NOT NULL,
    FOREIGN KEY (id_area) REFERENCES areas(id_area) ON DELETE CASCADE
);
```
-- Crear registros en la tabla areas
```sql
INSERT INTO areas (name, description) VALUES
('Artificial Intelligence', 'Focuses on building intelligent machines and systems.'),
('Cybersecurity', 'Covers techniques and tools to protect systems and data.'),
('Web Development', 'Covers front-end and back-end development for web applications.');
```
-- Crear registros en la tabla courses
```sql
INSERT INTO courses (name, description, price, credits, id_area) VALUES
('JavaScript',        'Introduction to JavaScript for front-end development.',    200.00, 4, 3),
('React',             'Advanced course on building front-end applications.',     300.00, 5, 3),
('Node.js',           'Back-end development using Node.js and Express.',         250.00, 4, 3),
('Python',            'General-purpose programming with Python.',               150.00, 3, 1),
('Machine Learning',  'Introduction to machine learning algorithms.',           400.00, 6, 1),
('Ethical Hacking',   'Techniques and tools for ethical hacking and security.', 350.00, 5, 2),
('Data Science',      'Data analysis and visualization with Python and R.',     450.00, 6, 1),
('Penetration Testing','Practical course on penetration testing tools.',        300.00, 5, 2),
('Vue.js',            'Front-end development with Vue.js framework.',           200.00, 4, 3),
('Cyber Forensics',   'Analyzing and investigating cyber incidents.',           300.00, 5, 2);
```
-- Modificar la tabla users para agregar el campo curso_id y relacionarla con courses
```sql
ALTER TABLE users
ADD id_courses INT,
ADD FOREIGN KEY (id_courses) REFERENCES courses(id_courses) ON DELETE CASCADE;
```
-- Insertar nuevos registros en la tabla users con personajes de One Piece
```sql
INSERT INTO users (name, id_card, age, email, height, birth_date, id_courses) VALUES
('Monkey D. Luffy',      'OP0001', 19, 'luffy@onepiece.com',    1.72, '2006-05-05',1),
('Roronoa Zoro',         'OP0002', 21, 'zoro@onepiece.com',     1.78, '2002-11-11',2),
('Nami',                 'OP0003', 20, 'nami@onepiece.com',     1.70, '2003-07-03',3),
('Sanji Vinsmoke',       'OP0004', 21, 'sanji@onepiece.com',    1.80, '2001-03-02',4),
('Tony Tony Chopper',    'OP0005', 17, 'chopper@onepiece.com',  1.50, '2008-12-24',5),
('Nico Robin',           'OP0006', 30, 'robin@onepiece.com',    1.88, '1994-02-06',6),
('Franky',               'OP0007', 36, 'franky@onepiece.com',   2.40, '1988-03-09',7),
('Brook',                'OP0008', 90, 'brook@onepiece.com',    2.66, '1934-04-03',8),
('Jinbe',                'OP0009', 46, 'jinbe@onepiece.com',    3.01, '1978-04-02',9),
('Portgas D. Ace',       'OP0010', 20, 'ace@onepiece.com',      1.85, '2004-01-01',10),
('Boa Hancock',          'OP0011', 31, 'hancock@onepiece.com',  1.91, '1993-09-02',1),
('Shanks',               'OP0012', 39, 'shanks@onepiece.com',   1.99, '1985-03-09',2),
('Buggy',                'OP0013', 37, 'buggy@onepiece.com',    1.92, '1987-08-08',3),
('Crocodile',            'OP0014', 46, 'crocodile@onepiece.com',2.53, '1978-09-05',4),
('Trafalgar D. Water Law','OP0015',26, 'law@onepiece.com',      1.91, '1998-10-06',5),
('Eustass Kid',          'OP0016', 23, 'kid@onepiece.com',      2.05, '2001-01-10',6),
('Killer',               'OP0017', 25, 'killer@onepiece.com',   1.95, '1999-12-25',7),
('Donquixote Doflamingo','OP0018', 41, 'doflamingo@onepiece.com',3.05,'1983-10-23',8),
('Kaido',                'OP0019', 59, 'kaido@onepiece.com',    7.10, '1965-06-06',9),
('Big Mom',              'OP0020', 68, 'bigmom@onepiece.com',   8.80, '1956-02-15',10);
```
