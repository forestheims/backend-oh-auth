# Why I Autha...

<sub style="color: #ccc">I'm sorry for the name</sub>

## Getting Started

Use [this template](https://github.com/alchemycodelab/backend-why-i-autha) to get started.

### Learning Objectives

- Use OAuth to create & log in users
- Use Express middleware to ensure requests are authenticated
- Use cookies to store user data
- Use JWTs for storing user data in cookies
- Sign & verify JWTs to ensure validitity
- Utilize GitHub OAuth for authentication

### Description

You've been selected to interview at GitHub for a Software Developer position. As part of the interview process, you've been asked to build an authentication system that uses GitHub's OAuth.

You've been provided a template that contains an API and some tests, but needs two of the routes implemented: `/api/v1/github/login` and `/api/v1/github/login/callback`.

In order to complete those routes, you'll need to implement the methods in the `/utils/github.js` file.

**You will need to [create an OAuth app on GitHub](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app) for this deliverable**

### Acceptance Criteria

- User is redirected to the GitHub authorization page when visiting `/api/v1/github/login`
- `/api/v1/github/login/callback` implements the GitHub OAuth flow to get a user's profile information (namely `login`, `avatar`, and `email`)
  - Upon getting the profile information, find the existing `GithubUser` by their username
    - If one doesn't exist, create it
  - Create a JWT with that user's information
  - Set the JWT in a server-side cookie, then redirect the user to `/api/v1/github/dashboard`

### Rubric

| Task                                        | Points |
| ------------------------------------------- | ------ |
| `/api/v1/github/login` implemented          | 1      |
| `/api/v1/github/login/callback` implemented | 2      |
| `exchangeCodeForToken` implemented          | 2      |
| `getGithubProfile` implemented              | 2      |
| Logging in sets a **server-side** cookie    | 1      |
| Existing tests pass                         | 2      |
