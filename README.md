# Tesla Ball

## Lightning Service Provider built on top of FastAPI asynchronous web framework

![Tesla Ball Banner](./static/tesla-banner.png "Tesla Ball Banner")

WARNING: Currently this project primarily targets Lightning Node Daemon (LND) implementation

## Run the server using [uvicorn](https://www.uvicorn.org)

Uvicorn is an ASGI web server implementation for Python with great compatibility with the chosen
framework for this project, [FastAPI](https://fastapi.tiangolo.com).

```bash
$ uvicorn serve:app --log-config log_conf.yml
```

## Contributions

This project uses [poetry](https://python-poetry.org) package manager to keep track of dependencies.
You can set up your local environment as such

```bash
$ pip install --user poetry
> ...
$ poetry install --with dev  # install with development dependencies
> Installing dependencies from lock file
>
> Package operations: 41 installs, 1 update, 0 removals
>
>   • ...
>   • ...
>   • ...
>   • ...
>
> Installing the current project: tesla-ball (0.1.0)
```

### `symbol not found in flat namespace '_CFRelease'` on ARM64 architecture systems

No idea why this happens when installing `grpcio-tool` using [poetry](https://python-poetry.com)
but you can just download without rebuilding from source on M1/M2 MacBooks as such

```bash
$ conda install grpcio-tools  # if using Anaconda3 / Miniconda3 for virtual environment
```

### Compile Proto files located at `~~/protos`

And turn them to Python modules at `~~/src/protos` by using the following command

```bash
$ poetry run compile-protos
```

Now you can begin contributing code and logic to the project.

## Run the project with Hot-Reload enabled

Uvicorn allows you to run the ASGI application with hot-reload enabled by adding `--reload` flag
to the command as such:

```bash
$ uvicorn serve:app --log-config log_conf.yml --reload
```

## License

This project is licensed under the terms of the MIT license.