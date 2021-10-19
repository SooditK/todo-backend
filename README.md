# Task Management REST API

This is a full featured Task Management REST API back-end built with Node.js and MongoDB. Features include:

- Pagination and filtering of server responses to avoid slow page load times.
- Full CRUD features for User and Task instances.
- Hash encryption of passwords and access management with JWT tokens.
- Restricted user access to CRUD operations based on JWT tokens.

### SETUP INSTRUCTIONS

To use this code you will require an account with [SendGrid](https://signup.sendgrid.com/). Sign-up is free and no credit card is required to access a free-tier API Key.

Node.js version 12+ and npm must be installed on your machine. In terminal type the following commands:

```
sudo npm install
mkdir config
cd config
touch dev.env
vim dev.env
```

Insert the following lines in `dev.env`, replacing all `<content>` with your own information:

```
PORT=<port number>
SGMAIL_EMAIL=<your email address>
MONGODB_URL=<mongodb connection string>
SENDGRID_API_KEY=<api key>
JWT_SECRET=<unique key of your choice to generate JSON web tokens>
```

To run the web server return to the root of the repository and type:

```
npm run dev
```

Alternatively you may name `config/prod.env` or `config/staging.env` and appropriately run the web server with `npm run prod` or `npm run staging`.

## API USAGE

### END POINTS FOR USER

##### POST - '/users/ - TO CREATE USER ACCOUNT

##### POST - "/users/login" - TO LOGIN USER

##### POST - "/users/logout" - TO LOGOUT USER

##### POST - "/users/logoutAll" - TO LOGOUT USER FROM ALL SESSIONS

##### GET - "/users/me" - TO GET USER INFO

##### PATCH - "/users/me" - TO UPDATE USER INFO

##### DELETE - "/users/me" - DELETE USER ACCOUNT

##### POST - "/users/me/avatar" - UPLOAD USER AVATAR

##### DELETE - "/users/me/avatar" - DELETE USER AVATAR

##### GET - "/users/me/avatar" - FETCH USER AVATAR

### END POINTS FOR TASKS ()

Remember to add Bearer Token🐼

##### POST - "/tasks" - CREATE TASKS

##### DELETE - "/tasks/:id" - DELETE TASK BY id

##### PATCH - "/tasks/:id" - UPDATE TASK BY id

##### GET - "/tasks" - GET - RETREIVE TASKS. URL OPTIONS:

    /tasks?completed=true
    /tasks?limit=10&skip=0
    /tasks?sortBy=createdAt_asc
    /tasks?sortBy=updatedAt_desc

##### GET - "/tasks/:id" - RETREIVE SPECIFIC TASK BY ID

For feedback or inquiries please contact Soodit at sooditkumar@duck.com
