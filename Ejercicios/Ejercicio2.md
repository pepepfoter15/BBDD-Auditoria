## 2. Realiza un procedimiento en PL/SQL que te muestre los accesos fallidos junto con el motivo de los mismos, transformando el código de error almacenado en un mensaje de texto comprensible. Contempla todos los motivos posibles para que un acceso sea fallido.

Primero, para poder realizar este procedimiento, tendremos que realizar una serie de preparativos que son los siguientes.

- Activar la auditoría de intentos de acceso fallidos. Esto lo haremos con ls siguiente directiva:

```sql
AUDIT CREATE SESSION WHENEVER NOT SUCCESSFUL;
```

![FOTOS](img/7.png)

