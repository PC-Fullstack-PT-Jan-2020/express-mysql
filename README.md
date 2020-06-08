# express-mysql

## crud operations:

CREATE:
axios: (post request)

```axios.post('/some-url-path', obj)```

express: (listening to post request)

```router.post('/some-url-path', (req, res, next) => {
  const objectSentFromPost = req.body
  res.send()
})```

CREATE in SQL:
```INSERT INTO users (first, last) VALUES ('john', 'smith');```

READ:
express/axios: (get request)
```axios.get('/some-url-path')```

READ in SQL:
```SELECT * FROM users;```

UPDATE:
express/axios (patch, put request)

UPDATE in SQL:

```UPDATE users SET first = 'a' WHERE id = 1;```


DELETE:
express/axios (delete request)

DELETE in SQL:

```DELETE * FROM users WHERE id = 1```


Executing sql statements from express:

`conn.query('SELECT * FROM todos;' (err, results) => {
    console.log(results)
    res.json(results)
})`