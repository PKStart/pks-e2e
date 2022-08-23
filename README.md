PKStart E2E tests
=================

Testing locally
---------------

### Code quality checks
Husky is set up to run the linter and check code formatting before each commit.
These checks however can also be run using the `npm run lint` and `npm run format:check` commands for the entire repository.

### Web frontend e2e tests
Frontend e2e tests can run in two ways:
* In "watch" mode using the `npm run watch:web` command during development, especially while writing the tests themselves. This will open the Cypress UI where we can see each step while the tests are running.
* In "headless" mode using the `npm run test:web` command, this will run all the tests using a headless browser all in the bacground.

> Make sure everything is running in the background (DB, API, Web).

> For each fresh test run the DB should be cleared using `npm run clear:db` and then `npm run start:db` in the `pks-api` repository.


Testing in Docker
-----------------

It is now possible to run all Web e2e tests in a completely encapsulated docker environment. **Note** that this workflow will actually pull the current `develop` branch of the `pks-api` and `pks-web` applications directly from Github, and it is not using the local files!
To run the tests this way:
```shell
npm run test:web:docker
```
