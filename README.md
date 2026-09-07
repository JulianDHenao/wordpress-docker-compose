# Despliegue de WordPress con Docker Compose

Este repositorio contiene la arquitectura y configuración para desplegar un entorno contenedorizado de WordPress junto con una base de datos MySQL usando Docker Compose.

## Requisitos
* Docker
* Docker Compose

## Estructura de Servicios
* **WordPress:** Servicio principal expuesto en el puerto host `8080` (Contenedor `wordpress_app`).
* **MySQL 8.0:** Base de datos relacional (Contenedor `wordpress_db`).
* **Volúmenes:** Almacenamiento persistente para la base de datos y los archivos de WordPress.

* ## Arquitectura de la Solución

```mermaid
graph TD
    User([Usuario / Navegador]) -->|Puerto 8080| WP[Contenedor WordPress]
    User -->|Puerto 8081| PMA[Contenedor phpMyAdmin]
    WP -->|Puerto 3306| DB[(Base de Datos MySQL)]
    PMA -->|Puerto 3306| DB
    
    subgraph Red de Docker [wordpress-network]
        WP
        PMA
        DB
    end
```

## Instrucciones de Despliegue

1. Clonar el repositorio:

2. bash
git clone
