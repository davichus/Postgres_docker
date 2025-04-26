# 🐳 Proyecto Docker Compose: PostgreSQL, MySQL, PgAdmin y PhpMyAdmin

Este proyecto levanta servicios de bases de datos **PostgreSQL** y **MySQL**, junto con sus respectivas interfaces de administración **PgAdmin** y **PhpMyAdmin**, utilizando Docker Compose.

---

## 📂 Estructura del Proyecto

```
/
├── docker-compose.yml
├── postgres_data/       # Datos persistentes de PostgreSQL
└── mysql_data/          # Datos persistentes de MySQL
```

---

## 📋 Instrucciones de uso

### 1️⃣ Construir y levantar los contenedores

Desde la terminal, en el mismo directorio del archivo `docker-compose.yml`, ejecuta:

```bash
docker-compose up -d
```

Esto realizará lo siguiente:

- Descargará las imágenes necesarias (si no están en tu sistema).
- Creará los contenedores para PostgreSQL, MySQL, PgAdmin y PhpMyAdmin.
- Levantará los contenedores en segundo plano.

---

### 2️⃣ Acceder a las aplicaciones

#### 🔷 PostgreSQL

- **Host:** `localhost`
- **Puerto:** `5432`
- **Usuario:** `japon`
- **Contraseña:** `japon`
- **Base de datos:** `myStore`

#### 🔷 PgAdmin 4

- **URL:** [http://localhost:5050](http://localhost:5050)
- **Correo electrónico:** `japon@mail.com`
- **Contraseña:** `japon`

**Para conectar a PostgreSQL desde PgAdmin:**

- Crear un nuevo servidor.
- En "Host name/address": `postgres`
- Usuario: `japon`
- Contraseña: `japon`

---

#### 🟡 MySQL

- **Host:** `localhost`
- **Puerto:** `3306`
- **Usuario:** `root`
- **Contraseña:** `root`
- **Base de datos:** `myStore`

#### 🟡 PhpMyAdmin

- **URL:** [http://localhost:8080](http://localhost:8080)
- **Servidor:** `mysql`
- **Usuario:** `root`
- **Contraseña:** `root`

---

### 3️⃣ Detener y eliminar los contenedores

#### Detener sin eliminar:

```bash
docker-compose stop
```

#### Detener y eliminar contenedores, redes y volúmenes anónimos:

```bash
docker-compose down
```

#### Eliminar completamente (incluye volúmenes persistentes):

```bash
docker-compose down -v
```

⚠️ Esto borrará los datos almacenados en las carpetas `postgres_data` y `mysql_data`.

---

## 💾 Persistencia de Datos

- PostgreSQL: `./postgres_data`
- MySQL: `./mysql_data`

Estos volúmenes garantizan que la información se conserve entre reinicios de los contenedores.

---

## 📝 Notas adicionales

- Asegúrate de que los puertos `5432`, `3306`, `5050` y `8080` estén disponibles en tu sistema.
- Puedes modificar usuarios, contraseñas y nombres de base de datos en el archivo `docker-compose.yml`.
- Para ver logs en tiempo real:

```bash
docker-compose logs -f
```

---

¡Listo! Ya tienes un entorno de desarrollo completo para trabajar con bases de datos relacionales usando Docker 🚀
