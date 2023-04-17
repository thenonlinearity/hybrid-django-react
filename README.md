## Starter project
# 🤠⚛️ Dockerized hybrid Django React app 
Starter project template using Docker to build a Django app that serves React apps statically (as JavaScript files)

## Tech stack
  - Django (with Rest framework, PostgreSQL, SMTP gmail backend, whitenoise, etc.)
  - React (bundled with webpack and transpiled with babel)
  - Docker
  - Deployment to Heroku

## Prerequisites
  - Docker
  - pip, poetry, pyenv or a similar tool to access [pypi](https://pypi.org/)


## Usage

Simply start the docker container to start working:
```
docker-compose up -d
```

You can then work as usual on your Django project.

The entry point of the React render can be edited from the file `frontend/index.js`

## Debugging with Docker and VSCode

Support for debugging remotely with VSCode is supported out-of-the-box.

To debug with Docker:

1. Run your Docker containers as usual: `docker-compose up -d --build`

3. Start the debug session from VS Code for the `[django:docker] runserver` configuration (either from the Debugger menu or with `F5`)

   - Logs will redirect to your integrated terminal as well.

4. Set some breakpoints in functions or methods executed when needed. Usually it's Model methods or View functions

## Adding external libraries

It's better to install external libraries from from Docker directly

### Python libraries:
   - Production libraries
   ```
   docker-compose exec web poetry add [pip_package]
   ```
   - Development libraries
   ```
   docker-compose exec web poetry add [pip_package] --dev
   ```
### JavaScript libraries:
   - Production libraries
   ```
   docker-compose exec web npm install [npm_package]
   ```
   - Development libraries
   ```
   docker-compose exec web npm install -D [npm_package]
   ```
