# Remove item

The user should be able to remove any item, whether it's still active or completed. Removing an item will be done by clicking a button, aptly named "remove". In this chapter, we'll learn how to add this functionality to our project.

## Add the "remove" button

First, we need to add the button to the item, so we'll work on the file `item.component.ts`.

Add a "remove" button to the item template, with a `click` event handler that calls a `removeItem` method (which we'll create in a moment):

```ts
template: `
  <div class="todo-item">
    {{ todoItem.title }}

    <button class="btn btn-red" (click)="removeItem()">
      remove
    </button>
  </div>
`,
```

Add a new output to the `ItemComponent` class, which will be emitted to the list manager when a user presses the remove button for a specific item:

```ts
@Output() remove:EventEmitter<any> = new EventEmitter();
```

Make sure to import both `EventEmitter` and `Output`:

```ts
import { Component, OnInit, Input, EventEmitter, Output } from '@angular/core';
```

Add a method to the `ItemComponent` class to actually emit the event. This method will be called when the user clicks the "remove" button:

```ts
removeItem() {
  this.remove.emit(this.todoItem);
}
```

## Remove the todo item

Now that each todo item can emit its own removal, let's make sure that the list manager actually removes that same item from the list. For that, we'll work on the file `list-manager.component.ts`.

We need to respond to the `remove` event. Let's add it to the template, inside the `<todo-item>` tag:

```html
<todo-item [todoItem]="item" (remove)="removeItem($event)"></todo-item>
```

Now we just need to add the method `removeItem()` to the `ListManagerComponent` class:

```ts
removeItem(item) {
  this.todoList = this.todoListService.removeItem(item);
}
```

## Remove the todo item from local storage

Removing the item is handled in the service. Open `todo-list.service.ts` and add a method called `removeItem` to the `TodoListService` class:

```ts
removeItem(item) {
  return this.storage.destroy(item);
}
```

This method calls the `destroy` method we already created in `todo-list-storage.service.ts` earlier.

[See the results on StackBlitz](https://stackblitz.com/github/angularbootcamp/todo-list-tutorial-steps/tree/step-17_Remove_item)

