# Internet of Things Exercise

Build an Internet of Things device.

## Concept

The Internet of Things (IoT) is the network of connected physical and virtual devices that communicate with one-another. Often envisioned as "smart devices" -- from smart toasters to home lighting systems to self-driving cars -- IoT devices can sense and respond to their usage, internal state, and external environment. They are often used to collect data and automate tasks.

In this exercise, we will build an IoT device that senses its environment, reports the data it collects to a central server which provides a web dashboard through which users can visualize the data.

## Requirements

The system you will build consists of two independent software sub-systems. Both parts of this project must be stored in this "monorepo" - a single version control repository housing multiple independent subsystems of a single software project.

- client device
- server

A starter `.gitignore` file has been provided for generic Python programming. However, this should be updated as necessary to make sure that any 3rd-party Python modules or dependencies used by the client or server of this project are not included in version control. Use `pip` or `pipenv` to document and install any 3rd-party Python software dependencies for both parts independently.

### Client device

The IoT client device will be built using a [Raspberry Pi](https://www.raspberrypi.com/) and any additional hardware of your choice, with custom programs written primarily in Python.

- The client device must collect data using one or more hardware sensors, such as camera, microphone, temperature sensor, humidity sensor, proximity sensor, etc.
- The client device must do some form of high-level analysis of the data, such as image recognition, speech recognition, classification, aggregation, etc, either using custom code, third-party APIs or code libraries designed for this purpose. In other words, the client device must not only collect raw data, but also must compute the results of some additional analysis of that data.
- The collected data, including the results of any analysis performed, must be sent to the IoT server using a [RESTful API](https://pythonbasics.org/flask-rest-api/) created with `flask` routes. How frequently the client communicates with the server must make sense for your application.
- Data in the body of any request or response between client and server must be formatted as [JSON](https://en.wikipedia.org/wiki/JSON) - typically either an array of objects or a single object, depending on the need.
- Unit tests using [pytest](https://docs.pytest.org/en/7.2.x/) must be written for the client device code that provide at least 50% code coverage of the client code.
- The client must have a Continuous Integration (CI) workflow using [GitHub Actions](https://github.com/features/actions) that automatically builds and tests the updated client subsystem every time a pull request is approved and code is merged into the `main` branch.

See some setup instructions and helpful resources for the Raspberry Pi in the [./pi-setup.md](./pi-setup.md) file.

### Server

The IoT server will be built using the Python [flask](https://palletsprojects.com/p/flask/) framework and a [MongoDB](https://www.mongodb.com/) database connected via [pymongo](https://pymongo.readthedocs.io/en/stable/), continuously deployed to a web server hosted with [Digital Ocean](https://m.do.co/c/4d1066078eb0) (note that this link includes a referral code that will give you $200 of credit, which is more than enough to cover this project. Just remember to cancel your account once the project is over to avoid being charged when the credit expires).

- The server must store the data received in a database and provide a web dashboard for users to visualize the data.
- Unit tests using `pytest`and [pytest-flask](https://pytest-flask.readthedocs.io/en/latest/) must be written for the server code that provide at least 50% code coverage of the server code.
- The server must have a Continuous Integration / **Continuous Deployment** (CI/**CD**) workflow using [GitHub Actions](https://github.com/features/actions) that automatically builds, tests, and deploys the updated server subsystem every time a pull request is approved and code is merged into the `main` branch.

## Developer workflow

### Task boards

ALl teams must use task boards to manage their work.

- The task boards must have at least 4 columns: "To Do", "In Progress", "Awaiting Review", "Done".
- Each task must be assigned to the developer(s) responsible for implementing it.
- Each task must be positioned on the board in the appropriate column representing its status.

### Standup meetings

Each team must have at least 3 standup meetings per week. In these meetings, each developer must answer three questions:

- what have you done since last meeting?
- what are you working on now?
- is anything blocking your way?

One team member must collect the answers each team member gave to each of these questions and post a report of the standup to the team's communication channel. For example:

```
Standup Report - January 24 2023
--------------------------------

Flora Rosenkrist @florarose
- did: implement upload picture functionality for upload item page fixed formatting of upload item page
- doing: figure out edit profile info not filling in
- blockers: none

Chad Mugabe @chmug
- did: finished saved posts and past uploads, resolved conflict and merged past uploads branch
- doing: add box headings to both pages, figure out background colour issue on user profile, edit profile pages
- blockers: none

Trish McPerson @tmcfer
- did: finished user and edit profile
- doing: working on the background issue
- blockers: studying for a midterm till Saturday

Pat Sachin @patsach
- did: map page, merged trish's pull request. refactored background code and centered stuff on saved posts and upload.
- doing: map popup, map api integration
- blockers: none
```

### Individual contributions

All team members must have visibly contributed to the code using their own git & GitHub accounts in order to claim that they contributed to the project.

### Feature branch workflow

All code changes must be done in feature branches and not directly in the `main` branch.

To merge code from a feature branch into the `main` branch, do the following:

1. Create a pull request from the feature branch to the `main` branch.
1. Ask a fellow developer to review your code.
1. The reviewer must review the code and run unit tests to verify that the functions behave as expepcted.
1. If the reviewer has any concerns, discuss then and make any changes agreed upon.
1. Merge the pull request into the `main` branch.
1. Delete the feature branch.
1. Pull the latest changes from the remote `main` branch to your local `main` branch.

**Warning**: the longer you let code sit in a feature branch, the more likely your team is to end up in [merge hell](https://en.wikipedia.org/wiki/Merge_hell). . Merge feature branches into `main` often to avoid this fate.

## Documentation

Replace the contents of the [README.md](./README.md) file with a beautifully-formatted Markdown file including

- a plain-language **description** of your project, including:
- a [badge](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/adding-a-workflow-status-badge) at the top of the `README.md` file showing the result of the latest build/test workflow of the server.
- a link to your package's page on the PyPI website.
- the names of all teammates as links to their GitHub profiles in the `README.md` file.
- instructions for how to configure and run all parts of your project for any developer on any platform - these instructions must work!
- instructions for how to set up any environment variables and import any starter data into the database, as necessary, for the system to operate correctly when run.
- if there are any "secret" configuration files, such as `.env` or similar files, that are not included in the version control repository, exact instructions for how to create them and what their contents should be must be supplied to the course admins by the due date.
