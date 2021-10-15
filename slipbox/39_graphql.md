GraphQL was initially developed in Facebook in 2012; its development is managed by the GraphQL Foundation hosted by the Linux Foundation. GQL is composed of a system type, a query language + execution semantics, static validation and type introspection.

It seems that the main advantage of GraphQL is precision in the request of data. When compared to REST APIs, GQL can handle requests from quickly changing front-ends in a more flexible way. Let's think about how REST APIs work: they basically expose a function or a method on the Web: they are exposed as GET, POST, or PUT endpoints depending on their semantics, and they expect exactly the parameters that the function or method was designed to receive. This means that a new endpoint needs to be created for each different kind data request. GQL, on the other hand, has *a single endpoint* and is thus flexible by design. The logic necessary to translate the GQL query to the actual DB query language is implemented in the back, once and for all. 

Another reason why GQL is preferred over REST APIs in mobile application is responsiveness, as requesting too much data can result in slowing down the application, while requesting too little and then having to request more means doing a lot of calls - and thus slowing down the app.

Querying with GQL is based on understanding the underlying structure of data: in the back-end, the structure of data is defined using the Schema Definition Language in json-like syntax. In the end, the language describes tables.

In place of tables we have *types* (e.g. Fruit), possessing some properties (i.e. the columns of the table, e.g. "name", "weight", "price"). Similarly as in Object Oriented languages, a type can have *another type* as property, which we can request properties of in turn (e.g. the type Tree could have a property Fruit). 

---

### Queries in GQL
To query a DB using GQL, we always need to refer to the `Query` type in the schema definition. That is the single endpoint used for any query to the database. The rest of the schema is composed of types and objects which possibly have dependencies between them. Indeed, it will be possible, as I mentioned above, to make a query in which several objects will be nested. In fact, when a query comprehends an object field, it will be necessary to specify at least one attribute of the object in order for the query to be successful. 

Some fields in a `Query` type can also be *lists*, returning many instances of a particular object or type (e.g. the field `Courses`, a list of `Course` objects).

*Any* query which comprehends an object or a list of them can be filtered on attributes of *any* object(s) included in the query. Similarly as a `WHERE` statement in SQL, we can select e.g. a specific course whose `id` is equal to 123 (passing to the object `Course` a value for the `id` field), or a list of courses whose `type` is 'workshop' (passing to the list type a json expressing our filtering condition).