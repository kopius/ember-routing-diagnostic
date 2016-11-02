# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router is responsible for recognizing the URL, matching it to a route,
    firing that route, and passing any params from the URL (such as an :id) to
    the route.

    The route is responsible for getting data (via the model hook or from a
    linking component) and passing it to the correct template to be rendered.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    Inside the template for the campus route, include the following code:
    `{{link-to 'boston' boston}}Link Text{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The former is defined by passing a callback to the 'products' route. The
    latter is defined by explicitly prepending the path with '/products'.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    We reference the value via `params.movie_id`.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We reference the data by the name `model`.
    ```
