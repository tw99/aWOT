<h3 id='app.all'>void all(const char* path, Router::Middleware* middleware);</h3>

This method is like any standard app.METHOD() methods, except it matches all HTTP verbs.

The `app.all()` method is useful for mapping "global" logic for specific path paths.

For more information, see the [routing guide](/guide/routing.html).

##### Example
```arduino
void noDelete(Request &req, Response &res) {
  if (req.method() == Request::DELETE) {
    res.sendStatus(405);
  }
}

app.all("/nodelete", &noDelete);
```