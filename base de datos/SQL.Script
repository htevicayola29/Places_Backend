
CREATE TABLE Lugares (
                id_lugares INT NOT NULL,
                nombre VARCHAR(200) NOT NULL,
                descripcion VARCHAR(500) NOT NULL,
                municipio VARCHAR(100) NOT NULL,
                provincia VARCHAR(100) NOT NULL,
                departamento VARCHAR(100) NOT NULL,
                ubicacion VARCHAR(500) NOT NULL,
                latitud DECIMAL(300) AUTO_INCREMENT NOT NULL,
                url VARCHAR(250) NOT NULL,
                longitud DECIMAL(300) AUTO_INCREMENT NOT NULL,
                PRIMARY KEY (id_lugares)
);


CREATE TABLE Horarios (
                id_horarios INT NOT NULL,
                dia VARCHAR(50) NOT NULL,
                hora_inicio TIME NOT NULL,
                horario_fin TIME NOT NULL,
                id_lugares INT NOT NULL,
                PRIMARY KEY (id_horarios)
);


CREATE TABLE Funcionalidades (
                id_funcionalidad INT NOT NULL,
                nombre VARCHAR(50),
                PRIMARY KEY (id_funcionalidad)
);


CREATE TABLE Roles (
                id_rol_ INT AUTO_INCREMENT NOT NULL,
                nombre VARCHAR(100),
                PRIMARY KEY (id_rol_)
);


CREATE TABLE Privilegios (
                id_rol_ INT NOT NULL,
                id_funcionalidad INT NOT NULL,
                PRIMARY KEY (id_rol_, id_funcionalidad)
);


CREATE TABLE Personas (
                id_persona INT AUTO_INCREMENT NOT NULL,
                nombres VARCHAR(100) NOT NULL,
                fecha_nacimiento DATE NOT NULL,
                dnl INT NOT NULL,
                email VARCHAR(100) NOT NULL,
                genero VARCHAR(50) NOT NULL,
                direccion VARCHAR(200) NOT NULL,
                telefono_fijo INT NOT NULL,
                celular INT NOT NULL,
                primer_apellido VARCHAR(100) NOT NULL,
                segundo_apellido VARCHAR(100),
                complemento VARCHAR(2),
                PRIMARY KEY (id_persona)
);


CREATE TABLE Usuarios (
                id_persona INT NOT NULL,
                usuario VARCHAR(50) NOT NULL,
                password VARCHAR(300) AUTO_INCREMENT NOT NULL,
                rol VARCHAR(50) NOT NULL,
                PRIMARY KEY (id_persona)
);


CREATE UNIQUE INDEX usuarios_idx
 ON Usuarios
 ( usuario );

CREATE UNIQUE INDEX usuarios_idx1
 ON Usuarios
 ( usuario );

CREATE TABLE Cuentas (
                id_rol_ INT NOT NULL,
                id_persona INT NOT NULL,
                PRIMARY KEY (id_rol_, id_persona)
);


CREATE TABLE Favoritos (
                id_persona INT NOT NULL,
                id_lugares INT NOT NULL,
                PRIMARY KEY (id_persona, id_lugares)
);


CREATE TABLE Comentarios (
                id_comentarios INT AUTO_INCREMENT NOT NULL,
                comentario VARCHAR(500) NOT NULL,
                calificaion INT NOT NULL,
                fecha DATE NOT NULL,
                id_persona INT NOT NULL,
                id_lugares INT NOT NULL,
                Parent_id_comentarios INT NOT NULL,
                PRIMARY KEY (id_comentarios)
);


CREATE TABLE Fotos (
                id_fotos INT NOT NULL,
                url VARCHAR(500) NOT NULL,
                descripcion VARCHAR(250) NOT NULL,
                id_comentarios INT NOT NULL,
                id_lugares INT NOT NULL,
                PRIMARY KEY (id_fotos)
);


ALTER TABLE Comentarios ADD CONSTRAINT lugares_comentarios_fk
FOREIGN KEY (id_lugares)
REFERENCES Lugares (id_lugares)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Horarios ADD CONSTRAINT lugares_horarios_fk
FOREIGN KEY (id_lugares)
REFERENCES Lugares (id_lugares)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Fotos ADD CONSTRAINT lugares_fotos_fk
FOREIGN KEY (id_lugares)
REFERENCES Lugares (id_lugares)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Favoritos ADD CONSTRAINT lugares_favoritos_fk
FOREIGN KEY (id_lugares)
REFERENCES Lugares (id_lugares)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Privilegios ADD CONSTRAINT funcionalidades_privilegios_fk
FOREIGN KEY (id_funcionalidad)
REFERENCES Funcionalidades (id_funcionalidad)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Privilegios ADD CONSTRAINT roles_privilegios_fk
FOREIGN KEY (id_rol_)
REFERENCES Roles (id_rol_)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Cuentas ADD CONSTRAINT roles_cuentas_fk
FOREIGN KEY (id_rol_)
REFERENCES Roles (id_rol_)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Usuarios ADD CONSTRAINT personas_usuarios_fk
FOREIGN KEY (id_persona)
REFERENCES Personas (id_persona)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Comentarios ADD CONSTRAINT usuarios_comentarios_fk
FOREIGN KEY (id_persona)
REFERENCES Usuarios (id_persona)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Favoritos ADD CONSTRAINT usuarios_favoritos_fk
FOREIGN KEY (id_persona)
REFERENCES Usuarios (id_persona)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Cuentas ADD CONSTRAINT usuarios_cuentas_fk
FOREIGN KEY (id_persona)
REFERENCES Usuarios (id_persona)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Fotos ADD CONSTRAINT comentarios_fotos_fk
FOREIGN KEY (id_comentarios)
REFERENCES Comentarios (id_comentarios)
ON DELETE NO ACTION
ON UPDATE NO ACTION;

ALTER TABLE Comentarios ADD CONSTRAINT comentarios_comentarios_fk
FOREIGN KEY (Parent_id_comentarios)
REFERENCES Comentarios (id_comentarios)
ON DELETE NO ACTION
ON UPDATE NO ACTION;
