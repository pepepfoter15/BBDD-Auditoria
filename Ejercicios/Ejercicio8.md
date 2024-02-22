## 8. Averigua si en MySQL se pueden realizar los apartados 1, 3 y 4. Si es así, documenta el proceso adecuadamente.

Para poder realizar la auditorías en MySQL mediante logs, deberemos habilitar una línea de configuración en el fichero de configuración de MySQL. Para ello, debemos editar el fichero de configuración de MySQL:

```sql
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```

Y modficaremos las siguiente líneas añadiéndolas a este fichero:

```sql
general_log_file       = /var/log/mysql/mysql.log
general_log            = 1
log_error = /var/log/mysql/error.log
```

![FOTOS](img/29.png)

Estas líneas nos guardarán logs de esta base de datos en las rutas definidas. Cuando lo tengamos, tenemos que cambiar la propiedad el directorio de logs y reiniciamos el servicio. 

```sql
sudo chown mysql:mysql /var/log/mysql/
sudo systemctl restart mariadb
```

![FOTOS](img/30.png)

Para comprobar el funcionamiento, debemos tratar de iniciar sesión en la base de datos con un usuario que no exista y con un usuario que exista . Estos son los comandos en cuestión:

```sql
mysql -u noexiste -p
mysql -u root -p
```

![FOTOS](img/31.png)

Como podemos ver que he intentado acceder a un usuario que no existe y posterior