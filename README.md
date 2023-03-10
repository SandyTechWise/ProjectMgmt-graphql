Tried this project to learn the graphql and followed the Traversy Media: 

Youtube Link: https://www.youtube.com/watch?v=BcLNfwF04Kw&ab_channel=TraversyMedia

To run the Server : `npm run dev`

To start the Client : `npm start`


**SERVER PART**
---------------

Built this project with MERN Stack.
GraphQL : https://graphql.org/graphql-js/running-an-express-graphql-server/

1. Create Package: `npm init -y`
2. Install graphql: `npm install express express-graphql graphql mongoose cors colors`
3. other dependencies(nodemon) and .env file : `npm i -D nodemon dotenv`

Setup Environment Variable in .env file for the below : 
```
1. PORT
2. NODE_ENV
3. MONGODB_URI
```

**MongoDB Name** : ProjMgmt DB.

**Server Details**
1. Create graphql schema. Folder: schema -> schema.js
	- Create the types for the date.
	- Create the Root Query.
	- Add mutation.(Add, Update, Delete)

2. Connect the MongoDB. Folder: config -> db.js 
	- Connect the MongoDB database with MongoDB URL.

3. Create Models for the required. Folder: models -> Clinet.js, Project.js
	- model details - Data fields and types will be defined.

4. Connect both graphql and mongo part. Folder: index.js
	- connect MongoDB.
	- use GraphQL.  

```

// Get Clients details (Select Query)
clients {
  id,
  name,
  email,
  phone
}

//Get Projects details (Select Query)
{
  projects {
    name
    description
    status
  }
}

// Mutation Part
// To Add Client (Insert Query)
mutation {
  addClient(name: "Captain America", email: "steverogers@gmail.com", phone: "0909090909") {
    id
    name
    email
    phone
  }
}

// To Delete Client: (Delete Query)
mutation {
  deleteClient(id: "63dc1c7345b49eac5e244663") {
    name
    email
    phone
  }
}

//To Add Project (Insert Query)
mutation {
  addProject(name: "save world", description: "destroy the evil plan and save the world", status: new, clientId: "63dc1267a83192e364a244d4") {
    name
    description
    status
  }
}

// To see project with client details (Select Query)
{
  projects {
    name
    description
    status
    client {
      name
      email
      phone
    }
  }
}


// To Delete Project - this will delete the clientId based on clientId. (Delete Query)
mutation {
	deleteProject(id: "63dc2a127b5fa03982cd89cc"){
    id
    name
  }
}

// To Update the Project (Update Query)
mutation {
  updateProject(id: "63dc25bdf55e017b9e24e563", name: "saved the world", status: completed){
    name
    status
  }
}
```

-------------------------------------------------------------------------------------------------

**CLIENT-PART**
---------------

1. Create React App for the UI inside the "client" Folder.
	- Command: `npx create-reat-app client`
2. Install the dependencies.
	- Command: `npm install @apollo/client graphql react-router-dom react-icons`
3. To start the app.
	- Command: `npm start`
