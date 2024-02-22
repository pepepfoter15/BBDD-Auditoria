## 9. Averigua las posibilidades que ofrece MongoDB para auditar los cambios que va sufriendo un documento. Demuestra su funcionamiento.

Tenemos que saber que para poder realizar auditorías en MongoDB, debemos tener la versión Enterprise de este mismo. Con esto dicho, hay 3 tipos opciones a la hora de realizar una auditoría y estas son las siguientes:

- `Guardar en el syslog`: Los registros de auditoría se envían al sistema de registro del sistema operativo y este nos será muy útil para entornos con contenidos centralizados en distintas bases de datos.

- `Guardar en fichero JSON/BSON`: Los registros se almacenan en archivos en el sistema de archivos del servidor MongoDB, facilitando la revisión y el análisis de estas mismas.

- `Mostrar mediante consola`: Los registros de auditoría se muestran directamente en la consola de MongoDB que es muy útil a la hora de ver los logs en tiempo real.

Con esto comentado, tendremos que habilitar las auditorías, deberemos modificar el fichero de configuración de MongoDB o podemos hacerlo mediante comandos. Por ello pasamos a verlos 1 a 1.

**Para habilitar las auditorías mediante syslog:**

- Mediante fichero de configuración (lo añadimos en las respectivas líneas del fichero):

```sql
sudo nano /etc/mongod.conf

storage:
  dbPath: /var/lib/mongodb/
auditLog:
  destination: syslog
```

- Mediante comandos desde la consola:

```sql
mongod --dbpath /var/lib/mongodb/ --auditDestination syslog
```

