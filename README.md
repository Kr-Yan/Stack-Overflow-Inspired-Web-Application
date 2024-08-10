[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/37vDen4S)

# Final Team Project for CS5500

Login with your Northeastern credentials and read the project description [here](https://northeastern-my.sharepoint.com/:w:/g/personal/j_mitra_northeastern_edu/ETUqq9jqZolOr0U4v-gexHkBbCTAoYgTx7cUc34ds2wrTA?e=URQpeI).

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

## Extra Credit Section (if applicable)
