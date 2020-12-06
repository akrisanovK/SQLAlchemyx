# Python-Flask & Graphene-SQLAlchemy(GraphQL) Example
This is a example project for using GraphQL with Flask using Graphene-SQLAlchemy.

## Installing Requirements
Use Virtualenv and install the packages.
```
pip install -r requirements.txt
```
## Running Flask Server
Go to the root dir and run the below line in the terminal.
```
pip install -r requirements.txt
```
## Creating a new Database
Create a database(I used sqlite) with the table structure mentioned in *struct.sql* and update the database name in *database.py* file.

## Testing GraphQL
Below are the example query for adding new user, getting all users, searching for user with username and updating username with email id.
### Adding a New User
```
mutation {
  createUser(name: "abc", email: "hello@abc.com", username: "abc") {
    user {
      id,
      name,
      email,
      username
    }
    ok
  }
}
```
### Getting All Users List
```
{
  allUsers {
    edges {
      node {
        name,
        email,
        username
      }
    }
  }
}
```
### Finding a User with Username
```
{
  findUser(username: "rahulmfg") {
    id,
    name,
    email
  }
}
```
### Updating a Username With Email ID
```
mutation {
  changeUsername(email: "abc@abc.com", username:"newabc") {
    user {
      name,
      email,
      username
    }
  }
}
```
