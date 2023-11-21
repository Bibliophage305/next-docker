# Next-Docker

Next-Docker is a preconfigured Docker environment tailored to streamline interaction with next.js projects using the next CLI.

## Installation

### Creating a New Project

To create a new next.js project and set it up within the Next-Docker environment:

```bash
npx next-docker init <PROJECT>
```

This command automates project creation by executing `create-next-app <PROJECT>` and copying the necessary Docker configurations for the new project.

### Installing Next-Docker in an Existing next Project

If you already have an existing next.js project and want to integrate it with the Next-Docker environment, you can use the `install` command:

```bash
npx next-docker install
```

This command sets up the necessary configurations and Docker environment within your current next project.

## Usage

### Commands Proxied to next

The following commands are proxied directly to next in the app container:

- `start`
- `export`
- `dev`
- `lint`
- `telemetry`
- `info`
- `experimental-compile`
- `experimental-generate`

To use these commands, execute:

```bash
npx next-docker <COMMAND> [args]
```

### next Build

To avoid collision with Docker Compose's `build`, use `next-build` to run next's build in the app container:

```bash
npx next-docker next-build [args]
```

### Commands proxied to binaries in the app container

The commands `next`, `node`, `npm`, `npx`, `yarn`, `pnpm`, `pnpx`, `bun`, and `bunx` are proxied to the binaries in the app container. Use them by running:

```bash
npx next-docker <COMMAND> [args]
```

### Shell Access

Initiate a terminal in the app container using:

```bash
npx next-docker shell
```

### Postgres Operations

Commands prefixed with `postgres` are forwarded to the Postgres container:

- `npx next-docker postgres [args]`: Execute Postgres-related commands.
- `npx next-docker postgres shell`: Initiate a terminal in the Postgres container.
- `npx next-docker psql`: Open a Postgres CLI terminal in the Postgres container.

### Docker Compose Proxy

Any other command is proxied to Docker Compose.
