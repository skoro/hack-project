## Hack lang project boilerplate

This is [Hack](https://docs.hhvm.com/hack/) project boilerplate based on steps from the official [documentation](https://docs.hhvm.com/hack/getting-started/starting-a-real-project).

## Getting started

Make sure [Docker](https://docs.docker.com/engine/install/) is installed on your development environment, this is the most preferable way to start with Hack.

Create a project, don't omit `--no-install` option, dependencies will be installed later on:
```sh
docker run --rm -it -v ${PWD}:/app composer create-project -s dev --no-install skoro/hack-project YOUR_PROJECT
```

Change to the project folder and create hhvm container:
```sh
cd YOUR-PROJECT
docker run -d -it --name YOUR_PROJECT -v ${PWD}:/mnt/project -w /mnt/project hhvm/hhvm
```

Now dependencies can be installed:
```sh
docker exec -it YOUR_PROJECT php composer.phar install
```

## VSCode

Install [Hack](https://marketplace.visualstudio.com/items?itemName=pranayagarwal.vscode-hack) extension, open the extension settings and configure the following parameters:
- Remote mode: `docker`
- Container name: `YOUR_PROJECT`
- Workspace path: `/mnt/project`

## FAQ

- Why is `composer.phar` here ?

    The hhvm docker image doesn't contain `composer` which is needed for 
    installing project dependencies.
