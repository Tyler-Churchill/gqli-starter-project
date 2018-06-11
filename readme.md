# GQLI Start Project

Instantly create a GraphQL server. Out of the box opinionated code modularization with Apollo Server under the hood. Skip the boilerplate

- [GQLI](https://github.com/Tyler-Churchill/gqli) - Core package
- [GQLI-CLI](https://github.com/Tyler-Churchill/gqli-cli) – Manage your GraphQL server with an easy to use command line interface
- [Project Structure](#project-structure) – More information on how you should structure your GQLI project.

## Quick Start

### Get a GraphQL server running now!

### Prerequisites

- [Node](https://nodejs.org/en/)
- Your favourite editor (VSCode, sublime, webstorm etc...)

## Installation via the CLI tool (recommended)

run

```
npm install -g gqli-cli
```

### Create a project

```
gqli create [options] <project_name> [project_path]
```

Example:

```
gqli create ./first-project
```

and finally cd into your new projects path and run

```
gqli

----
node index.js
☄️ Server ready at http://localhost:4000/
```

## Installation via core package

run

`npm install gqli`

create a new javascript file

#### index.js

```javascript
const GQLIServer = require('gqli');
const server = new GQLIServer();
server.start();

----
node index.js
☄️ Server ready at http://localhost:4000/
```

or for es2015

#### index.js

```javascript
import GQLIServer from 'gqli';
const server = new GQLIServer();
server.start();

----
npx babel ./ -d dist --copy-files && node dist/index.js
☄️ Server ready at http://localhost:4000/
```

## Project Structure

Basic music related project

```
your-project/
├── npm_modules/
├── modules/
│   ├── users/
│   │   ├── resolvers.js
│   │   ├── schema.graphql
│   └── songs/
│   │   ├── resolvers.js
│   │   ├── schema.graphql
│   └── albums/
│       ├── resolvers.js
│       ├── schema.graphql
├──index.js (contains the GQLIServer initialization)
└──.gqlirc
```

`resolvers(.js,ts)` and `schema.graphql` will be auto detected and used by GQLI. You can change what directory GQLI will scan for schema and resolver files by edting `.gqlirc` in your projects root directory.

```json
{
  "moduleDirectory": "../your/path/here"
}
```
