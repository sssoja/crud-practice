<h1>CRUD Practice</h1>
The functions to Create, Read, Update, and Delete resources are fundamental components of a usable storage model. You have now seen a couple of examples for how the CRUD paradigm can help us design systems. Now, try to use CRUD to list out routes for a new example model. Imagine we are trying to design a system that keeps track of workout classes, including the name of each class, who teaches it, and the duration of the class. An example class object would look like:
<br>
```js
{
  "class": {
    "id": 1
    "name": “Pure Strength”,
    "trainer": “Bicep Bob”,
    "duration": 1.5
   }
}
```

All of the classes are stored in a classes resource at `www.musclecademy.com/classes`.

For each CRUD operation, write out answers to the following questions:

What routes would you need to implement to provide your workout class model with this CRUD functionality and what are their corresponding HTTP verbs?
What effect would each route have on the database?
What response body would each route return?
What response code would each route return?

<h2>CRUD Answers</h2>

1. Create
   <b>Route</b>: POST/classes
   <b>Effect on datebase:</b> Adds the class provided in the request body to the database
   <b>Response body:</b>
   `{ "class": The Newly-Created Class }`

Example:

```js
{ "class": {
"id": 2
"name": "Boxing",
"trainer": "Bicep Bill",
"duration": 0.5
}}

```

Response code: 201 (CREATED)

2. Read (all classes)
   <b>Route:</b> GET/classes
   <b>Effect on datebase:</b> None
   <b>Response body:</b>
   `{ "classes": [ Array of All Saved Classess ] }`

Example:

```js
{
    "classes":
    [
        "class": {
            "id": 1
            "name": "Pure Strength",
            "trainer": "Bicep Bob",
            "duration": 1.5
        },
        {
            "class": {
                "id": 2
                "name": "Boxing",
                "trainer": "Bicep Bill",
                "duration": 0.5
             }
        },
         {
            "class": {
                "id": 3
                "name": "Swim",
                "trainer": "Swimming Sal",
                "duration": 0.5
             }
        }
    ]
}
```

<b>Response code:</b> 200 (OK)

3. Read (one class)
   <b>Route:</b> GET/classes/:id
   <b>Effect on datebase:</b> None
   <b>Response body:</b>
   `{"class": The class with the specified ID}`

Example:

```js
{
            "class": {
                "id": 2
                "name": "Boxing",
                "trainer": "Bicep Bill",
                "duration": 0.5
             }
        }
```

<b>Response code:</b> 200 (OK)

4. Update
   <b>Route:</b> PUT/classes/:id
   <b>Effect on datebase:</b> Updates the class with the specified ID with the information provided in the request body
   <b>Response body:</b>
   `{ "class": The updated class now saved in the database }`

   Example:

   ```js
   {
            "class": {
                "id": 2
                "name": "Boxing",
                "trainer": "Bicep Barry",
                "duration": 0.5
             }
        }
   ```

<b>Response code:</b> 200 (OK)

5. Delete
   <b>Route:</b> DELETE/classes/:id
   <b>Effect on datebase:</b> Removes the class with the specified ID from the database
   <b>Response body:</b> None
   <b>Response code: </b> 204 (NO CONTENT)

As you get more practice with designing storage systems, incorporating CRUD operations into your models will become easier and easier.
