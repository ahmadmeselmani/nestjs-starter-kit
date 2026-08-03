

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

# Kit de Inicio de NestJS 🚀

<div align="center">
  <img src="https://github.com/mr-meselmani/nestjs-starter-kit/blob/master/public/words-github-banner.jpg?raw=true" alt="Project Banner" style="width:100%;"/>
</div>

</br>

# Arquitectura

<div align="center">
  <img src="https://github.com/mr-meselmani/nestjs-starter-kit/blob/master/public/nestjs-starter-kit-architecture.jpg?raw=true" alt="Project Banner" style="width:100%;"/>
</div>

</br>

> **_NOTA:_** A cualquier carpeta que no sea un módulo de NestJS se le añade un prefijo `_`, esto mejora la visualización en el editor de código y separa las responsabilidades.

---

## Bienvenido

Bienvenido al Kit de Inicio de NestJS 🚀 Este kit es de código abierto y proporciona un marco de trabajo robusto para backend usando NestJS con Prisma para la gestión de bases de datos, PostgreSQL como base de datos, Zod para la validación de esquemas, el servicio de correo Resend y TypeScript para seguridad de tipos. También incluye autenticación y autorización completas listos para usar, utilizando estrategias de PassportJS con tokens JWT de acceso y actualización.

> **_NOTA:_** Únete gratis al [Servidor de Discord](https://discord.gg/Z8Yf4xj529) de Innovators Lounge para obtener soporte y ser miembro innovador 😎

---

## Tabla de Contenidos

- [Características y Beneficios](#features-and-benefits)
- [Primeros Pasos](#getting-started)
- [Instalación](#installation)
- [Uso](#usage)
- [Configuración de Docker](#docker-setup)
- [Contribuir](#contributing)
- [Patrocinio](#sponsorship) 🤍
- [Diagrama ER Actual](#current-erd)
- [Licencia](#license)

---

## Características y Beneficios

- **NestJS**: Un marco de trabajo progresivo para Node.js para construir aplicaciones del lado del servidor eficientes, confiables y escalables.
- **Autenticación y Autorización**: Solución completa de autenticación de usuario y Control de Acceso Basado en Roles (RBAC) 🎉.
- **Prisma**: Un kit de herramientas de base de datos de código abierto que simplifica el acceso y la gestión de bases de datos.
- **PostgreSQL**: Un potente sistema de base de datos relacional de código abierto.
- **Soporte para TypeScript**: Código fuertemente tipado para una mejor mantenibilidad y escalabilidad.
- **Validación con Zod**: Validación en todo el ciclo de vida de solicitudes y respuestas utilizando esquemas de zod.
- **Docker**: La contenedorización abstracta las herramientas de configuración en cualquier máquina local y facilita el despliegue.
- **Servicio de Correo Resend**: Un servicio de correo rápido y económico para usar en tu proyecto.
- **Arquitectura Modular**: Estructura de código organizada para una mejor separación de responsabilidades.
- **Documentación Local Auto Generada**: Usando [Compodoc](https://github.com/compodoc/compodoc/), después de la instalación ejecuta este comando: `pnpm dlx @compodoc/compodoc -p tsconfig.json -s`

---

## Primeros Pasos

Esta guía te mostrará cómo configurar, ajustar y ejecutar el kit de inicio de NestJS en tu máquina local O saltarte esta sección e ir directamente a Configuración de Docker para evitar instalar herramientas.

### Requisitos Previos

Asegúrate de tener lo siguiente instalado:

- Node.js (versión 20.11.0 o superior)
- npm & pnpm
- PostgreSQL (instalado y en ejecución)

---

## Instalación

Para comenzar con este kit de inicio, sigue estos pasos:

1. Clona el repositorio:
   ```bash
   git clone https://github.com/mr-meselmani/nestjs-starter-kit.git
   ```
2. Navega al directorio del proyecto:

   ```bash
   cd nestjs-starter-kit
   ```

3. Instala las dependencias:

   ```bash
   pnpm install
   ```

4. Configura las Variables de Entorno:

   - Crea un `.env` en el directorio raíz.
   - Copia el contenido de `.env.example` en `.env` y configura cualquier variable de entorno necesaria. Asegúrate de leer las notas escritas dentro del archivo `.env`. Para entornos locales, asegúrate de que `DATABASE_URL` esté configurada para usar `HOST` como `localhost`.

5. Realiza una migración de base de datos usando el script definido en el archivo `package.json` ejecutando:
   ```bash
   pnpm db:migrate
   ```
6. Ejecuta el comando de semilla para poblar la base de datos con algunos datos definidos en `prisma/seed/data`:

   ```bash
   pnpm db:seed
   ```

7. Ejecuta la aplicación:
   ```bash
   pnpm start:dev
   ```

---

## Uso

Después de ejecutar la aplicación, puedes acceder a la documentación de la API de Swagger en `http://localhost:3000/doc`. Puedes modificar el código para que se ajuste a los requisitos de tu proyecto.

---

### Configuración de Docker

Para ejecutar el proyecto usando Docker, asegúrate de que Docker esté instalado y en ejecución en tu máquina. Sigue estos pasos:

1. **Clona el Repositorio**:

   ```bash
   git clone https://github.com/mr-meselmani/nestjs-starter-kit.git
   ```

2. **Navega al Directorio del Proyecto**:

   ```bash
   cd nestjs-starter-kit
   ```

3. **Configura las Variables de Entorno**:

   - Crea un `.env` en el directorio raíz.
   - Copia el contenido de `.env.example` en `.env` y configura cualquier variable de entorno necesaria. Para Docker, asegúrate de que `DATABASE_URL` esté configurada para usar `HOST` como `postgres` (el nombre del servicio de base de datos en el archivo `docker-compose.yml`).

4. **Ejecuta el Proyecto con Docker Compose**:

   ```bash
   docker-compose up -d
   ```

   Este comando construirá y ejecutará la aplicación y un contenedor de PostgreSQL, tal como se define en el archivo `docker-compose.yml`.

5. **Aplica las Migraciones de Base de Datos**:
   Una vez que los contenedores estén en ejecución, aplica las migraciones de base de datos usando el siguiente comando:

   ```bash
   docker-compose exec app pnpm prisma migrate deploy
   ```

   Reemplaza `app` con el nombre del servicio en tu archivo `docker-compose.yml` si es diferente.

6. **Accede a la Aplicación**:
   La aplicación debería estar disponible en `http://localhost:3000/doc` en tu máquina local.

---

## Contribuir

Damos la bienvenida a las contribuciones de la comunidad. Si deseas contribuir, por favor sigue estos pasos:

1. Abre un problema (issue) en el repositorio de GitHub.
2. Realiza un fork del repositorio.
3. Crea una nueva rama para tu característica o corrección de error.
4. Realiza tus cambios y haz commit.
5. Haz push de tu rama y crea un pull request **`solo a la rama de desarrollo`**.
6. Espera la revisión y aceptación.

Asegúrate de que tu código siga los estándares de codificación del proyecto y esté muy bien probado.

---

## Patrocinio

Si encuentras este proyecto útil y deseas apoyar su desarrollo, considera patrocinarlo. Puedes enviar contribuciones usando la siguiente criptomoneda:

- **Solana**: **`HevTaAxB36eqHFhLEYcDnZJtySBebQUbaxBBaau5qyin`**

Tus contribuciones ayudarán a garantizar el desarrollo y mantenimiento continuo de este kit de inicio. Gracias por tu apoyo 🤍

---

## Diagrama ER Actual

<div align="center">
  <img src="https://github.com/mr-meselmani/nestjs-starter-kit/blob/master/public/current-erd.png?raw=true" alt="Project Banner" style="width:100%;"/>
</div>

---

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.

---

Gracias por explorar el Kit de Inicio de NestJS 🚀 Feliz programación 🎉
