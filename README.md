## Hack lang project boilerplate

This is [Hack](https://docs.hhvm.com/hack/) project boilerplate based on steps from the official [documentation](https://docs.hhvm.com/hack/getting-started/starting-a-real-project).

## What next ?
Install HHVM (either from repository or docker image). Clone this repository and in case of the docker image create container:
```sh
docker run -d --name hhvm-project -v ${PWD}:/mnt/project -w /mnt/project hhvm/hhvm
```

If your editor is VSCode install [Hack](https://marketplace.visualstudio.com/items?itemName=pranayagarwal.vscode-hack) extension.

## FAQ
- Why is `composer.phar` here ?
    The hhvm docker image doesn't contain `composer` which is needed for 
    installing project dependencies.
