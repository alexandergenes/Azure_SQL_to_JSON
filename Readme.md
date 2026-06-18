CADENA DE ACTIVIDADES

```
tabla_control.tabla
    → Lookup
        → ForEach → item().tabla
            → Copy Activity
                → ds_destino_parquet
                    → p_tabla = @item().tabla
                    → p_fecha_ingesta = @variables('v_fecha_ingesta')

```

TABLA DE CONTROL

CREAR TABLA

```sql
CREATE TABLE dbo.tabla_control (
id       INT IDENTITY(1,1) PRIMARY KEY,
esquema  NVARCHAR(50)  NOT NULL,
tabla    NVARCHAR(100) NOT NULL,
activo   BIT           NOT NULL DEFAULT 1
);

```

INSERT DE TABLAS

```sql
INSERT INTO dbo.tabla_control (esquema, tabla, activo) VALUES
('dbo', 'datos_personales', 1),
('dbo', 'datos_residencia',  1);

```
