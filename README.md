# Full Stack FastAPI, PostgreSQL, Neo4j & Nuxt 3 Base Project Generator

[![Build Status](https://app.travis-ci.com/whythawk/full-stack-fastapi-postgresql.svg?branch=master)](https://app.travis-ci.com/whythawk/full-stack-fastapi-postgresql)

Accelerate your next web development project with this FastAPI/Nuxt.js base project generator.

This project is for developers looking to build and maintain full-feature progressive web applications using Python on the backend / Typescript on the frontend, and want the complex-but-routine aspects of auth 'n auth, and component and deployment configuration, taken care of, including interactive API documentation. 

This is a comprehensively updated fork of [Sebastián Ramírez's](https://github.com/tiangolo) [Full Stack FastAPI and PostgreSQL Base Project Generator](https://github.com/tiangolo/full-stack-fastapi-postgresql). FastAPI is updated to version 0.99 (July 2023), SQLAlchemy to version 2.0 (July 2023), and the frontend to Nuxt 3.6 (July 2023).

- [Screenshots](#screenshots)
- [Key features](#key-features)
- [How to use it](#how-to-use-it)
  - [Getting started](./docs/getting-started.md)
  - [Development and installation](./docs/development-guide.md)
  - [Deployment for production](./docs/deployment-guide.md)
  - [Authentication and magic tokens](./docs/authentication-guide.md)
  - [Websockets for interactive communication](./docs/websocket-guide.md)
- [More details](#more-details)
- [Help needed](#help-needed)
- [Release notes](#release-notes)
- [License](#license)
  
## Screenshots

<details>
  <summary>
  Click to unfold usage
  </summary>

### App landing page

![Landing page](img/landing.png)

### Dashboard Login

![Magic-link login](img/login.png)

### Dashboard User Management

![Moderator user management](img/dashboard.png)

### Interactive API documentation

![Interactive API docs](img/redoc.png)

### Enabling two-factor security (TOTP)

![Enabling TOTP](img/totp.png)

</details>

## Key features

<details>
  <summary>
  Click to unfold usage
  </summary>

This FastAPI, PostgreSQL, Neo4j & Nuxt 3 repo will generate a complete web application stack as a foundation for your project development.

- **Docker Compose** integration and optimization for local development.
- **Authentication** user management schemas, models, crud and apis already built, with OAuth2 JWT token support & default hashing. Offers _magic link_ authentication, with password fallback, with cookie management, including `access` and `refresh` tokens.
- [**FastAPI**](https://github.com/tiangolo/fastapi) backend with [Inboard](https://inboard.bws.bio/) one-repo Docker images:
  - **SQLAlchemy** version 2.0 support for models.
  - **MJML** templates for common email transactions.
  - **Metadata Schema** based on [Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#section-3) for inheritance.
  - **Common CRUD** support via generic inheritance.
  - **Standards-based**: Based on (and fully compatible with) the open standards for APIs: [OpenAPI](https://github.com/OAI/OpenAPI-Specification) and [JSON Schema](http://json-schema.org/).
  - [**Many other features**]("https://fastapi.tiangolo.com/features/"): including automatic validation, serialization, interactive documentation, etc.
- [**Nuxt/Vue 3**](https://nuxt.com/) frontend:
  - **Authorisation** via middleware for page access, including logged in or superuser.
  - **Model blog** project, with [Nuxt Content](https://content.nuxtjs.org/) for writing Markdown pages.
  - **Form validation** with [Vee-Validate 4](https://vee-validate.logaretm.com/v4/).
  - **State management** with [Pinia](https://pinia.vuejs.org/), and persistance with [Pinia PersistedState](https://prazdevs.github.io/pinia-plugin-persistedstate/).
  - **CSS and templates** with [TailwindCSS](https://tailwindcss.com/), [HeroIcons](https://heroicons.com/), and [HeadlessUI](https://headlessui.com/).
  - **Internationalisation** with [@nuxt/i18n](https://nuxt.com/modules/i18n).
  - **PWA support** with [Vite PWA plugin](https://vite-pwa-org.netlify.app/frameworks/nuxt.html).
- **PostgreSQL** database.
- **PGAdmin** for PostgreSQL database management.
- **Celery** worker that can import and use models and code from the rest of the backend selectively.
- **Flower** for Celery jobs monitoring.
- **Neo4j** graph database, including integration into the FastAPI base project.
- Load balancing between frontend and backend with **Traefik**, so you can have both under the same domain, separated by path, but served by different containers.
- Traefik integration, including Let's Encrypt **HTTPS** certificates automatic generation.
- GitLab **CI** (continuous integration), including frontend and backend testing.

</details>

## How to use it

<details>
  <summary>
  Click to unfold usage
  </summary>

- [Getting started](./docs/getting-started.md)
- [Development and installation](./docs/development-guide.md)
- [Deployment for production](./docs/deployment-guide.md)
- [Authentication and magic tokens](./docs/authentication-guide.md)
- [Websockets for interactive communication](./docs/websocket-guide.md)

</details>

## More details

<details>
  <summary>
  Click to unfold usage
  </summary>

After using this generator, your new project (the directory created) will contain an extensive `README.md` with instructions for development, deployment, etc. You can pre-read [the project `README.md` template here too](./{{cookiecutter.project_slug}}/README.md).

This current release (August 2023) is for FastAPI version 0.99 and is the last before introducing support for Pydantic 2. Since this is intended as a base stack on which you will build complex applications, there is no intention of backwards compatability between releases, and the objective is to ensure that each release has the latest long-term-support versions of the core libraries so that you can rely on your application core for as long as possible.

To align with [Inboard](https://inboard.bws.bio/), Poetry has been deprecated in favour of [Hatch](https://hatch.pypa.io/latest/). This will also, hopefully, sort out some Poetry-related Docker build errors.

You will also find an initial implementation of internationalisation using [@nuxt/i18n](https://nuxt.com/modules/i18n). This is - at this time - a release candidate, so please do update and check their documentation for any changes. The [Vite PWA plugin](https://vite-pwa-org.netlify.app/frameworks/nuxt.html) is also included, along with a Node CLI for generating all necessary app icons. You will see links and notes to this in the [nuxt.config.ts](./{{cookiecutter.project_slug}}/frontend/nuxt.config.ts) file.

</details>

## Help needed

<details>
  <summary>
  Click to unfold usage
  </summary>

The tests are broken and it would be great if someone could take that on. Other potential roadmap items:

- Translation: docs are all in English and it would be great if those could be in other languages.
- Internationalisation: [nuxt/i18n](https://v8.i18n.nuxtjs.org/) is added, but the sample pages are not all translated.
- Code review and optimisation: both the front- and backend stacks have seen some big generational changes, so would be good to have more eyes on the updates to this stack.

</details>

## Release Notes

<details>
  <summary>
  Click to unfold usage
  </summary>

See notes and [releases](https://github.com/whythawk/full-stack-fastapi-postgresql/releases). 

## 0.8.2

Fixing [#39](https://github.com/whythawk/full-stack-fastapi-postgresql/issues/39), thanks to @a-vorobyoff:

- Exposing port 24678 for Vite on frontend in development mode.
- Ensuring Nuxt content on /api/_content doesn't interfere with backend /api/v routes.
- Checking for password before hashing on user creation.
- Updating generated README for Hatch (after Poetry deprecation).
- Minor fixes.

### 0.8.1

- Minor updates to Docker scripts for `build`.

### 0.8.0

- Updates to `frontend`, [#37](https://github.com/whythawk/full-stack-fastapi-postgresql/pull/37) by @turukawa:
  - `@nuxtjs/i18n` for internationalisation, along with language selection component.
  - `@vite-pwa/nuxt` along with button components for install and refreshing the app and service workers, and a CLI icon generator.
  - `@nuxtjs/robots` for simple control of `robots.txt` permissions from `nuxt.config.ts`.

### 0.7.4
- Updates: Complete update of stack to latest long-term releases. [#35](https://github.com/whythawk/full-stack-fastapi-postgresql/pull/35) by @turukawa, review by @br3ndonland
  - `frontend`:
    - Node 16 -> 18
	- Nuxt 3.2 -> 3.6.5
    - Latest Pinia requires changes in stores, where imports are not required (cause actual errors), and parameter declaration must happen in functions.
  - `backend` and `celeryworker`:
    - Python 3.9 -> 3.11
    - FastAPI 0.88 -> 0.99 (Inboard 0.37 -> 0.51)
    - Poetry -> Hatch
    - Postgres 14 -> 15
- Fixed: Updated token url in deps.py [#29](https://github.com/whythawk/full-stack-fastapi-postgresql/pull/29) by @vusa
- Docs: Reorganised documentation [#21](https://github.com/whythawk/full-stack-fastapi-postgresql/pull/21) by @turukawa

[Historic changes from original](https://github.com/tiangolo/full-stack-fastapi-postgresql#release-notes)

</details>

## License

This project is licensed under the terms of the MIT license.
