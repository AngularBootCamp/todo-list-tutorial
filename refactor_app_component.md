# Refactor App Component

We're going to perform a small refactoring. The `todo-root` shouldn't have such a large template and all this logic. It should just call another component that will deal with that.

* Create a new component called `list-manager`: 

```
ng g c list-manager -it
```

* Move all the code from `AppComponent` to `ListManagerComponent`
* Call the new component from the `AppComponent` template:

```
  template: `
    <todo-list-manager></todo-list-manager>
  `,
```

That's it! Now we can go on.

