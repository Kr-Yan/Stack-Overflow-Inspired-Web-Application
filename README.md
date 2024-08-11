# Stack Overflow-Inspired Web Application

## Overview

This project is the culmination of our CS5500: Foundations of Software Engineering course, where we have developed a web application inspired by Stack Overflow. This platform is designed to demonstrate our understanding and application of software engineering principles, including software methodologies, design patterns, testing, and maintenance strategies.

## Project Objectives

The main objectives of this project are:

1. **Application Development**: Design and implement a full-stack web application with functionality similar to Stack Overflow, focusing on scalability, performance, and user experience.
2. **Software Engineering Practices**: Apply best practices in software design, modularization, and coding standards. Ensure the application is secure, maintainable, and robust.
3. **Testing and Quality Assurance**: Utilize Cypress for end-to-end testing and Jest for unit testing to ensure the application meets the functional and non-functional requirements.
4. **Continuous Integration**: Implement a CI pipeline using GitHub Actions to automate the testing and integration process.

## Features

### Functional Requirements

- **User Authentication**: Implement user registration and login functionality.
- **Question and Answer System**: Allow users to post questions, provide answers, and vote on the quality of both questions and answers.
- **Tagging System**: Implement a tagging system to categorize questions.
- **Search Functionality**: Allow users to search for questions using keywords and tags.
- **User Profiles**: Provide users with profiles where they can view their activity and manage their questions and answers.

### Non-Functional Requirements

- **Security**: Implement threat modeling to identify and mitigate potential security risks. Ensure user data is protected through secure authentication and authorization mechanisms.
- **Performance**: Use performance measurement tools to ensure the application responds quickly and handles high traffic effectively.
- **Accessibility**: Ensure the application is accessible to users with disabilities, following best practices in web accessibility.

## Repository Structure

The repository is organized as follows:

- **client/**: Contains all logic for the user interface, implemented using React. The `src/components/` directory holds modular components, and the `cypress/` directory contains all end-to-end and component tests.
- **server/**: Contains the server-side logic of the application, implemented with Node.js and connected to a MongoDB database. Key files include:
  - `server.js`: The entry point for the server application.
  - `config.js`: Contains configuration settings such as database URLs.
  - `init.js`: Used to set up initial test data in the MongoDB database.
  - `destroy.js`: Resets the database to a clean state.
  - `tests/`: Contains all unit tests, implemented using Jest.
- **.github/workflows/**: Contains YAML files for GitHub Actions workflows, automating the CI/CD process.

## Testing

### Coverage of Requirements

Testing is a critical component of our project to ensure all functional and non-functional requirements are met. We meticulously mapped each requirement to specific test cases using Cypress and Jest, ensuring comprehensive test coverage. This mapping is documented within the README to maintain transparency and ease of future maintenance.

### Coverage of Implementation Aspects

In addition to requirement-based testing, we used code coverage tools to ensure our test suite thoroughly exercises all parts of the codebase, including edge cases and error scenarios. We aimed to maximize the coverage of lines, branches, and functions to ensure the robustness of our application.

- **Cypress**: Used for end-to-end tests to validate user flows and integration between the client and server.
- **Jest**: Used for unit tests to validate the correctness of individual functions and components.

## Deployment

Our application is containerized using Docker, which allows for consistent deployment across different environments. The Docker setup includes:

- **Dockerfile**: Located in both `client/` and `server/` directories, defining the build process for the frontend and backend.
- **docker-compose.yml**: Located in the project root, this file orchestrates the entire application, including the MongoDB instance, and runs both the client and server in a single Docker container.

### Deployment Instructions

1. **Install Docker**: Follow the instructions at [Docker Installation Guide](https://docs.docker.com/engine/install/).
2. **Run Docker Compose**:
   - Ensure Docker is running on your machine.
   - Update the MongoDB URL in `docker-compose.yml` to match your setup.
   - From the project root, run `docker-compose up` to build and start the containers.
3. **Access the Application**: Once the containers are up, the application can be accessed via your browser.

## Continuous Integration

We have implemented a CI pipeline using GitHub Actions to automate testing and integration. The workflow is triggered on every pull request to the main branch and includes the following:

- **Jobs**: Separate jobs for running Jest and Cypress tests.
- **Environment Setup**: Ensures the required dependencies and configurations are in place for testing.
- **Test Execution**: Automatically runs the test suites and reports the results.
- **Local Testing**: Configured self-hosted runners for testing the workflow locally before pushing changes to the cloud.

### Git Workflow

Our team followed a Git Flow-inspired workflow:

1. **Main Branch**: Contains stable, production-ready code.
2. **Testdev Branch**: Used for integrating changes from individual feature branches and for thorough testing.
3. **Feature Branches**: Each new feature or bug fix is developed in a separate branch.
4. **Pull Requests**: Used for code reviews and automated testing before merging changes into `testdev` and eventually into `main`.

## Conclusion

This project represents our understanding and application of software engineering principles, from design and implementation to testing and deployment. The result is a robust, scalable web application that showcases our ability to work effectively as a team, apply best practices, and deliver high-quality software.



## List of features
\* indicates extra features

| Feature                   | Description                                                                                                                                                                                            | E2E Tests     | Component Tests | Jest Tests                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------- | --------------- | --------------------------------- |
| View posts                | Responsible for retrieving and displaying the content page of a certain post if the user intends to read this post.                                                                                    | /path/to/test | path/to/test    | server\tests\questionCtrl.test.js |
| Create new posts          | When users upload the content, censor the questions and publish them online on Stack Overflow.                                                                                                         | /path/to/test | path/to/test    | server\tests\questionCtrl.test.js |
| Search for existing posts | User can search and retrieve of lists existing posts on StackOverflow by query word and apply filter                                                                                                   | /path/to/test | path/to/test    | server\tests\questionCtrl.test.js |
| Commenting on posts       | Post users’comments for a specific post, and store the comment information in our database.                                                                                                           | /path/to/test | path/to/test    | server\tests\answerCtrl.test.js   |
| Voting on posts           | StackOverflow registered members can vote the Post up and down only once and display the overall voting to all users.                                                                                  | /path/to/test | path/to/test    | server\tests\voteCtrl.test.js |
| Tagging posts             | Users can tag the post at least 1 up to 5 by searching up existing tags or creating new tags when creating new posts. Then the post will be included in the list of all posts containing the same tag. | /path/to/test | path/to/test    | server\tests\questionCtrl.test.js |
| User profile              | Represents some information on the web using information related to a specific user account.                                                                                                           | /path/to/test | path/to/test    | server\tests\answerCtrl.test.js server\tests\questionCtrl.test.js server\tests\voteCtrl.test.js  |
| Post moderation           | Analyze a recent post or a comment, check if it meets certain standards and guidelines                                                                                                                 | /path/to/test | path/to/test    | path/to/test                      |
| * Saving post             | Users can save the post to existing lists or create new lists by clicking the save button. Then the user can access the “saves” page to see all checklists of saved posts and access those posts.    | /path/to/test | path/to/test    | server\tests\userCtrl.test.js     |
| * Follow the question     | Add a post to the ‘following post’ section in the user’s profile and send a notification if there are activities of the posts                                                                       | /path/to/test | path/to/test    | server\tests\userCtrl.test.js     |
| * User Account            | Authentication user information and assign sessions and keep the status of records. if a new user, register accounts allow users to member-only features.                                              | /path/to/test | path/to/test    | server\tests\userCtrl.test.js     |

## Instructions to generate and view coverage report

#### Move to Server directory and run jest test
cd server
npx jest --runInBand --coverage
#### Report will be under
server\coverage\lcov-report\index.html

## Authors

- Kairuo Yan
- Cheng Shi
