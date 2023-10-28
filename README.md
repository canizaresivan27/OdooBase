
# 🚀 Despliegue de Odoo con Docker

Este repositorio contiene una configuración de `docker-compose` para desplegar Odoo junto con una base de datos PostgreSQL.

## 📦 Servicios

- **web** (🌍): Servicio de Odoo.
  -  Imagen: Definida por las variables de entorno `WEB_IMAGE_NAME` y `WEB_IMAGE_TAG`.
  -  Puerto: Mapeado desde el puerto definido por `WEB_PORT` al puerto `8069` del contenedor.
  -  Volúmenes:
    - Configuraciones: `./odoo_conf:/etc/odoo`
    - Datos de Odoo: `./odoo-web:/var/lib/odoo/`
    - Addons generales: `./addons:/mnt/extra-addons`
    - Addons personalizados: `./addons-customize:/mnt/extra-addons-customize`

- **db** (🗄️): Servicio de base de datos PostgreSQL.
  -  Imagen: Definida por las variables de entorno `DB_IMAGE` y `DB_TAG`.
  -  Puerto: Mapeado desde el puerto definido por `DB_PORT` al puerto `5432` del contenedor.
  -  Volúmenes:
    - Datos de PostgreSQL: `./odoo_postgresdata:/var/lib/postgresql/data/pgdata`

## 🛠️ Uso

1.  Clona este repositorio:
```
git clone [URL DEL REPOSITORIO]
```

2.  Navega al directorio del repositorio:
```
cd [NOMBRE DEL DIRECTORIO]
```

3.  Asegúrate de definir las variables de entorno necesarias o crea un archivo `.env` con las definiciones.

4.  Lanza los servicios usando docker-compose:
```
docker-compose up -d
```

5. Accede a Odoo a través de tu navegador usando la dirección `http://localhost:[WEB_PORT]`.


Las contribuciones son bienvenidas. Por favor, crea una *pull request* o informa de cualquier problema a través de la sección de *issues* del repositorio.
