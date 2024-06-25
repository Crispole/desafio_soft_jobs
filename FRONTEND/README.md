# Desafío - Soft Jobs

## Descripción
La empresa Soft Jobs ha iniciado el desarrollo de una plataforma que busca apoyar a la comunidad de desarrolladores juniors a conseguir trabajos cortos y sencillos para acumular experiencia laboral y mejorar sus oportunidades.

En este desafío serás backend developer de la empresa y deberás crear un servidor para la autenticación y autorización de usuarios usando JWT.

Deberás descargar el material de apoyo en el que encontrarás una aplicación cliente desarrollada con React preparada para consumir las rutas de tu servidor.

Para realizar este desafío necesitarás ejecutar el siguiente script sql en tu terminal psql para crear la base de datos y la tabla que utilizaremos:

```
CREATE DATABASE softjobs;
\c softjobs;

CREATE TABLE usuarios (
    id SERIAL,
    email VARCHAR(50) NOT NULL,
    password VARCHAR(60) NOT NULL,
    rol VARCHAR(25),
    lenguage VARCHAR(20)
    );

SELECT * FROM usuarios;
```


Tu servidor debe:
- Permitir el registro de nuevos usuarios a través de una ruta POST /usuarios.
- Ofrecer la ruta POST /login que reciba las credenciales de un usuario y devuelva un token generado con JWT. Se debe incluir el payload del token el email del usuario registrado.
- Disponibilizar una ruta GET /usuarios para devolver los datos de un usuario en caso de que esté autenticado, para esto:
    - Extraiga un token disponible en la propiedad Authorization de las cabeceras.
    - Verifique la validez del token usando la misma llave secreta usada en su firma.
    - Decodifique el token para obtener el email del usuario a buscar en su payload.
    - Obtenga y devuelva el registro del usuario.

## Authors

- [@Crispole](https://github.com/Crispole)

