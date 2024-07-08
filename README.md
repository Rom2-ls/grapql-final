# GraphQL Efrei

This GraphQL API project is designed to handle user management functionalities along with authentication capabilities using CRUD operations

## Requirements

The project is using pnpm as the package manager.

Install pnpm using: https://pnpm.io/installation

## Installation

Clone the repository using

SSH

```bash
  git clone git@github.com:Rom2-ls/grapql-final.git
```

HTTPS

```bash
  git clone https://github.com/Rom2-ls/grapql-final.git
```

Enter the folder using

```bash
  cd grapql-final
```

Start the database

```bash
  docker compose up -d
```

Run

```bash
  pnpm install
```

to install dependencies

Go inside the backend project and initialise Prisma

```bash
  cd apps/backend-graphql/
  npx prisma generate
```

Now go back to the root folder and start the project

```bash
  cd ../../
  pnpm run dev
```

## Available routes

Create a user

```bash
  mutation {
    register(registerUserInput: {
      name: "user",
      email: "user@example.com",
      password: "password"
    }) {
      id
      name
      email
    }
  }
```

Then you must login, and copy the returned token, it will be your acces token for the remaining routes

```bash
  mutation {
    userLogin(
      username: "user@example.com",
      password: "password"
    ) {
      access_token
    }
  }
```

Get all users

```bash
  query {
    users {
      id
      name
      email
      password
    }
  }
```

Get user by id

```bash
  query {
    user(id: "" ) {
      id
      name
      email
      password
    }
  }
```

Update user by id (required), name (optional), email (optional)

```bash
  mutation {
    updateUser(updateUserInput: {
      id: "",
      name: "",
      email: ""
    }) {
      id
      name
      email
    }
  }
```
