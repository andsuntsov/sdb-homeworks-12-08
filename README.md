# Домашнее задание к занятию "`Резервное копирование баз данных`" - `Сунцов Андрей`

---

### Задание 1

1. `Full Backup: Позволяет восстановить всю базу данных`

2. `Incremental Backup: Позволяет восстанавливать изменения, произошедшие с момента последнего полного бэкапа`

---

### Задание 2

1.1 `pg_dump -h localhost -U user -Fc database > /tmp/db_backup.dump`
1.2 `pg_restore -h localhost -U user -d database -v /tmp/db_backup.dump`

---

### Задание 3

1. ```
mysqlbackup --defaults-file=/home/dbadmin/my.cnf \
  --incremental=optimistic \
  --incremental-base=history:last_backup \
  --backup-dir=/home/dbadmin/temp_dir \
  --backup-image=incremental_image.bi \
  backup-to-image
```