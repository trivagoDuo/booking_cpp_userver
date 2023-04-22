# booking_cpp_userver <img src="./frontend/public/Logo.png" align='right' width="30%">
[Readme на русском доступно тут](./README_RU.md)

Booking service for hotels, rooms and private homes like booking.com, trivago, etc. With
personal accounts for the buyer, seller and administrators of the platform, with different variants of calculation (both at check-in and online)

## Stack

- ### Backend
    - C ++
      The prerequisite for the creation of this project
    - [Userver framework](https://github.com/userver-framework/userver)
      Ready service solution, to spend time only on writing the logic of the service, writing handlers and work with the database
    - [next.js](https://nextjs.org/)
      Read more in the frontend
- ### Frontend
    - [TypeScript](https://www.typescriptlang.org/)
      Typed js, will simplify data validation and help detect errors at compile time
    - [Next.js](https://nextjs.org/)
      Setting up over React with the backend, the choice fell on this particular framework because of the preender on the server side
  (for indexing by search engines), improved work with React components (will be detected only those components that need to be displayed),
  as well as the presence of routing, improved optimization and support for integration with other frameworks
    - [Eslint](https://eslint.org/)
      For fast refactoring according to predefined rules and for detecting errors while writing code
    - [Redux toolkit](https://redux-toolkit.js.org/)
      An improved version of Redux, which solves some of its problems, is a tool for managing data state and UI in JavaScript applications with a large number of entities.
    - [Tailwind](https://tailwindcss.com/)
      Offers pre-designed widgets for building a site from scratch with quick UI development, while Bootstrap comes with a set of pre-styled
  adaptive mobile components that have a defined UI set.
      

## Engines

It is possible to run on Linux and with Docker

## Build
First, you need to clone the repository
```
git clone https://github.com/trivagoDuo/booking_cpp_userver.git
```
Then you need make and g++ to compile, install them.

Next, run one of the build options, either debug build or release build, respectively:
```
make build-debug
```

or

```
make build-release
```

Framework will check which dependencies are missing and ask you to install them, just follow its instructions

## Launch build

- Go to the build directory (build_debug or build_release)
- To run it for the first time, write in the console
```
make start-booking_cpp_userver
```
- For subsequent runs, write in the console
```
make start-booking_cpp_userver/fast
```

## Makefile

Makefile contains typicaly useful targets for development:

* `make build-debug` - debug build of the service with all the assertions and sanitizers enabled
* `make build-release` - release build of the service with LTO
* `make test-debug` - does a `make build-debug` and runs all the tests on the result
* `make test-release` - does a `make build-release` and runs all the tests on the result
* `make service-start-debug` - builds the service in debug mode and starts it
* `make service-start-release` - builds the service in release mode and starts it
* `make` or `make all` - builds and runs all the tests in release and debug modes
* `make format` - autoformat all the C++ and Python sources
* `make clean-` - cleans the object files
* `make dist-clean` - clean all, including the CMake cached configurations
* `make install` - does a `make build-release` and run install in directory set in environment `PREFIX`
* `make install-debug` - does a `make build-debug` and runs install in directory set in environment `PREFIX`
* `make docker-COMMAND` - run `make COMMAND` in docker environment
* `make docker-build-debug` - debug build of the service with all the assertions and sanitizers enabled in docker environment
* `make docker-test-debug` - does a `make build-debug` and runs all the tests on the result in docker environment
* `make docker-start-service-release` - does a `make install-release` and runs service in docker environment
* `make docker-start-service-debug` - does a `make install-debug` and runs service in docker environment
* `make docker-clean-data` - stop docker containers

Edit `Makefile.local` to change the default configuration and build options.

## License
GNU General Public License v3.0

Permissions of this strong copyleft license are conditioned on making available complete source code of
licensed works and modifications, which include larger works using a licensed work, under the same license.
Copyright and license notices must be preserved. Contributors provide an express grant of patent rights.

## Userver template license

The original template is distributed under the [Apache-2.0 License](https://github.com/userver-framework/userver/blob/develop/LICENSE)
and [CLA](https://github.com/userver-framework/userver/blob/develop/CONTRIBUTING.md). Services based on the template may change
the license and CLA.
