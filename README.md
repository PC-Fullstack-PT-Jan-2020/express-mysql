# axios express and mysql

## express definitions

### retrive information from post request

```req.body```

### retriving query strings and query parameters

#### query string example

- incoming get request: my-url-path?name=foo

`router.get('/my-url-path', (req, res, next) => {
  const name = req.query.name
  // SQL code HERE
  res.send()
})`

#### query param example

- incoming get request: my-url-path/1

`router.get('/my-url-path/:id', (req, res, next) => {
  const name = req.params.id
  // SQL code HERE
  res.send()
})`

Example of query string and params below:

https://www.youtube.com/watch?v=Q4LzkQ3icRg&list=PLa5bYMAqOz6NzPkb4tFAXDzpvFKzD0MBh&index=112

## crud operations:

### creating a resource

## CREATE:
### axios: (post request)

```axios.post('api/some-url-path', obj)```

### express: (listening to post request)

`router.post('/some-url-path', (req, res, next) => {
  const objectSentFromPost = req.body
  // SQL code HERE
  res.send()
})`

### CREATE in SQL (SQL code HERE):
```INSERT INTO users (first, last) VALUES ('john', 'smith');```

## READ:
### axios: (get request)
```axios.get('api/some-get-path')```

### express: (listening to get request)
`router.get('/some-get-path', (req, res, next) => {
  // SQL code HERE
  res.send()
})`

## READ in SQL (SQL code HERE):
```SELECT * FROM users;```

## UPDATE:
### axios: (patch request)
```axios.patch('api/some-patch-path', objectToPatch)```

### express: (listening to patch request)
`router.patch('/some-patch-path', (req, res, next) => {
  const objectSentFromPost = req.body
  // SQL code HERE
  res.send()
})`

### UPDATE in SQL (SQL code HERE):

```UPDATE users SET first = 'a' WHERE id = 1;```


## DELETE:
### axios: (delete request - passing id...)
```axios.delete('api/some-delete-path/1')```

### express: (listening to delete request)
`router.delete('/some-delete-path/:id', (req, res, next) => {
  const idOfThingToDelete = req.params.id
  // SQL code HERE
  res.send()
})`

### DELETE in SQL:

```DELETE * FROM users WHERE id = 1```


# How to call sql statements from express:

`conn.query('SELECT * FROM todos;' (err, results) => {
    console.log(results)
    res.json(results)
})`

# an example of a route with sql code together

`router.get('/some-get-path', (req, res, next) => {
  conn.query('SELECT * FROM todos;' (err, results) => {
    res.json(results)
  })
})`