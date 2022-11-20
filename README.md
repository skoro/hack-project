## Hack lang project boilerplate

This is [Hack](https://docs.hhvm.com/hack/) project boilerplate based on steps from the official [documentation](https://docs.hhvm.com/hack/getting-started/starting-a-real-project).

## Getting started

Make sure [Docker](https://docs.docker.com/engine/install/) is installed on your development environment, this is the most preferable way to get started with Hack language.

Build the application image:
```sh
docker-compose build --no-cache
```

Install dependencies:
```sh
docker-compose up -d
docker-compose exec hhvm composer install
```

Check that the application is working:
```sh
curl http://localhost/
```

## VSCode

Install [Hack](https://marketplace.visualstudio.com/items?itemName=pranayagarwal.vscode-hack) extension, open the extension settings and configure the following parameters:
- Remote mode: `docker`
- Container name: `YOUR_PROJECT`
- Workspace path: `/var/www`
