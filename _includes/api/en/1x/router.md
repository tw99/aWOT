<h2 id="router">Router</h2>

<section markdown="1">
A `Router` is an isolated instance of middleware and routes. You can think of it
as a "mini-application," capable only of performing middleware and routing
functions. Every aWOT application has a built-in default router.

Routers can't be nested. Use it as an argument to [app.route()](#app.router) method. 

##### Example
```arduino
Application app;
Router cats("/cats");

void looooong(Request &req, Response &res) {
  res.print("looooong cat is long!");
}

void ceiling(Request &req, Response &res) {
  res.print("ceiling cat is watching you debug!");
}

void nyannyan(Request &req, Response &res) {
  for (int i = 0; i < 100; i++) {
      res.print("nyan ");
  }
}

void setup() {
  // other setup

  cats.get("/long", &looooong);
  cats.get("/ceiling", &ceiling);
  cats.get("/nyan", &nyannyan);

  app.use(&cats);
}
```

</section>

<h3 id='router.types'>Types</h3>

<section markdown="1">
  {% include api/en/1x/router-Middleware.md %}
</section>

<h3 id='router.methods'>Methods</h3>

<section markdown="1">
  {% include api/en/1x/router-Router.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-all.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-del.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-get.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-options.md %}
</section>
<section markdown="1">
  {% include api/en/1x/router-patch.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-post.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-put.md %}
</section>

<section markdown="1">
  {% include api/en/1x/router-use.md %}
</section>
