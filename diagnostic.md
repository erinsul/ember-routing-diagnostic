# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The main task inside the Ember Router is defining url paths for routes (whether by
    using the default or specifying). The main task inside an Ember Route is
    gathering data from a model to be passed onto a template later.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}{{/link-to}}
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
    1) The top one is a nested route (and the bottom is not), which means that
    2) it won't overwrite the info that has been rendered from products when a
    user navigates there, while the bottom one will replace products when navigated
    to.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    By calling the model that a Route returns. So if only one, and the model had properties of
    name and age (it's a person, I guess...), you could call model.name and model.age within
    handlebars {{}} to access those properties. If the model contains an array, you can
    call the handlebars helper {{#each model as |your-choice| }} and then the properties of
    the model can be accessed inside handlebars as yourchoice.property.
    ```
