

TABLA DE CONTROL

CREAR TABLA

```
CREATE TABLE dbo.tabla_control (
    id       INT IDENTITY(1,1) PRIMARY KEY,
    esquema  NVARCHAR(50)  NOT NULL,
    tabla    NVARCHAR(100) NOT NULL,
    activo   BIT           NOT NULL DEFAULT 1
);

```

INSERT DE TABLAS

```

INSERT INTO dbo.tabla_control (esquema, tabla, activo) VALUES
('dbo', 'datos_personales', 1),
('dbo', 'datos_residencia',  1);

```
