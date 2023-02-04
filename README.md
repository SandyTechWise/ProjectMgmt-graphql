To run the Project : npm run dev

Going to build this project with MERN Stack.
GraphQL : https://graphql.org/graphql-js/running-an-express-graphql-server/

1. Create Package: "npm init -y"
2. Install graphql: "npm install express express-graphql graphql mongoose cors colors"
3. other dependencies(nodemon) and .env file : "npm i -D nodemon dotenv"

Setup Environment Variable in .env file for the below : 
1. PORT
2. NODE_ENV
3. MONGODB_URI

MongoDB Name : ProjMgmt DB.


// Mutation Part
// To Add Client
mutation {
  addClient(name: "Captain America", email: "steverogers@gmail.com", phone: "0909090909") {
    id
    name
    email
    phone
  }
}

// To Delete Client:
mutation {
  deleteClient(id: "63dc1c7345b49eac5e244663") {
    name
    email
    phone
  }
}

//To Add Project
mutation {
  addProject(name: "save world", description: "destroy the evil plan and save the world", status: new, clientId: "63dc1267a83192e364a244d4") {
    name
    description
    status
  }
}

// To see project with client details
{
  projects {
    name
    status
    client {
      name
      email
    }
  }
}

// To Delete Project - this will delete the clientId based on clientId.
mutation {
	deleteProject(id: "63dc2a127b5fa03982cd89cc"){
    id
    name
  }
}

// To Update the Project
mutation {
  updateProject(id: "63dc25bdf55e017b9e24e563", name: "saved the world", status: completed){
    name
    status
  }
}

