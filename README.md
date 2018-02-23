# Node / TypeScript example

What is this application? Who uses it, and what do they do with it? Which team is responsible for it?

What technologies does this project use? Links to technical documentation might live here.

## Project structure

| Name                 | Description                                                                                   |
| -------------------- | --------------------------------------------------------------------------------------------- |
| .circleci            | Contains YAML to configure Circle build & deploy pipeline                                     |
| .ebextensions        | Contains configuration for Elastic Beanstalk app (server config, ports, scaling policy, etc.) |
| config               | Configuration templates for Node app (switches, environment variables, initial state, etc.)   |
| dist                 | Contains server/client distributables                                                         |
| node_modules         | Contains all our lovely dependencies                                                          |
| src/client/js        | Browser JavaScript / TypeScript sources                                                       |
| src/client/css       | Browser stylesheet sources                                                                    |
| src/client/static    | Static assets that will be used client side                                                   |
| src/server/controllers | Controllers define functions that respond to various HTTP requests                          |
| src/server/services  | Services fetch data on behalf of controllers (e.g. from other APIs)                           |
| src/server/util      | General-purpose utilities that don't fit anywhere else                                        |
| src/server/views     | HTML templates                                                                                |
| src/app.ts           | Express app                                                                                   |
| src/config.ts        | Uses Convict to parse environment variables                                                   |
| src/index.ts         | Wraps Express app (so app.ts can be tested in a mock server)                                  |
| src/types            | Holds .d.ts files not found on DefinitelyTyped.                                               |
| devConfig.json       | Environment variables to use in local development (be careful about committing to this)       |
| package.json         | Lists NPM dependencies and build scripts                                                      |
| tsconfig.json        | Configures the TypeScript compiler                                                            |

## Local development

### Prerequisities
- Node v8.0+
- NPM v5.1+
- Mac OS or Windows 7

### Quick start
```bash
git clone ...
npm install
npm start
# go to localhost:1234 (or whatever...)
```

## NPM tasks

List all the _top level_ NPM tasks in the project - subtasks don't need to be documented. For example, you would document `test-server` but not `test-server:unit` or `test-server:integration`.

Example:

| Name                     | Description                                                                                   |
| ------------------------ | --------------------------------------------------------------------------------------------- |
| clean                    | Deletes and regenrates dist folder                                                            |
| develop                  | Start app, watch files, compile continuously and restart as necessary                         |
| dist                     | Compile all resources one time                                                                |
| start                    | Alias for 'develop'                                                                           |
| ngrok                    | If installed, uses ngrok to generate public tunnel to local zone                              |

## API

Here you might list the routes of your webservice.

### GET /health

Heartbeat route for AWS. Should always return HTTP 200

### GET /tree/:id

Request JSON for your favourite species of tree. Returns a `TreeSpeciesMetadata`.

### GET /

Test splash page.
