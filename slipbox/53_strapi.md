# Strapi

## Authentication & authorization
[Official guide](https://strapi.io/blog/a-beginners-guide-to-authentication-and-authorization-in-strapi)

### What's the difference?
Authentication is the process of verifying that a user really is who he/she claims to be. The most common method of authentication is email + username & password, which is also the one used by Strapi.

Authorization regards the permission to access specific resources that each user has. It is the process of establishing whether a user has such access rights and consequently to allow or forbid access to resources to that particular user. Strapi uses JWT Tokens for Authorization.

- What will be the different roles we will need in Join?
   Up to now we have: Super Admin, Editor, Author (in decreasing order of power).


```
Username: mariorossi
Email: mariorossi@test.com
Password: password
```

## Data
Access to data is granted (by design?) in Strapi via GraphQL [39_graphql](39_graphql.md).

Editing data for the user is not allowed by default in Strapi, so a custom method to update user data must be defined following [this guide](https://strapi.io/documentation/developer-docs/latest/development/backend-customization.html#services) (an approach inspired by [this](https://stackoverflow.com/questions/62631528/how-to-update-user-in-strapi?rq=1) StackOverflow thread).

## Backend configuration
### Routes
Routes exposed by the backend can be defined for each `Custom Type` defined by the user. They are associated to some business logic implemented in a `Controller`'s actions and (optionally) to additional controls defined in the policies.

### Policies
These are functions that are executed when an API is called, before executing the business logic implemented in the `Controller`. They can be used to authorize access to resources.


### Controllers
> Controllers are JavaScript files which contain a set of methods called **actions** reached by the client according to the requested route. It means that every time a client requests the route, the action performs the business logic code and sends back the response.


### Services
> Services are a set of reusable functions. They are particularly useful to respect the DRY (don’t repeat yourself) programming concept and to simplify controllers.

### Queries
> Strapi provides a utility function `strapi.query` to make database queries.
> You can just call `strapi.query('modelName', 'pluginName')` to access the query API for any model.

The utility function can also be used to update values in the database. 

### Models
> Models are a representation of the database's structure. They are split into two separate files. A JavaScript file that contains the model options (e.g: lifecycle hooks), and a JSON file that represents the data structure stored in the database.