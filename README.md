# Chirpfy

This project is the backend for Chirpfy, the Twitter clone.

## Installation

We use [yarn](https://yarnpkg.com/) package manager, to install project dependencies, run:

```bash
yarn
```

## Configuration

We use PostgreSQL with [typeorm](https://www.npmjs.com/package/typeorm), to config you need to run local database (preferably using Docker image).

Create file in root path of project named `ormconfig.json` and use `ormconfig.example.json` as a basis for adding your settings:

```typescript
[
  {
    "name": "default",
    "type": "postgres",
    "host": "localhost",
    "port": 5432,
    "username": "db_username",
    "password": "db_password",
    "database": "chirpfy_db",
    "entities": [
      "./src/modules/**/infra/typeorm/entities/*.ts"
    ],
    "migrations": [
      "./src/shared/infra/typeorm/migrations/*.ts"
    ],
    "cli": {
      "migrationsDir": "./src/shared/infra/typeorm/migrations"
    }
  }
]

```

## Start coding

After install project dependencies and add your database configurations, are you ready to start coding. To do this, run:

```typescript
yarn dev:server
```

**Use all the powers of TypeScript to write clean code, typed code.**

**Keep it simple!**

## Tests

We use jest for unit tests.

Run tests using:
```typescript
yarn test
```

Code your tests inside `src/__tests__`.
Use folders to separate, example:

`CreateUserService.ts` add to: `src/__tests__/services/CreateUserService.spec.ts`

**EVER** create fakes and mocks to use in tests.

**NEVER** test directly your code, use fakes for this.


**TIP:** Try to code test first (TDD - Test-driven Development).
____

Almost always what we test is services. This is where the business rules to be validated are. Evaluate if you understand that you need to test something else.

## Commit and Pull Request
Always create a branch from the master before starting a new development.

Always use a lowercase name in the name of the branch and messages of the commits.

Use prefixes to facilitate reading and make the tree simple to understand. For example, create a branch `feature/feed-post` and commit `feat: create user feed posts`.

The most branch prefix used are:
```typescript
bugfix
feature
misc
doc
```

And commits messages prefix:

```typescript
fix:
feat:
misc:
doc:
```

Let us know if you have any other suggestions.

Use as many commits as needed, but try to maintain logic. Use 1 commit if it is something small or more if it is a bigger development. Try not to change too many files in a single Pull Request to facilitate code review, to facilitate a possible rollback and to know exactly where to return if necessary.

After finishing your development and pushing your commits, open a Pull Request from your branch to the master branch. Describe what was done to help developers review the code and see if everything is OK.

We use **Rebase** method. **Avoid using merge**.

And the **most important**: ask for help if you need.

## Build

The builded files go to the /dist folder converted to JavaScript.
To build, run:

```typescript
yarn build
```
____________
## License
[MIT](https://choosealicense.com/licenses/mit/)
